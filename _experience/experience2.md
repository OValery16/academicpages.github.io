---
title: "Talk 1 on Relevant Topic in Your Field"
collection: experience
type: "Experience"
permalink: /experience/experience2
venue: "UC San Francisco, Department of Testing"
date: 2017-03-01
location: "fresdt4era"
---

from July 2011, I did a 7 months internship in ITRI (in taiwan), in the Cloud Computing center for Mobile Application department. For 7 months, I had worked on Cloud OS, in the Physical Resource Management team. I have had several objectives:
- My first task was to provide to the end-user a flexible node installation : as you know, the installation process is based on the Kickstart Installation, created by Red Hat. In our case, we would like to provide the end users the capability to easily configure this installation. For that, we need to be able to generate all boot configuration files (the tftp boot files, the kickstart files, the prescript files, the postscript files) in a dynamic way. So my task was to create several Python programs that can generate these files according to some parameters.
- My second task was very interesting. Currently, the deployment is made in unicast. So in the case of the deployment of one hundred nodes, the deployment time would be very long. So, my task was to study and find several solutions to install one hundred nodes without spending too much time, using the smallest bandwith as possible, and at the same time provide the user a flexible installation (he can choose what he want to install). Moreover, the user should be able to monitor the deployment. After several tests (speed, bandwith ...), the solution that I proposed to Willy is based on a tool called SystemImager, that is a program for system cloning : I made some scripts to create a image from scratch (chroot jail), and I used SystemImager to deploy it on all targets. With the solutions that I proposed, it is possible to use several different images to deploy at the same time. Moreover, I tested several solutions with different transport protocols (rsync, multicast, BitTorrent).
- My third task was to a find a solution to provide a disk less booting for the Compute nodes, according to some requirements.
