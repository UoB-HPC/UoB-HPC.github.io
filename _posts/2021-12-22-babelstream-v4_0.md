---
layout: post
title: BabelStream v4.0 Released
author: Tom Deakin
---

![BabelStream logo repeated 4 times]({{site.url}}/assets/babelstream_v4.png){:width="100%"} 

We are pleased to announce the latest [release of BabelStream](https://github.com/UoB-HPC/BabelStream/releases/tag/v4.0). This update adds new implementations in parallel programming models, including ISO C++, SYCL 2020, TBB and Thrust. We also include new standalone implementations in the Julia, Rust and Scala languages. Our build system has been updated to use CMake exclusively, and provides recommended build parameters for major compilers for all programming models.

BabelStream is a benchmark used to measure the main memory bandwidth attainable across a diverse range of CPU and GPU processors. The benchmark is implemented in a wide range of parallel programming models in a consistent manner following best practices for each programming model. This allows BabelStream to measure the sustained main memory bandwidth on a diverse range of processors.

BabelStream is based on the famous [STREAM](https://www.cs.virginia.edu/stream/) benchmark, but differs in important ways to make it representative of today's scientific applications. BabelStream requires the size of the arrays to be set at runtime, and allocated dynamically on the heap, rather than fixed at compile time - just as the problem sizes of scientific applications are known only at runtime. The breadth of implementations provides a way to run the benchmark on both CPUs and GPUs. We also incorporate two additional kernels: a dot product and the "nstream" kernel from the [Parallel Research Kernels (PRK)](https://github.com/ParRes/Kernels).

You can read more about updating BabelStream's SYCL implementation from 1.2.1 to 2020 in [our earlier post](http://uob-hpc.github.io/2021/02/09/SYCL-2020.html).

The latest version of BabelStream is available [on GitHub](https://github.com/uob-hpc/babelstream).


## BabelStream enabled research

Since the previous release in April 2019, we've used BabelStream extensively in our own research, and have published a number of papers at international workshops and conferences. The following papers have all used BabelStream; as well as providing up to date results across a wide range of computer architectures, they show the advances we have made in understanding and developing the field of performance portability that this benchmark has enabled. 

In collaboration with Intel, we released our latest summative work on performance portability *[Navigating Performance, Portability and Productivity](https://doi.org/10.1109/MCSE.2021.3097276)* in the IEEE Computing in Science and Engineering Special Issue on Performance Portability (the [authors accepted manuscript](https://research-information.bris.ac.uk/en/publications/navigating-performance-portability-and-productivity) is available via the University of Bristol).

Wei-Chen Lin used BabelStream as part of his work [tracking the historical performance of SYCL implementations](https://doi.org/10.1145/3456669.3456701) at [IWOCL'21](https://www.iwocl.org/iwocl-2021/conference-program/). This was a great follow on from our previous study in exploring [SYCL for HPC-style applications](https://doi.org/10.1145/3388333.3388643) which was presented at [IWOCL'20](https://www.youtube.com/watch?v=5W6SsreZ3ew). Wei-Chen also used BabelStream to evaluate Julia for HPC ([DOI - not yet active](https://doi.org/10.1109/PMBS54543.2021.0001)) in the 2021 [IEEE International Workshop on Performance Modeling, Benchmarking and Simulation of High Performance Computer Systems (PMBS)](https://www.dcs.warwick.ac.uk/pmbs/pmbs/PMBS/Schedule.html).

Our [2020 study](https://doi.org/10.1109/P3HPC51967.2020.00006), shared at the [International Performance Portability and Productivity Workshop at Supercomputing (P3HPC)](https://p3hpc.org), used BabelStream as one application we used to track how performance portability of different programming models has improved over a diverse range of processors. This extended our [earlier 2019 study](https://doi.org/10.1109/P3HPC49587.2019.00006) where we used a suite of applications which included BabelStream to assess the performance portability landscape.



## Highlighted release notes

For a detailed list of changes please see the [CHANGELOG](https://github.com/UoB-HPC/BabelStream/blob/main/CHANGELOG.md).
Some notable changes are:

* New implementations, including ISO C++, SYCL 2020, TBB, Thrust, Julia, Rust and Scala.
* The addition of the "nstream" kernel, which has an access pattern which requires, and therefore accounts for, read-for-ownership.
* The primary branch is now `main`. Please make sure you update your bookmarks.
* The build system has migrated to CMake. We not longer make available Makefiles.
* The GitHub repository now runs Continuous Integration to ensure all models build with a variety of freely available compilers in each update.

> Find out more about Dr Tom Deakin at [his website: https://hpc.tomdeakin.com](https://hpc.tomdeakin.com).
