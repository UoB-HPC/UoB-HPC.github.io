---
layout: page
title: HPC Zoo
permalink: /zoo/
---

In order to test performance portability across a wide range of devices,
we maintain a small cluster containing many different accelerator technologies.

Access is by [request](mailto:tom.deakin@bristol.ac.uk).

## Contents

| Name                    | Class         | Architecture | Queue command                |
| ------------------------|:--------------| -------------|------------------------------|
| NVIDIA K20m             | HPC GPU       | Kepler       | `-lnodes=1:gpus=1:k20`       |
| NVIDIA K40m             | HPC GPU       | Kepler       | `-lnodes=1:gpus=1:k40`       |
| NVIDIA GTX 580          | Consumer GPU  | Fermi        | `-lnodes=1:gpus=1:gtx580`    |
| NVIDIA GTX 680          | Consumer GPU  | Kepler       | `-lnodes=1:gpus=1:gtx680`    |
| NVIDIA GTX 780 Ti       | Consumer GPU  | Kerper       | `-lnodes=1:gpus=1:gtx780ti`  |
| NVIDIA GTX 980 Ti       | Consumer GPU  | Maxwell      | `-lnodes=1:gpus=1:gtx980ti`  |
| AMD S9150               | HPC GPU       | Hawaii       | `-lnodes=1:gpus=1:s9150`     |
| AMD S10000              | HPC GPU       | Tahiti       | Unavailable                  |
| AMD HD7970              | Consumer GPU  | Tahiti       | `-lnodes=1:gpus=1:hd7970`    |
| AMD R9-295X2            | Consumer GPU  | Hawaii       | `-lnodes=1:gpus=1:r9-295x2`  |
| AMD R9-290X             | Consumer GPU  | Hawaii       | `-lnodes=1:gpus=1:r9-290x`   |
| AMD Fury X              | Consumer GPU  | Fiji         | `-lnodes=1:gpus=1:furyx`     |
| Intel Xeon E5-2697 v2   | Server CPU    | Ivy Bridge   | `-lnodes=1:ivybridge`        |
| AMD A10-7850K Radeon R7 | APU           | Kaveri       | `-lnodes=1:kaveri`           |

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

You can specify any NVIDIA or AMD gpu using the following:

    qsub -lnodes=1:gpus=1:nvidia -I
    qsub -lnodes=1:gpus=1:amd -I

You can also request by architecture, for example:

    qsub -lnodes=1:gpus=1:kepler
