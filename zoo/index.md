---
layout: page
title: HPC Zoo
---

In order to test performance portability across a wide range of devices, we maintain a small cluster containing many different accelerator technologies.

### Here from the SC14 tutorial: *OpenCL: A Hands on Introduction*?
- Log in to the cluser with your allocted user name and passwords: `ssh <user>@hpc.cs.bris.ac.uk`
- Copy the Exercises to your home directory: `cp -r ~tom/OpenCL_SC14/ .`
- Upload your Solutions: `scp -r /path/to/your/folder <user>@hpc.cs.bris.ac.uk:~`
- Check out [instructions](#opencl) on how to run on a node

# Access

Access is via ssh using passwordless login. To access the zoo you will need to send us your preferred username and the **public** part of your ssh key.

## Cluster URL
`hpc.cs.bris.ac.uk`

## Generate public key
    $ ssh-keygen
    Generating public/private rsa key pair.
    Enter file in which to save the key (/home/tom/.ssh/id_rsa):
    Enter passphrase (empty for no passphrase):
    Enter same passphrase again:

Then please email us the `id_rsa.pub` file (or whatever you chose to call this file when creating the key).

Note: the public key has extension `.pub` and the private key has *no* extension. Remember to keep your private key private!

## Connect
`ssh <user>@hpc.cs.bris.ac.uk -i ~/.ssh/key`

# Available software

- gcc 4.8.2
- OpenMPI 1.6.5


# Submitting a job
The cluster uses the queuing system [slurm](http://www.schedmd.com/slurmdocs/slurm.html).
By using the queue, you can request interactive and batch jobs to be run on the cluster.
A brief summary of the commands is presented in the table, with some specific example use cases detailed below it.

<table class="zoo-list">
<tr><th>Command</th><th>Usage</th></tr>
<tr><td><code>squeue</code></td><td>List running and queued jobs</td></tr>
<tr><td><code>sinfo</code></td><td>Information about the state of the queues</td></tr>
<tr><td><code>salloc</code></td><td>Allocate nodes and run a command (often <code>bash</code> for an interactive job)</td></tr>
<tr><td><code>srun</code></td><td>Run a command on the nodes allocated to the job (like <code>mpirun</code>)</td></tr>
<tr><td><code>sbatch</code></td><td>Enqueue a batch script, containing a number of <code>srun</code> (or <code>mpirun</code>) commands</td></tr>
<tr><td><code>scancel</code></td><td>Kill a job</td></tr>
</table>

## Examples

We present some sample use cases for testing out applications on the cluster.

### Interactive job
In this example, we would like to request a single node interactively to compile some code.

    $ salloc -n1 bash

This then drops us down to a bash shell to run jobs interactively.
To run a command on the prompt on **all** the nodes in the allocation, we need to  place `srun` at the start of each line: for example `srun ./a.out`.
When we exit the bash shell the job will end.

### MPI Example
In this example, we would like to interactively run a simple 'Hello World' MPI job. We decide we will have 8 MPI tasks.
Firstly, we use `salloc` to allocate an interactive shell job comprising of 8 tasks.
We can then use `mpirun` to run the executable over the 8 tasks.
Note, you don't specify the number of MPI tasks in the `mpirun` command.

    $ salloc -n8 bash
    salloc: Granted job allocation 82
    $ mpirun ./hello_world_c
    Hello, world; from host yawai: process 4 of 8
    Hello, world; from host yawai: process 5 of 8
    Hello, world; from host yawai: process 6 of 8
    Hello, world; from host yawai: process 7 of 8
    Hello, world; from host ohmai: process 1 of 8
    Hello, world; from host ohmai: process 2 of 8
    Hello, world; from host ohmai: process 3 of 8
    Hello, world; from host ohmai: process 0 of 8
    $ exit
    salloc: Relinquishing job allocation 82
    salloc: Job allocation 82 has been revoked.

### OpenCL Example <a name="opencl"></a>
In this example, we would like to run the OpenCL code `./vadd` on a specific GPU.
Use the table below to find the hostname of where the device is hosted.

    ssh <node_name>
    ./vadd

Note: SLURM offers no way to choose specific accelerators in a node, only the node itself.
You can specify to run on any device with `srun -n1 --gres=gpu:1 ./vadd`

### Batch job
Coming soon!

# List of devices

Each of our devices is situated in a host machine, which have different CPUs.

## Nodes
<table class="zoo-list">
<tr><th>Node name</th><th>CPU</th><th>Family</th><th>Cores</th><th>RAM</th></tr>
<tr><td>tldr (head node)</td><td>Intel Xeon CPU W3530 @ 2.80GHz</td><td>Nehalem</td><td>8</td><td>6 GB</td></tr>
<tr><td>yawai</td><td>?</td><td>?</td><td>?</td><td>?</td></tr>
<tr><td>nowai</td><td>?</td><td>?</td><td>?</td><td>?</td></tr>
<tr><td>ohmai</td><td>?</td><td>?</td><td>?</td><td>?</td></tr>
<tr><td>stahp</td><td>Intel Core i5-3550 @ 3.30GHz</td><td>Ivy Bridge</td><td>4</td><td>12 GB</td></tr>
</table>

## Devices

<table class="zoo-list">
<tr>
<th>Device</th>
<th>Vendor</th>
<th>Node</th>
<th>Instructions</th>
</tr>
{% for device in site.data.zoo %}
<tr>
<td>{{ device.device }}</td>
<td>{{ device.vendor }}</td>
<td>{{ device.node }}</td>
<td>{{ device.info }}</td>
</tr>
{% endfor %}
</table>

