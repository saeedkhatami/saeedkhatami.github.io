---
layout: project
type: project
image: img/krew/krew.png
title: "krew"
date: 2023
published: true
labels:
  - C
  - GitHub
summary: "Kernel Read end(and) Write"
---

<img class="img-fluid" src="../img/krew/krewhead.png" alt="os-sim" />

## Kernel Read end(and) Write

a more stable & secure read/write virtual memory for kernel mode drivers

intended to be called using Kernel Function hooks, but could be fitted to be used with **IOCTL**'s

these method's are slightly more secure compared to paracorded's methods (links in driver.c) and should be faster then **MmCopyVirtualMemory**

created with the purpose of removing **PAGE_FAULT_IN_NONPAGED_AREA** bluescreen, and any other **BSOD**'s that come with copying bad memory

Source: <a href="https://github.com/saeedkhatami/MultiThread">saeedkhatami/MultiThread</a>
