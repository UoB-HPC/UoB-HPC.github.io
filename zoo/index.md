---
layout: page
title: HPC Zoo
---

In order to test performance portability across a wide range of devices, we maintain a small cluster containing many different accelerator technologies.

# Cluster URL
`hpc.cs.bris.ac.uk`

# List of devices

Each of our devices is situated in a host machine, which have different CPUs.

## Nodes
<table class="zoo-list">
<tr><th>Node name</th><th>CPU</th><th>Family</th><th>Cores</th><th>RAM</th></tr>
<tr><td>tldr (head node)</td><td>Intel Xeon CPU W3530 @ 2.80GHz</td><td>Nehalem</td><td>4</td><td>6 GB</td></tr>
<tr><td>yawai</td><td>Intel Core i5-3550 CPU @ 3.30GHz</td><td>Ivy Bridge</td><td>4</td><td>16 GB</td></tr>
<tr><td><del>nowai</del></td><td><del>Intel Core i5-3550 CPU @ 3.30GHz</del></td><td><del>Ivy Bridge</del></td><td><del>4</del></td><td><del>16 GB</del></td></tr>
<tr><td>awyiss</td><td>Intel Core i5-4590 CPU @ 3.30GHz</td><td>Haswell</td><td>4</td><td>32 GB</td></tr>
<tr><td>ohmai</td><td>Intel Core i5-4590 CPU @ 3.30GHz</td><td>Haswell</td><td>4</td><td>32 GB</td></tr>
<tr><td>stahp</td><td>Intel Core i5-4590 CPU @ 3.30GHz</td><td>Haswell</td><td>4</td><td>32 GB</td></tr>
<tr><td>umwat</td><td>Intel Core i5-3550 CPU @ 3.30GHz</td><td>Ivy Bridge</td><td>4</td><td>12 GB</td></tr>

</table>

## Devices

<table class="zoo-list">
<tr>
<th>Device</th>
<th>Vendor</th>
<th>Node</th>
</tr>
{% for device in site.data.zoo %}
<tr>
<td>{{ device.device }}</td>
<td>{{ device.vendor }}</td>
<td>{{ device.node }}</td>
</tr>
{% endfor %}
</table>

