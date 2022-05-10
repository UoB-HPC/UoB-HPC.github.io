---
layout: page
title: Projects
permalink: /projects/
---

- [Isambard](http://gw4.ac.uk/isambard/)  
  The Isambard supercomputer, a collaboration between the GW4 Alliance, Cray Inc. and the Met Office, aims to deliver a Tier 2 high performance computing service for UK-based scientists. It will provide multiple advanced architectures within the same system, and includes 64-bit ARM CPUs, Intel Xeon and Xeon Phi processors and NVIDIA GPUs.

- [BabelStream](http://github.com/uob-hpc/BabelStream/)  
  A benchmark used to measure memory bandwidth, in a wide variety of programming models.

- [MEGA-STREAM](http://github.com/uk-mac/mega-stream)  
  A benchmark used to investigate why streaming many arrays (with different sizes) causes memory bandwidth limits not to be reached; resulting in latency becoming a dominant factor.

- [The arch project](https://github.com/uob-hpc/arch/)  
  Hosts mini-apps serving as proxies for scientific applications, aiming to provide capability for evaluation of components of the HPC stack. Current: structured heat diffusion, hydrodynamics, an FFT-based Poisson solver and Monte Carlo neutral particle transport. In progress: Deterministic neutral particle transport, and unstructured variations of the heat diffusion and Monte Carlo neutral particle transport.

- Leveraging Multi-Core Technology for Deterministic Neutral Particle Transport at Extreme Scale  
  An investigation into the parallelism of the Sn transport algorithm on an unstructured, domain decomposed mesh, at the core, node and interconnect level (including accelerated devices such as GPUs) using proxy apps including [SNAP](http://www.lanl.gov/projects/feynman-center/technologies/software/snap-sn.php).

- [CloverLeaf](http://uk-mac.github.io/CloverLeaf/) and [CloverLeaf 3D](http://uk-mac.github.io/CloverLeaf3D/)  
  A Lagrangian-Eulerian hydrodynamics benchmark, part of the [Mantevo Project](https://mantevo.org/).

- [TeaLeaf](https://github.com/UoB-HPC/TeaLeaf)  
  A PPCG-based sparse iterative solver framework and heat diffusion benchmark, part of the [Mantevo Project](https://mantevo.org/). Written in C, with multiple programming models. Original code available at [UK-MAC](http://uk-mac.github.io/TeaLeaf/).

- [Oclgrind](https://github.com/jrprice/Oclgrind)  
  An extensible OpenCL device simulator that provides a platform with which various OpenCL developer tools can be created. Includes support for detecting memory access errors, race conditions, work-group divergence, and provides an interactive debugging environment.

- [BUDE](http://www.bris.ac.uk/biochemistry/research/bude)  
  A GPU accelerated molecular docking program that can be used to perform virtual drug screening, ligand binding site identification on protein surfaces, and protein-protein docking in real space. Collaboration with the School of Biochemistry.

- [Hands On OpenCL](http://handsonopencl.github.io/)  
  Hands On OpenCL is a two-day lecture course introducing OpenCL, the API for writing heterogeneous applications. Provided are slides for around twelve lectures, plus some appendices, complete with Examples and Solutions in C, C++ and Python. The lecture series finishes with information on porting CUDA applications to OpenCL.

- [ROTORSIM]()  
  An accelerated CFD code, originall developed by Prof. Chris Allen in the Department of Aerospace Engineering at the University of Bristol. ROTORSIM now includes a port to OpenCL in order to exploit many-core processors such as GPUs and the Intel Xeon Phi.

- [danceroom Spectroscopy](http://danceroom-spec.com/)  
  OpenCL accelerated interactive real-time molecular dynamics simulations. Using commodity depth sensors such as the LEAP Motion and Microsoft Kinect, we develop artistic and educational platforms allowing the broader public to experience the microscopic world. 

- Development of fully atomistic QM/MM simulations of light harvesting (LH2) complexes found in purple bacteria.  
  Making use of the GPU accelerated quantum chemistry software package [TeraChem](http://www.petachem.com/products.html), we aim to perform the most detailed LH2 calculations ever taken, by scaling the simulation across many GPUs.

