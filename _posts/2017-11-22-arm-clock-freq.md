---
layout: post
title: Estimating Arm clock frequencies
author: James Price
---

As part of the [Isambard Tier-2 HPC service](http://gw4.ac.uk/isambard/) which will deliver a production Arm-based supercomputer with 10000+ Cavium ThunderX2 cores early next year, we're working with an increasing number of different Arm platforms.
With some of these systems being fairly experimental, it can often be difficult to determine some basic information about them, such as the CPU clock frequency.
Conventional approaches such as `lscpu`, `cat /proc/cpuinfo`, and `perf stat` frequently fail to provide this information on Arm systems.

Until this situation improves, I've been using the following simple program to estimate the clock frequency of an Arm CPU.
This program runs a long sequence of `add` instructions written using inline assembler, and estimates the frequency based on the runtime and the number of instructions executed.

```
#include <stdio.h>
#include <stdlib.h>
#include <sys/time.h>

#ifndef ITRS
#define ITRS 1000000000
#endif

int main(int argc, char *argv[])
{
  struct timeval tv;
  gettimeofday(&tv, NULL);
  double start = tv.tv_sec + tv.tv_usec*1e-6;

  long instructions;
  for (instructions = 0; instructions < ITRS; )
  {
#define INST0 "add  %[i], %[i], #1\n\t"
#define INST1 INST0 INST0 INST0 INST0   INST0 INST0 INST0 INST0 \
              INST0 INST0 INST0 INST0   INST0 INST0 INST0 INST0
#define INST2 INST1 INST1 INST1 INST1   INST1 INST1 INST1 INST1 \
              INST1 INST1 INST1 INST1   INST1 INST1 INST1 INST1
#define INST3 INST2 INST2 INST2 INST2   INST2 INST2 INST2 INST2 \
              INST2 INST2 INST2 INST2   INST2 INST2 INST2 INST2
    asm volatile (
      INST3
      : [i] "=r" (instructions)
      :
      : "cc"
      );
  }

  gettimeofday(&tv, NULL);
  double end = tv.tv_sec + tv.tv_usec*1e-6;
  double runtime = end-start;
  printf("Runtime (seconds)     = %lf\n", runtime);
  printf("Instructions executed = %ld\n", instructions);
  printf("Estimated frequency   = %.2lf MHz\n", (instructions/runtime)*1e-6);

  return 0;
}
```

This can be compiled and run using any C compiler that supports the GNU extended assembler syntax:

    # Add -DITRS=##### to change the number of instructions exectuted
    cc -O2 freq.c -o freq

    $ ./freq
    Runtime (seconds)     = 0.499674
    Instructions executed = 1000001536
    Estimated frequency   = 2001.31 MHz

While approximate, this approach works fairly well for determining the CPU frequency.
On a few platforms where I _do_ know the actual frequency, the estimation provided by this program is typically within 1-2% of the real number.
