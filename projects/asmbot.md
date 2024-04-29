---
layout: project
type: project
image: img/asmbot/asmbot.jpg
title: "ASMbot"
date: 2024
published: true
labels:
  - C++
  - Assembly
  - CMake
  - C
summary: "A game which inspired by Much Assembly Required "
---

<img class="img-fluid" src="../img/asmbot/asmbot.jpg"/>

## ASMBots

[Much Assembly Required](https://github.com/simon987/Much-Assembly-Required)

Just an assembler and emulator for my custom 8086-like BOT.

## Waht is going on

You have a robot that spawns in a world with resources in it. You can control it manually, or you can program it in assembly to do your bidding for you. You can make more robots, and program them too. Soon enough, you'll have an army of robots that program themselves.

### How to

install:

```bash
sudo apt install build-essential libsdl2-dev libsdl2-2.0 cmake
```

configure project

```bash
cmake --no-warn-unused-cli -DCMAKE_BUILD_TYPE:STRING=Debug -DCMAKE_EXPORT_COMPILE_COMMANDS:BOOL=TRUE -DCMAKE_C_COMPILER:FILEPATH=/usr/bin/gcc -DCMAKE_CXX_COMPILER:FILEPATH=/usr/bin/g++ -S<PROJECT_DIR> -B<BUILD_DIR> -G "Unix Makefiles"
```

build:

```bash
cmake --build <BUILD_DIR> --config Debug --target all -j 4
```

usage:

```bash
ASMBot file.asm
```

---

Source: <a href="https://github.com/saeedkhatami/ASMBot"><i class="large github icon "></i>saeedkhatami/ASMBot</a>
