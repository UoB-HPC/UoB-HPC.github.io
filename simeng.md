---
layout: page
title: Simulation Engine
permalink: /SimEng/
---

The Simulation Engine framework (SimEng) provides a modern cycle-accurate processor simulator, with aims to be:

* Fast
* Easy to use and modify to desired configurations
* Scalable, supporting simulation of simple scalar cores, up to superscalar out-of-order designs
* Capable of supporting a wide range of ISAs, starting with ARMv8 but eventually including x86, RISC-V, POWER, etc.
* Open source, with a permissive license to enable collaboration across academia and industry

The purpose of SimEng is to provide an alternative to the existing industry standard, [gem5](https://www.gem5.org/), by placing an emphasis on performance and scalability from the start, and maintaining a clean, modern, and well-documented code base.

## Current Support
Under its current developed state, SimEng targets the ARMv8+SVE ISA with the ability to model up to out-of-order, superscalar, single-core processors and emulate a subset of system-level function calls. It supports statically compiled C binaries that run on real hardware and models memory as an infinite L1 cache. 

The main component provided by the simulator is a discrete processor core model, a generic variant seen below, which accepts a clock signal and supports a memory access interface. A configuration file, YAML format, can be passed to the simulation to modify the core model and tuned to the specification of current or experimental hardware. Currently, SimEng has been configured to model a Marvell ThunderX2 and Fujitsu A64FX processor.

![alt text]({{site.url}}/assets/simeng_generic_core_model.png "Generic Core Model"){:height="75%" width="75%"}

Once the core model is mature enough, integration with the [Structural Simulation Toolkit](http://sst-simulator.org/) (SST) is planned to support multi-core and memory hierarchy simulation. To date, a prototype of SST's memory hierarchy integration has been created.

Additional documentation for SimEng can be found [here](http://uob-hpc.github.io/SimEng-Docs/).

## Talks and presentations
SimEng has been presented by [Professor Simon McIntosh-Smith](http://uob-hpc.github.io/SimonMS/) at previous Workshop on Modeling & Simulation of Systems and Applications (ModSim) events:

* ModSim 2019 - [Enabling Processor Design Space Exploration with SimEng]({{site.url}}/assets/simeng_modsim_2019.pdf)

Additional presentation given:

* [Modelling Advanced Arm-based CPUs with SimEng]({{site.url}}/assets/simeng_arm_cpus.pdf)

## Release
SimEng is planned for open source release during summer 2021 under an [Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0) license.

## External projects usage
* [Capstone disassembly engine](https://www.capstone-engine.org/) - Instruction decoding
* [Yaml-cpp](https://github.com/jbeder/yaml-cpp) - Parsing YAML configuration files
* [Googletest](https://github.com/google/googletest) - Framework for test suite
* [LLVM](https://github.com/llvm-mirror/llvm) - Generation of binaries for use in the regression test suite

## Funding
EPSRC ASiMoV project (Advanced Simulation and Modelling of Virtual systems) EP/S005072/1, Arm via a Centre of Excellence in HPC at University of Bristol