---
layout: project
type: project
image: img/acer-sense/dark.png
title: "Acer SenSe"
date: 2022
published: true
labels:
  - C
  - Shell
  - Python
  - Makefile
  - GitHub
summary: "Linux kernel module to support Turbo mode and RGB Keyboard for Acer Predator and Nitro notebook series"
---

<img class="img-fluid" src="../img/acer-sense/keyboard.webp" alt="keyboard" />

Unofficial Acer Gaming RGB keyboard backlight and Turbo mode Linux kernel module (Acer Predator, Acer Helios, Acer Nitro)

**Will this work on my laptop?**

Compablity table:

| Product name |                                          Turbo Mode (Implemented)                                           |                                             Turbo Mode (Tested)                                             | RGB (Impelmented) | RGB (Tested) |
|--------------|:-----------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|:-----------------:|:------------:|
| AN515-45     |                                                      -                                                      |                                                      -                                                      |        Yes        |     Yes      |
| AN515-55     |                                                      -                                                      |                                                      -                                                      |        Yes        |     Yes      |
| AN515-56     |                                                      -                                                      |                                                      -                                                      |        Yes        |     Yes      |
| AN515-57     |                                                      -                                                      |                                                      -                                                      |        Yes        |     Yes      |
| AN515-58     |                                                      -                                                      |                                                      -                                                      |        Yes        |     Yes      |
| AN517-41     |                                                      -                                                      |                                                      -                                                      |        Yes        |     Yes      |
| PH315-52     |                                                     Yes                                                     |                                                     Yes                                                     |        Yes        |     Yes      |
| PH315-53     |                                                     Yes                                                     |                                                     Yes                                                     |        Yes        |     Yes      |
| PH315-54     |                                                     Yes                                                     |                                                     Yes                                                     |        Yes        |     Yes      |
| PH315-55     |                                                     Yes                                                     |                                                     [Buggy](https://github.com/JafarAkhondali/acer-predator-turbo-and-rgb-keyboard-linux-module/issues/122)                                                      |        Yes        |     No      |
| PH317-53     |                                                     Yes                                                     |                                                     Yes                                                     |        Yes        |     Yes      |
| PH317-54     |                                                     Yes                                                     |                                                     No                                                      |        Yes        |      No      |
| PH517-51     |                                                     Yes                                                     |                                                     No                                                      |        Yes        |      No      |
| PH517-52     |                                                     Yes                                                     |                                                     No                                                      |        Yes        |      No      |
| PH517-61     | [Partial#94](https://github.com/JafarAkhondali/acer-predator-turbo-and-rgb-keyboard-linux-module/issues/94) | [Partial#94](https://github.com/JafarAkhondali/acer-predator-turbo-and-rgb-keyboard-linux-module/issues/94) |        Yes        |     Yes      |
| PH717-71     |                                                     Yes                                                     |                                                     No                                                      |        Yes        |      No      |
| PH717-72     |                                                     Yes                                                     |                                                     No                                                      |        Yes        |      No      |
| PT314-51     |                                                     No                                                      |                                                     No                                                      |        Yes        |     Yes      |
| PT315-51     |                                                     Yes                                                     |                                                     Yes                                                     |        Yes        |     Yes      |
| PT314-52S     |                                                     Yes                                                     |                                                     Yes                                                     |        Yes        |      No      |
| PT315-52     |                                                     Yes                                                     |                                                     No                                                      |        Yes        |      No      |
| PT515-51     |                                                     Yes                                                     |                                                     Yes                                                     |        Yes        |     Yes      |
| PT515-52     |                                                     Yes                                                     |                                                     No                                                      |        Yes        |      No      |
| PT516-52s    |                                                     Yes                                                     |                                                     No                                                      |        Yes        |     Yes      |
| PT917-71     |                                                     Yes                                                     |                                                     No                                                      |        Yes        |      No      |

---

Source: <a href="https://github.com/saeedkhatami/Acer-SenSe"><i class="large github icon "></i>saeedkhatami/Acer-SenSe</a>
