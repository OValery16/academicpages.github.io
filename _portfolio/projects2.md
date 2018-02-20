---
title: "TransferCL: an open framework for transfer learning on mobile device "
excerpt: "TransferCL is an open source deep learning framework which has been designed to run on mobile devices. All my code can be downloaded on my [Github](https://github.com/OValery16/TransferCL)<br/><img src='/images/transfercl.jpg'>"
collection: projects
permalink: /projects/p2
---


TransferCL
======== 

Table of Contents
=================

* [1. Why TransferCL ?](#1-why-transfercl-)
* [2. How does it work?](#2-how-does-it-work)
	* [2.1 Transfer Learning](#21-transfer-learning)
* [3. To get in contact](#8-to-get-in-contact)
* [4. Contribute](#9-contribute)



TransferCL is an open source deep learning framework which has been designed to run on mobile devices.  The goal is to enable mobile devices to tackle complex deep learning oriented-problem reserved to desktop computers. This project has been initiated by the parallel and distributed processing laboratory at [National Taiwan University](https://www.ntu.edu.tw).  Olivier Valery develloped this tool during his PhD at National Taiwan University. TransferCL is released under Mozilla Public Licence 2.0.

### 1. Why TransferCL ?

Recent mobile devices are equipped with multiple sensors, which can give insight into the mobile users' profile.  We believe that such information can be used to customize the mobile experience for a specific user.

The primary goal of TransferCL is to leverage Transfer Learning on mobile devices. Our work is based on the [DeepCL Library](https://github.com/hughperkins/DeepCL). Despite their similarities, TransferCL has been designed to run efficiently on a broad range of mobile devices. As a result, TransferCL implements its own memory management system and own OpenCL kernels in order take into account the specificity of mobile devices' System-on-Chip.

### 2. How does it work?

TransferCL is implemented in C++ and is able to run on any Android device with an OpenCL compliant GPU (the vast majority of modern Android devices). TransferCL provides several APIs which allow programmers to transparently leverage deep learning on mobile devices.

#### 2.1 Transfer Learning

Modern mobile devices suffer from two major issues that prevent them from training a deep neural network on mobile devices via a classic supervised learning approach:

* First, the computing capabilities are relatively limited in comparison to servers.
* Then, a single mobile device may not have a sufficient label data in its training data set to train a deep neural network accurately.

![file architecture](/images/traditional_ml_setup.png?raw=true)

Transfer learning is a technique that shortcuts a lot of this work by taking a fully-trained model for a set of categories like ImageNet and retraining from the existing weights for new classes.  The use of pre-trained features is currently the most straightforward and most commonly way to perform transfer learning, but it is not the only one.

![file architecture](/images/transfer_learning_setup.png?raw=true)

For more information, please check these websites:
* [Transfer Learning with TensorFlow](https://www.tensorflow.org/tutorials/image_retraining)
* [Transfer Learning with CNTK](https://docs.microsoft.com/en-us/cognitive-toolkit/Build-your-own-image-classifier-using-Transfer-Learning)
* [A survey of existing Transfer Learning techniques](http://ruder.io/transfer-learning/index.html)
* [The class Convolutional Neural Networks for Visual Recognition at Stanford ](http://cs231n.github.io/transfer-learning/)
* [A paper study of transfer learning performance](https://arxiv.org/abs/1411.1792)


## 3. To get in contact

Just create issues (in GitHub) in the top right of this page. Don't worry about whether you think your issue sounds unimportant or trivial. The more feedback we can get, the better!

## 4. Contribute

If you are interestered in this project, feel free to contact me.




