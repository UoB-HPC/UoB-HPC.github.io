---
layout: page
title: Home
weight: 0
---

The High Performance Computing group, led by [Simon McIntosh-Smith](http://www.cs.bris.ac.uk/home/simonm/), is part of the [Microelectronics Research Group](http://www.cs.bris.ac.uk/Research/Micro/) in the [Department of Computer Science](https://www.cs.bris.ac.uk) at the [University of Bristol](http://www.bristol.ac.uk).

Our research focuses on the application of heterogeneous and many-core computing to solve large-scale scientific problems. Related research problems we are addressing include: performance portability across many-core devices; automatic optimisation of many-core codes; communication-avoiding algorithms for massive scale systems; and fault tolerance software techniques for resiliency at scale.

The group maintains an experimental cluster of some of the fastest and most exotic GPUs and accelerators in the world - see the [web page](/zoo) for information on our ‘Zoo'.

Bristol University also boasts the [Advanced Computing Research Centre](https://www.acrc.bris.ac.uk/) hosting BlueCrystal Phase 3 which featured in the [Top 500](http://www.top500.org/) supercomputers in the world in 2013. The university’s HPC resources include around 10,000 cores and over 100 GPUs and accelerators from Nvidia, Intel and AMD.

The University of Bristol became an [Intel Parallel Computing Center (IPCC)](https://software.intel.com/en-us/ipcc) in January 2014 (see the [press announcement](http://www.bristol.ac.uk/news/2014/january/10099.html)). We were the first such centre in the UK and the seventh worldwide. As part of this initiative we are working with Intel to help modernise HPC codes so that they are ready for future many-core systems, such as the Intel Xeon Phi. This work has already resulted in one of the fastest codes on a Xeon Phi, the BUDE molecular docking code, which achieved 32% of peak performance. We are also optimising CFD and lattice Boltzmann codes, and, in collaboration with AWE and the universities of Warwick and Oxford are developing many-core optimised mini-apps for Sandia’s [Mantevo benchmark suite](https://mantevo.org).

We also offer training in parallel programming. Simon McIntosh-Smith is one of the foremost OpenCL trainers in the world, having taught the subject since 2009. He has run many OpenCL training courses at conferences such as SuperComputing and HiPEAC, and has provided OpenCL training for academic endeavours, including the UK's national supercomputing service, the Barcelona Supercomputing Centre, and Uppsala’s UPMARC summer school. He has also run many OpenCL training courses for commercial entities. With OpenCL training experience ranging from half day on-site introductions within companies, to two-day intensive hands-on workshops for undergraduates, Simon and his team can provide customized OpenCL training to meet your needs. Get in touch if you'd like to know more.

# List of HPC projects underway in the group:

- Development of fully atomistic QM/MM simulations of light harvesting (LH2) complexes found in purple bacteria.  
  Making use of the GPU accelerated quantum chemistry software package [TeraChem](http://www.petachem.com/products.html), we aim to perform the most detailed LH2 calculations ever taken, by scaling the simulation across many GPUs.

- [danceroom Spectroscopy](http://danceroom-spec.com/)  
  OpenCL accelerated interactive real-time molecular dynamics simulations. Using commodity depth sensors such as the LEAP Motion and Microsoft Kinect, we develop artistic and educational platforms allowing the broader public to experience the microscopic world. 

- [BUDE](http://www.bris.ac.uk/biochemistry/research/bude)  
  A GPU accelerated molecular docking program that can be used to perform virtual drug screening, ligand binding site identification on protein surfaces, and protein-protein docking in real space. Collaboration with the School of Biochemistry.

- [ROTORSIM]
  An accelerated CFD code, originall developed by Prof. Chris Allen in the Department of Aerospace Engineering at the University of Bristol. ROTORSIM now includes a port to OpenCL in order to exploit many-core processors such as GPUs and the Intel Xeon Phi.

- [Oclgrind](https://github.com/jrprice/Oclgrind)  
  An extensible OpenCL device simulator that provides a platform with which various OpenCL developer tools can be created. Includes support for detecting memory access errors, race conditions, work-group divergence, and provides an interactive debugging environment.

- Leveraging Multi-Core Technology for Deterministic Neutral Particle Transport at Extreme Scale  
  An investigation into the parallelism of the Sn transport algorithm on an unstructured, domain decomposed mesh, at the core, node and interconnect level (including accelerated devices such as GPUs) using proxy apps including [SNAP](http://www.lanl.gov/projects/feynman-center/technologies/software/snap-sn.php), [DockLeaf](http://uk-mac.github.io/DockLeaf/) and [PalmLeaf](http://uk-mac.github.io/PalmLeaf/).

- [TeaLeaf](http://uk-mac.github.io/TeaLeaf/) and [TeaLeaf 3D](http://uk-mac.github.io/TeaLeaf3D/)  
  Matrix free linear solver. A heat conduction benchmark, part of the [Mantevo Project](https://mantevo.org/).

- [CloverLeaf](http://uk-mac.github.io/CloverLeaf/) and [CloverLeaf 3D](http://uk-mac.github.io/CloverLeaf3D/)  
  A Lagrangian-Eulerian hydrodynamics benchmark, part of the [Mantevo Project](https://mantevo.org/).

- [Hands On OpenCL](http://handsonopencl.github.io/)  
  Hands On OpenCL is a two-day lecture course introducing OpenCL, the API for writing heterogeneous applications. Provided are slides for around twelve lectures, plus some appendices, complete with Examples and Solutions in C, C++ and Python. The lecture series finishes with information on porting CUDA applications to OpenCL.


