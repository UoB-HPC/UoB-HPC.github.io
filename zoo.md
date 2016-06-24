---
layout: page
title: HPC Zoo
permalink: /zoo/
---

In order to test performance portability across a wide range of devices,
we maintain a small cluster containing many different accelerator technologies.

Access is by [request](mailto:tom.deakin@bristol.ac.uk).

## Contents

| Name              | Class         | Info  |
| ------------------|:--------------| ------|
| NVIDIA K20m       | HPC GPU       |       |
| NVIDIA K40m       | HPC GPU       |       |
| NVIDIA GTX 580    | Consumer GPU  |       |
| NVIDIA GTX 680    | Consumer GPU  |       |
| NVIDIA GTX 980 Ti | Consumer GPU  |       |
| AMD S9150         | HPC GPU       |       |
| AMD S10000        | HPC GPU       |       |
| AMD Fury X        | Consumer GPU  |       |
| Ivy Bridge        | Server CPU    |       |

## Documentation

Connect to the headnode via ssh at `hpc.cs.bris.ac.uk`.

### Software

Tools and compilers are made available via the `module` command.

List available software: `module avail`

Load a module: `module load <name>`

Unload a module: `module unload <name>`

### Running jobs

We use the TORQUE (PBS) queueing system to manage job allocations of the cluster.

#### Interactive job

You can launch an interactive job requesting the gpu `<name>` (all lower case) using

    qsub -lnodes=1:gpus=1:<name> -I


