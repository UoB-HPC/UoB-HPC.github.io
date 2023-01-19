---
layout: page
title: Projects
permalink: /projects/
---

- [Isambard](http://gw4.ac.uk/isambard/)  
  The Isambard supercomputer, the world's first Arm-based production supercomputer, is a collaboration between the GW4 Alliance, Cray Inc. and the Met Office. Isambard is a Tier-2 high performance computing service for UK-based scientists, providing multiple advanced architectures within the same system, including 64-bit Arm CPUs, the latest Intel and AMD CPUs, and GPUs from NVIDIA and AMD.

- [The Simulation Engine: SimEng](https://uob-hpc.github.io/SimEng/)  
  SimEng is a new, fast, accurate, easy to use and modify cycle-level CPU simulator. Initially focused on modelling Arm and RISC-V CPUs, it comes with a growing array of models, including Arm's latest Neoverse v2 and Apple M1 cores.

- [BabelStream](https://github.com/UoB-HPC/BabelStream)  
  A benchmark used to measure memory bandwidth, in a wide variety of programming models.

- [BUDE / miniBUDE](https://github.com/UoB-HPC/miniBUDE)  
  A GPU accelerated molecular docking program that can be used to perform virtual drug screening, ligand binding site identification on protein surfaces, and protein-protein docking in real space. Collaboration with the School of Biochemistry. Our research group recently produced a mini-app version of BUDE to make it easier to use as an experimental sandpit for emerging parallel programming models and computer architectures.

- [MiniCombust](https://github.com/UoB-HPC/minicombust)
A new mini-app developed as part of the ASiMoV EPSRC prosperity partnership with Rolls-Royce. MiniCombust enables the exploration of combustion codes relevant to gas turbine engines and similar machinery. MiniCombust couples particles (to model fuel droplets) and CFD, and comes in parallel (OpenMP and MP) and serial versions. Written in simple, modern C++, MiniCombbust also enables exploration of emerging parallel programming languages, such as ISO C++ standard parallelism, SYCL and Kokkos. 

- [ExCALIBUR](https://excalibur.ac.uk)
ExCALIBUR is the UK's 5-year Exascale software and algorithms programme. The HPC research group is central to several important parts of ExCALIBUR: Tom Deakin is Co-I for the benchmarking activity, and Simon McIntosh-Smith co-chairs the [hardware and enabling software programme](https://excalibur.ac.uk/themes/hardware-and-enabling-software/), as well as sitting on the steering committee.

- [CloverLeaf](http://uk-mac.github.io/CloverLeaf/) and [CloverLeaf 3D](http://uk-mac.github.io/CloverLeaf3D/)  
  A Lagrangian-Eulerian hydrodynamics benchmark, part of the [Mantevo Project](https://mantevo.org/), and now adopted into the latest version of the [SPEChpc benchmark suite] ().

- [TeaLeaf](https://github.com/UoB-HPC/TeaLeaf)  
  A PPCG-based sparse iterative solver framework and heat diffusion benchmark, part of the [Mantevo Project](https://mantevo.org/). Written in C, with multiple programming models. Original code available at [UK-MAC](http://uk-mac.github.io/TeaLeaf/). Now adopted into the latest version of the [SPEChpc benchmark suite] ().

- [MEGA-STREAM](http://github.com/uk-mac/mega-stream)  
  A benchmark used to investigate why streaming many arrays (with different sizes) causes memory bandwidth limits not to be reached; resulting in latency becoming a dominant factor.

- [The arch project](https://github.com/uob-hpc/arch/)  
  Hosts mini-apps serving as proxies for scientific applications, aiming to provide capability for evaluation of components of the HPC stack. Current: structured heat diffusion, hydrodynamics, an FFT-based Poisson solver and Monte Carlo neutral particle transport. In progress: Deterministic neutral particle transport, and unstructured variations of the heat diffusion and Monte Carlo neutral particle transport.

- Leveraging Multi-Core Technology for Deterministic Neutral Particle Transport at Extreme Scale  
  An investigation into the parallelism of the Sn transport algorithm on an unstructured, domain decomposed mesh, at the core, node and interconnect level (including accelerated devices such as GPUs) using proxy apps including [SNAP](http://www.lanl.gov/projects/feynman-center/technologies/software/snap-sn.php).

- [Oclgrind](https://github.com/jrprice/Oclgrind)  
  An extensible OpenCL device simulator that provides a platform with which various OpenCL developer tools can be created. Includes support for detecting memory access errors, race conditions, work-group divergence, and provides an interactive debugging environment.

- [Hands On OpenCL](http://handsonopencl.github.io/)  
  Hands On OpenCL is a two-day lecture course introducing OpenCL, the API for writing heterogeneous applications. Provided are slides for around twelve lectures, plus some appendices, complete with Examples and Solutions in C, C++ and Python. The lecture series finishes with information on porting CUDA applications to OpenCL.

- ROTORSIM  
  An accelerated CFD code, originall developed by Prof. Chris Allen in the Department of Aerospace Engineering at the University of Bristol. ROTORSIM now includes a port to OpenCL in order to exploit many-core processors such as GPUs and the Intel Xeon Phi.

- [danceroom Spectroscopy](http://danceroom-spec.com/)  
  OpenCL accelerated interactive real-time molecular dynamics simulations. Using commodity depth sensors such as the LEAP Motion and Microsoft Kinect, we develop artistic and educational platforms allowing the broader public to experience the microscopic world. 

- Development of fully atomistic QM/MM simulations of light harvesting (LH2) complexes found in purple bacteria.  
  Making use of the GPU accelerated quantum chemistry software package [TeraChem](http://www.petachem.com/products.html), we aim to perform the most detailed LH2 calculations ever taken, by scaling the simulation across many GPUs.

