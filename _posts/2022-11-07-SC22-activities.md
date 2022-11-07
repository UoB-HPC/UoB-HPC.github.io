---
layout: post
title: Bristol HPC at Supercomputing'22
author: Tom Deakin
---

The Supercomputing conference is a highlight of the HPC calendar. This year we're very much looking forward to joining the conference in Dallas, Texas, and (as usual) we expect this to be a busy one for the [High Performance Computing Research Group](https://uob-hpc.github.io) at the University of Bristol. In the official programme, we've got **four** workshop papers to present, **two** Birds of a Feathers to chair, our OpenMP on GPUs tutorial, and a poster! It's been a busy year, and we're looking forward to sharing our work with you all at the conference.


## Performance Portability

Performance Portability and Productivity is one of the key areas of our research in the group here at Bristol. We're pleased to be sharing our latest work on Sunday at the [P3HPC workshop](https://p3hpc.org/workshop/2022/program/) and Monday at the [PMBS'22 workshop](https://www.dcs.warwick.ac.uk/pmbs/pmbs/PMBS/Welcome.html).

We've been working on best practices for writing performance portable parallel programs for a while, and at PMBS we're presenting our evaluations of writing parallel programs directly in ISO language: C++ and Fortran.
Wei-Chen (Tom) Lin will present ["Evaluating ISO C++ Parallel Algorithms on Heterogeneous HPC Systems"](https://sc22.supercomputing.org/?post_type=page&p=3479&id=ws_pmbsf113&sess=sess453) which explores the C++17 parallel algorithms and benchmarks the current performance on CPUs and GPUs. We will also present ["Benchmarking Fortran DO CONCURRENT on CPUs and GPUs Using BabelStream"](https://sc22.supercomputing.org/?post_type=page&p=3479&id=ws_pmbsf108&sess=sess453), a collaboration between the Bristol HPC group and Jeff Hammond (NVIDIA), which looks at the performance portability story for Fortran.

At P3HPC, we're presenting our paper ["Heterogeneous Programming for the Homogeneous Majority"](https://sc22.supercomputing.org/?post_type=page&p=3479&id=ws_p3hpc105&sess=sess428) which took a hard look at how heterogeneous programming models like OpenMP Target, SYCL and Kokkos perform on CPUs. We anticipate high performance CPU-only systems will still be important for some time to come (in all sizes of supercomputer), and so as codes consider their path to GPUs, they're going to have to maintain high performance on CPUs too.


## Processor Simulation

The Bristol HPC Group is also developing a modern, fast, cycle-accurate processor simulator, called [The Simulation Engine (SimEng)](https://uob-hpc.github.io/SimEng/). At PMBS, Finn Wilkinson will present ["An Initial Evaluation of Arm's Scalable Matrix Extension"](https://sc22.supercomputing.org/presentation/?id=ws_pmbss105&sess=sess453). This paper compares the performance of the Arm Scalable Matrix Extension (SME) to Scalable Vector Extension (SVE) in a simulated core based on the Fujitsu A64FX.


## Panels and Birds of a Feathers

One part of Supercomputing I really enjoy is the opportunities in Panels and Birds of a Feather sessions to interact and discuss important topics.

On Sunday, Tom Deakin will appear as a panellist as part of the P3HPC'22 Workshop: ["Blending Accelerated Programming Models in the Face of Increasing Hardware Diversity"](https://sc22.supercomputing.org/presentation/?id=miscp111&sess=sess428). CJ Newburn (NVIDIA) is moderating and has chosen some tough but important questions for us to answer.

On Tuesday, Tom Deakin with chair the SYCL Birds of a Feather, along with Michael Wong (Codeplay/Intel) and James Brodman (Intel): ["Khronos SYCL: Current and Future Directions"](https://sc22.supercomputing.org/presentation/?id=bof152&sess=sess321). We've got a great line up of panellists, so do come along to hear the latest updates about the SYCL ecosystem.

On Wednesday, Simon McIntosh-Smith and Michael Klemm (AMD and CEO OpenMP ARB) will host the OpenMP Birds of a Feather: ["OpenMP API - Present and Future"](https://sc22.supercomputing.org/?post_type=page&p=3479&id=bof122&sess=sess351). This will definitely be one to catch to hear all about the incoming OpenMP 6.0. There are lots of other OpenMP-related events happening at Supercomputing; do checkout, so do checkout [this list to find out more](https://www.openmp.org/events/sc22/).


## Tutorial

Simon McIntosh-Smith and Tom Deakin are looking forward to working once again with Tim Mattson (Intel) on their [Programming Your GPU with OpenMP: A Hands-On Introduction](https://sc22.supercomputing.org/presentation/?id=tut104&sess=sess197) on Monday. This year we'll be using some of the cool new features from OpenMP 5.0 such as `#pragma omp loop`, and attendees will once again be developing and running programs using OpenMP on HPC GPUs in the [GW4 Isambard supercomputer](https://gw4.ac.uk/isambard/).

We may even be able to share some breaking news about some a **new** OpenMP resource coming sometime next year...


## Even more events

Check out a poster showing a collaboration between the Federal University of Sao Carlos, Brazil, the Paris School of Mines and Simon McIntosh-Smith on ["Performance of OpenMP Loop Transformations for the Acoustic Wave Stencil on GPUs"](https://sc22.supercomputing.org/?post_type=page&p=3479&id=rpost119&sess=sess274).

Tom Deakin is speaking at the AWS Booth at 11:30 on Wednesday, with a talk on "Programming and benchmarking AWS Graviton for HPC".

Other groups from the University of Bristol will also be represented at Supercomputing! Do check out this [Invited Talk on "Emergency Forecasting of Volcanic Gas Dispersion"](https://sc22.supercomputing.org/presentation/?id=misc162&sess=sess442) from Mark Woodhouse (Department of Mathematics) and colleagues at the University of Leeds and the National Centre for Atmospheric Science (NCAS), UK.


## Keep in touch!
If you're attending Supercomputing, do come and say hi! We'll be posting regularly on Twitter too, so do follow us at [@simonmcs](https://twitter.com/simonmcs) and [@tjdeakin](https://twitter.com/tjdeakin) too.

## We're hiring!

The High Performance Computing Group has a number of current and upcoming vacancies for staff and PhD projects. If you're interested in hearing more, please [contact us](mailto:S.McIntosh-Smith@bristol.ac.uk,tom.deakin@bristol.ac.uk).
