---
layout: post
title: Bristol HPC at Supercomputing'20
author: Tom Deakin
---

> Workshops, Tutorials and BoFs, Oh My!

The annual Supercomputing conference is always a highlight and one of the busiest times of the HPC year, and this year has been no exception. Not least because of the advanced preparation needed for a virtual conference.

We're involved in lots of different things at SC this year: presenting workshop papers, running remote tutorials, reviewing papers on programme committees, giving booth talks and appearing as panelists for Birds of a Feather sessions. You can find more details below.

Although we won't be seeing you in person this year, do keep in touch: we're on Twitter as [@simonmcs](https://twitter.com/simonmcs) and [@tjdeakin](https://twitter.com/tjdeakin).


## P3HPC'20: International Workshop on Performance, Portability, and Productivity in HPC
Performance Portability is a key reasearch area for the group, and at this year's [P3HPC workshop](http://p3hpc.org) we have two publications.

Tom Deakin, Andrei Poenaru, Tom Lin and Simon McIntosh-Smith have expanded the [2019 survey](https://doi.org/10.1109/P3HPC49587.2019.00006) of performance portability to include the latest and greatest processors (Fujitsu A64FX, NVIDIA A100 Ampere GPUs, Amazon Graviton 2, etc) and programming models such as SYCL.
The paper, *Tracking Performance Portability on the Yellow Brick Road to Exascale*, shows very promising performance portability for open-standard programming models such as OpenMP. We also build on our [2019 study](https://doi.org/10.1109/P3HPC49587.2019.00006) and track some historical trends.

Tom Deakin and Simon McIntosh-Smith have been collaborating with Jason Sewall, John Pennycook and Doug Jacobson from Intel on furthering the fundamental principals of performance portability. The paper, *Interpreting and Visualizing Performance Portability Metrics*, critically asses performance portability metrics and proposes interesting visualisations which help interpret performance portability data.

You can find out when these talks will be shown in the [schedule](https://sc20.supercomputing.org/session/?sess=sess221).

## MCHPC'20: Workshop on Memory Centric High Performance Computing

Batched linear algebra is an important piece of the HPC arsenal. For finite element codes, batches of very small linear systems, are created and solve on the fly. Tom Deakin will present work co-authored with James Cownie, Simon McIntosh-Smith, Justin Lovegrove and Richard Smedley-Stevenson on how the way memory is allocated can cause big performance differences. In the paper, [Hostile Cache Implications for Small, Dense Linear Solves](https://sc20.supercomputing.org/presentation/?id=ws_mchpc102&sess=sess195) which we'll present in the [MCHPC'20 workshop](https://passlab.github.io/mchpc/mchpc2020/), we observe false-sharing cache behaviour, something which is crucial to mitigate for good performance.


## PyHPC 2020: 9th Workshop on Python for High-Performance and Scientific Computing

PhD Student, and Research Engineer at HPE, Clément Foyer will be sharing their work along with Simon McIntosh-Smith and co-authors from BSC and NAG on *Enabling System Wide Shared Memory for Performance Improvement in PyCOMPSs Applications* at the [PYHPC 2020](https://pyhpc.io) workshop. Shared memory support was added to parallel Python programs in PyCOMPSs and they show performance improvements of using this approach.

You can find out when this talk will be shown in the [schedule](https://sc20.supercomputing.org/session/?sess=sess227).


## OpenMP at Supercomputing
There are lots of OpenMP events going on at SC'20 this year: find out more about [OpenMP at SC'20](https://www.openmp.org/events/openmp-sc20/).

Simon McIntosh-Smith and Tom Deakin are running their popular *Programming your GPU with OpenMP: A Hands-on Introduction* tutorial will be split over two days ([Part 1](https://sc20.supercomputing.org/presentation/?id=tut155&sess=sess237) and [Part 2](https://sc20.supercomputing.org/presentation/?id=pec101&sess=sess240)). There are plenty of hands-on exercises planned between pre-recoded presentations, so attendees can gain practical experience writing OpenMP code targeting GPUs in the [Isambard supercomputer](https://gw4.ac.uk/isambard/).

Keep an eye out for our promotional video!

Tom Deakin is presenting a [booth talk](https://www.openmp.org/events/openmp-sc20/#boothtalks) on performance portability of OpenMP on CPUs and GPUs.


## Birds of a Feather: SYCL and C++

Join Simon McIntosh-Smith and Tom Deakin for the
[Khronos SYCL 2020 Release and ISO C++ 20 status and future directions](https://sc20.supercomputing.org/presentation/?id=bof155&sess=sess315) Birds of a Feather. The BoF focuses on SYCL 2020 and C++20 within HPC.

Tom Deakin spoke recently about SYCL and other programming models at [SYCL Summer Sessions](https://sycl.tech/sessions/).

