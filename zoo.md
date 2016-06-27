---
layout: page
title: HPC Zoo
permalink: /zoo/
---

In order to test performance portability across a wide range of devices,
we maintain a small cluster containing many different accelerator technologies.

Access is by [request](mailto:tom.deakin@bristol.ac.uk).

## Contents

| Name                    | Class         | Info       |
| ------------------------|:--------------| -----------|
| NVIDIA K20m             | HPC GPU       | Kepler     |
| NVIDIA K40m             | HPC GPU       | Kepler     |
| NVIDIA GTX 580          | Consumer GPU  | Fermi      |
| NVIDIA GTX 680          | Consumer GPU  | Kepler     |
| NVIDIA GTX 780 Ti       | Consumer GPU  | Kerper     |
| NVIDIA GTX 980 Ti       | Consumer GPU  | Maxwell    |
| AMD S9150               | HPC GPU       | Hawaii     |
| AMD S10000              | HPC GPU       | Tahiti     |
| AMD HD7970              | Consumer GPU  | Tahiti     |
| AMD R9-295X2            | Consumer GPU  | Hawaii     |
| AMD Fury X              | Consumer GPU  | Fiji       |
| Intel Xeon E5-2697 v2   | Server CPU    | Ivy Bridge |
| AMD A10-7850K Radeon R7 | APU           | Kavari     |

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

For example, to run on the K20 GPU:

    qsub -lnodes=1:gpus=1:k20 -I

