---
layout: post
title:  "Application Level Memory Ballooning"
date:   2021-08-12 14:46:00 +0530
categories: jekyll update
---

# Overview

Quoting from Wikipedia Memory Ballooning is a technique used to eliminate the need to overprovision host memory used by a virtual machine. Typically there is a ballooning driver in guest os which allocated unused guest memory which ensures that these allocated pages are not being used by any other process. Now, host can deallocate corresponding host pages.

As shown in the following figure an application registers itself to the kernel if it is interested in receiving the SIGBALLOON signal in the event of memory pressure. So, the kernel sends the SIGBALLOON signal to the registered application whenever the amount of free memory falls below the specified threshold. Also, there is a ballooning driver in an application which acts by sending the victim pages to the kernel whenever it receives the SIGBALLOON signal.

![image demonstrating the application level memory ballooning](/pictures/image_01.png)

# Implementation

To be added soon...