---
layout: page
title: HPC Zoo
---

In order to test performance portability across a wide range of devices, we maintain a small cluster containing many different accelerator technologies.



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

## View information about the queues
`squeue`

## Interactive job
`srun`

## Batch job
`sbatch`

## Killing jobs
`scancel`


# List of devices
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

# List of devices
| Device | Vendor | Node | Instructions |
|--------|--------|------|--------------|
{% for device in site.data.zoo %}
| {{ device.device }} | {{ device.vendor }} | {{ device.node }} |{{ device.info }} |
{% endfor %}
</table>
