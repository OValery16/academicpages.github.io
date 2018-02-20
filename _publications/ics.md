---
title: "Adaptive OpenCL Computation Offloading Framework on Mobile Device"
collection: publications
permalink: /publications/ics2014
excerpt: 'This paper presents the design and the implementation of an adaptive computation offloading framework based on OpenCL. This system can transparently offload OpenCL workloads from mobile devices to an available OpenCL compatible device.'
date: 2014-12-15
venue: 'ICS 2014: International Computer Symposium'
citation: 'Olivier Valery, Wei-Shu Hung, Ju-Cheng Chou, Pangfeng Liu, and Jan-Jan Wu'
---

<h2>Abstract:</h2>

The rapid development of mobile technology and the emergence of cloud resources have freed the mobile user from the constraints due to the limited resources of their device.  Since a decade ago, many efforts have been done in order to take advantage of these resources-rich cloud.  One common approach is to offload computation from mobile devices to resourceful servers.  Recently GPUs also have received a lot of attention from the scientific community.  GPU is highly optimized for throughput and can be used to accelerate different types of applications.

This paper presents the design and the implementation of an adaptive computation offloading framework based on OpenCL.  This system can transparently offload OpenCL workloads from mobile devices to an available OpenCL compatible device.  In addition the system is able to decide if a certain workload needs to be offloaded and to which devices.  This adaptive method takes into account the network transfer speed and the intrinsic characteristics of the kernel that impacts on its execution time.  Our evaluation shows our system can adapt to several different environments and can achieve as much as 50.3X execution speed compared to the local execution.

