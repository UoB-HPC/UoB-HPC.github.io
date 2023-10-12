---
layout: post
title: "BabelStream v5: now with added Fortran!"
author: Tom Deakin
---

![BabelStream logo with a sticker saying "Now with added Fortran!"]({{site.url}}/assets/babelstream_v5.png){: width="50%" style="display:block; margin-left:auto; margin-right:auto;"}

## BabelStream v5.0 is now [available on GitHub](https://github.com/uob-hpc/babelstream).


It's been a little while since the last release in 2021, but we've been busy working on adding lots of new features, along with the few fixes.

There are new implementations, most notably in __Fortran__ as a result of a collaboration which resulted in a [research paper at the PMBS workshop at SC'22](https://doi.org/10.1109/PMBS56514.2022.00013). We have also added a SYCL 2020 version that uses Unified Shared Memory (USM) to complement the Buffer/Accessor model in the first implementation.

The benchmark now also reports timing and sustained bandwidth for the data initialisation and device-to-host copy; important phases of heterogeneous programming models that we need to quantify. We hope that this will be a useful addition, especially where some models (like SYCL) support unified shared memory.

Initial support for BabelStream is also available in the [Spack package manager](https://packages.spack.io/package.html?name=babelstream), thanks to support from an [ExCALIBUR project](https://hpc.tomdeakin.com/projects/excalibur-benchmarking).
Bringing the complete software environment to run BabelStream using several of the programming models on a new platform (something the team here in Bristol does regularly) can be challenging due to the breadth of dependencies required (compilers, runtimes, libraries, etc). More details of building the benchmark with Spack will be shared at the [HPCTESTS Workshop at SC'23](https://sc23.supercomputing.org/presentation/?id=ws_hpct103&sess=sess464) in November.

Thanks to the team here in the University of Bristol HPC Research Group, especially Wei-Chen (Tom) Lin and Kaan Olgu.

