---
layout: post
title: Keynote on Heterogeneous Computing at CIUK, December 2021
author: Simon McIntosh-Smith
---


![alt text]({{site.url}}/assets/CIUK_keynote_photo.jpg "CIUK keynote talk"){:width="75%"} 


Prof. Simon McIntosh-Smith, head of the HPC Research Group at the University of Bristol, gave an invited keynote to an audience of around 200 people at the Computing Insight UK 2021 conference in Manchester on Thursday December 9th. 

Simon has been designing, developing and programming heterogeneous systems since 1994, when he joined Inmos/STMicro to work on early generations of embedded System on Chip (SoC) processors for the first generation of digital set top boxes for the home. 

In his keynote on heterogeneous computing, he described how early computers were nearly all heterogeneous. For example, in the mid 1960s, the Seymour Cray-designed CDC6600 sported 10 programmable co-processors sitting alongside the CPU. Systems became increasingly homogeneous as the silicon transistor and large-scale integration meant that CPUs and SoCs could include most of a system in a single chip. However, heterogeneity continued to be a more optimal approach in areas outside of high performance computing, especially in consumer electronics, initially for "tethered" systems in the home, before the explosive growth of the smartphone in the late twenty noughties. The SoCs in today's smartphones are some of the most diversely heterogeneous systems ever designed.

Heterogeneous computing first took off in HPC in 2006, when Tsubame 1.0 appeared in the top 10 of the Top500 supercomputer list, using the precursor to the modern GPU - ClearSpeed's CSX accelerators. Tsubame had a 2-year lead before, in 2008, other accelerated supercomputers started to appear in the Top500 using GPUs.

Heterogeneous architectures, which in HPC today largely combine CPUs and GPUs, are being adopted especially for the largest supercomputers, because of their benefits in terms of energy efficiency and higher peak performance for memory bandwidth and floating-point computation. However, heterogeneous (CPU+GPU) architectures are more complicated to program than homogeneous (CPU only) ones, so they do come with big implications for software development costs and programmer productivity. No single heterogeneous programming model has been agreed and championed by all the main heterogeneous systems vendors, which has been a major impediment to adoption in the weider community, and a drag on the porting of scientific codes to accelerated supercomputers.

![alt text]({{site.url}}/assets/Chameon-ST40.jpg "An Inmos/STMicro Chameleon ST40 from 1996"){:width="50%"} 


In the talk Simon showed some rare pictures of early heterogeneous systems, including an Inmos/STMicro Chameleon digital set top box CPU from 1996 (dual core, 64-bit, with on-chip accelerators for video and audio decode, amongst others), and a PixelFusion F150 GPU from 1999, the world's first fully-programmable GPU, which used 1,536 SIMD processors to deliver leading performance for professional graphics.

![alt text]({{site.url}}/assets/F150-GPU.jpg "A PixelFusion F150 GPU from 1999"){:width="75%"} 

The talk concluded with some reflections on how heterogeneous computing is here for the long term, how there's been progress in how these systems can be programmed, but there's still a long way to go in this respect. It also acknowledged that there's a valuable and critically important "long tail" of codes which may never port to GPUs, and that these users and codes also need to be embraced and supported.

You can view the slides from the keynote [here]({{site.url}}/assets/CIUK_McIntosh-Smith_Dec_2021.pdf).



Simon McIntosh-Smith, Professor of High Performance Computing, Head of the HPC Research Group, University of Bristol. Follow @simonmcs on Twitter for more news from the HPC research group in Bristol.

