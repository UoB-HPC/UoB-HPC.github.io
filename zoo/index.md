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
<tr><th>Node</th><th>CPU</th><th>Family</th><th>Cores</th><th>RAM</th></tr>
<tr><td>Head node</td><td>Intel Xeon CPU W3530 @ 2.80GHz</td><td>Nehalem</td><td>4</td><td>6 GB</td></tr>
<tr><td>A</td><td>Intel Core i5-3550 CPU @ 3.30GHz</td><td>Ivy Bridge</td><td>4</td><td>16 GB</td></tr>
<tr><td>B</td><td>Intel Core i5-3550 CPU @ 3.30GHz</td><td>Ivy Bridge</td><td>4</td><td>16 GB</td></tr>
<tr><td>C</td><td>Intel Core i5-4590 CPU @ 3.30GHz</td><td>Haswell</td><td>4</td><td>32 GB</td></tr>
<tr><td>D</td><td>Intel Core i5-4590 CPU @ 3.30GHz</td><td>Haswell</td><td>4</td><td>32 GB</td></tr>
<tr><td>E</td><td>Intel Core i5-4590 CPU @ 3.30GHz</td><td>Haswell</td><td>4</td><td>32 GB</td></tr>
<tr><td>F</td><td>Intel Core i5-3550 CPU @ 3.30GHz</td><td>Ivy Bridge</td><td>4</td><td>12 GB</td></tr>

</table>

## Devices

<table class="zoo-list">
<tr>
<th>Device</th>
<th>Vendor</th>
</tr>
{% for device in site.data.zoo %}
<tr>
<td>{{ device.device }}</td>
<td>{{ device.vendor }}</td>
</tr>
{% endfor %}
</table>

