---
layout: post
title: Which performance portable programming model should I use?
author: Tom Deakin
---

This post has come about after we were asked the following question recently:

> I want to run my code on CPUs and GPUs from different vendors without having to duplicate everything in different languages each time. Which parallel programming model should I use?

It's a question we've regularly thought about in the HPC group at the University of Bristol over the years.
It's tricky to answer this question as it involves some prediction of the future, which is notoriously hard!
The best response can also depend on what the code looks like today.

There are a number of ways to approach this and we discuss a few of the options in this blog post.

## Attack of the clones

One possible approach we've used is to bear the burden of maintaining multiple versions of codes in each programming model we care about.
This is more a pragmatic approach rather than a maintainable one, especially for an application which must endure in a production environment.
This approach is often used where compiler support is limited for a particular combination of platform and model; unfortunately we often find that Fortran compilers are the last to include the latest features and so we must use a different host language such as C in order to try things out.
However, where codebases are of moderate size, we're able to port codes from one programming model to another within a few weeks.

This allows us to start asking questions about performance portability, which we did in [our paper at P3HPC](https://conferences.computer.org/sc19w/2019/pdfs/P3HPC2019-4EEo872AT37XFNn0hNAzRv/28Dv6zrZOx4Ed9bIsN7Le2/6QPaLH6KpgoskTkAyLU1vj.pdf).
In this study we took mini-apps written in a variety of programming models, including high level C++ abstractions like Kokkos, directive based models like OpenMP and OpenACC, and low level APIs such as OpenCL and CUDA.
We tried to run each of the codes, implemented in each model, across a diverse range of hardware from many different vendors.
This included CPUs from AMD, Intel and Marvell, GPUs from AMD and NVIDIA, and other devices such as the NEC SX-Aurora Vector Engine and Data Centre Arm CPUs from Ampere.
This study highlights the challenge of making the choice this question poses.


## Self-isolation

A more refined approach is to isolate parts of the code behind an interface of some sort.
This isn’t some grandiose library affair though: it just means that there are specialisations of parts of the code.
HPC applications are often made up of different parts, with main structural code driving some critical routines.
Those critical routines, or kernels, can then be specialised in a programming model best suited for each target architecture.
This also allows you to specialise algorithm choice depending on the platform.

The general idea is that you'd have a version of the key routines in different files with a canonical function call in the driving code.
When you compile your code, you can then pick the versions you need.
The result is a plug-and-play code you can implement in any language needed to run on the devices you want.

Our [BabelStream](https://github.com/UoB-HPC/BabelStream) code is an extreme example of this approach.
The simple STREAM kernels are implemented in 10 different programming models and called from a main driver code containing the output and timing routines.
We made the decision with this code that each implementation would own the data, and be responsible for memory allocation, initialisation and deallocation.
This was important as some models have different ideas when it comes to memory management, requiring different data types or other abstractions.

Obviously the problem with this approach is precisely that there are all of these different kernel files, each of which contains a separate implementation of your core algorithm,
and each of which needs to be maintained and updated if you find a bug.

## The search for the grail

The ideal would, of course, be to use a portable language so that you only have one version of the code that runs well on all of your platforms.
In our experience we have found that OpenCL can achieve this and has provided performant, portable code for a long time.
Support is fairly widespread from all vendors today.
The community support is also abundant with tools from the LLVM project (Khronos highlights some of these in their [blog post](https://www.khronos.org/blog/new-and-enhanced-opencl-open-source-tools-resources)) and cross-platform runtimes such as [Pocl](http://portablecl.org).
A minor downside though is the split source model with kernels represented in strings, often loaded from a file at runtime.

The OpenMP(r) standard has had support for programming heterogeneous devices in the programming model since OpenMP 4.0 was released in 2013. 
This allowed OpenMP to supporting a huge range of devices including CPUs and GPUs.
The refinements to the specification in 4.5 and 5.0 are big improvements in the ease of writing code to target different devices.
However, there is still a want of widespread compiler support for offload in the 3 base languages (C, C++ and Fortran) across all hardware vendors.
As our P3HPC study showed, we were able to get some of the best performance with OpenMP, however either the performance or simple lack of support for some processors means that it is not yet enabling developers to deliver on the goal of writing a code with portable performance.
OpenMP's historic support for parallelism on CPUs also means that the device support sometimes feels grafted on, and it is currently hard to write a set of directives which work well whether the code ends up running on a GPU device or a CPU.

For single source file C++ abstractions, SYCL is the natural choice.
It’s an open standard, single source, modern C++ parallel programming model from Khronos.
Intel has recently announced that  the "Data Parallel C++ (DPC++)" language which is a key component of their "oneAPI" programming model is based on SYCL (with some Intel extensions if you want to use them).
As such there is momentum behind SYCL in the HPC space, but this needs to be boosted by support from all vendors in their own compilers.
At the moment, no other hardware vendor has announced SYCL support, though there are independent software vendors (such as Codeplay) who are producing [LLVM based SYCL implementations](https://codeplay.com/portal/02-03-20-codeplay-contribution-to-dpcpp-brings-sycl-support-for-nvidia-gpus).
We've had great success running SYCL code on GPUs from Intel, AMD and NVIDIA, and on CPUs from Intel, and are expanding our experience with support for other CPUs.
The results were presented at [IWOCL and SYCLCon 2020](https://dl.acm.org/doi/abs/10.1145/3388333.3388643) ([watch the presentation online](https://youtu.be/5W6SsreZ3ew)) and demonstrate that performance code to the proprietary vendor languages was possible for a variety of codes.
We used community tools for many of the results but as a community we need commitment of vendor support from all.


## Pragmatism

The presence of the C++ abstraction layers [Kokkos](https://github.com/kokkos/kokkos) from Sandia National Laboratory and [RAJA](https://github.com/LLNL/RAJA) from Lawrence Livermore National Laboratory shows the urgent requirement for performance portable programming models that are available *today*.
These layers come with different, potentially target specific, backends which enable support on many platforms for different vendors without requiring significant user-level code changes once the abstraction has been introduced.
The labs write backends in whatever language is required to run on their next platform.
The results are promising as performance is often close to native performance (see our P3HPC study for examples).
Unfortunately, some backends are missing from their mainstream releases so not all platforms are yet supported. However the range of US Exascale systems due to come online over the coming years should widen the support.

These layers, along with SYCL, are also trying to inform the direction of standard C++, so we can hope that by about 2030 this debate will become moot, since the answer will just be "ISO C++".
This isn't a new idea though: Fortran has long since included parallel execution through Coarrays and `DO CONCURENT` blocks, however that support has not proved sufficient on its own.
Luckily, the common DNA in all these C++ abstractions (Kokkos, RAJA and SYCL) means that porting between them can often be a straightforward exercise.


## Taking stock

It’s tricky to advise on just picking one model to write code in today.
This is a much more difficult question to answer than it first appears.
Open standards are the best answer we have to encourage the diversity and choice in hardware we need in HPC.
But whatever the solution is, it requires support from a wide range of platforms and the current landscape has some areas for improvement.
Perhaps we need to think of HPC codes a fluid objects, and so the approach we take today should be flexible to morph into whatever becomes the next best approach.

Let's use these ideas to start a discussion in the community.
Which programming model would you recommend today? And why?


