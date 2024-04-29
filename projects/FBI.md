---
layout: project
type: project
image: img/fbi/fbi.png
title: "FBI"
date: 2024
published: true
labels:
  - C
  - Visual Studio
  - C#
  - GitHub
summary: "Force Bind IP GUI WPF, reinventing Force Bind IP"
---

<img class="img-fluid" src="../img/fbi/fbi.png"/>

## FBI (Force Bind IP)

- based on [r1ch](https://r1ch.net/projects/forcebindip)'s Force Bind IP (Closed Source)

## Overview

ForceBindIP is a Windows application that will inject itself into another application and alter how certain Windows socket calls are made, allowing you to force the other application to use a specific network interface / IP address. This is useful if you are in an environment with multiple interfaces and your application has no option to bind to a specific interface.

## How It Works

ForceBindIP works in two stages - the loader, ForceBindIP.exe will load the target application in a suspended state. It will then inject a DLL (BindIP.dll) which loads WS2_32.DLL into memory and intercepts the bind(), connect(), sendto(), WSAConnect() and WSASendTo() functions, redirecting them to code in the DLL which verifies which interface they will be bound to and if not the one specified, (re)binds the socket. Once the function intercepts are complete, the target application is resumed. Note that some applications with anti-debugger / injection techniques may not work correctly when an injected DLL is present; for the vast majority of applications though this technique should work fine.

## Usage

1. **Set Interface Priority**: Prioritize the desired network interface for downloading by adjusting its priority settings manually in the Windows Network Connections settings. Assign a higher priority to the interface you wish to use for downloading and a lower priority to others.

2. **Launch Application**: Close any running download applications and initiate them as usual. FBI does not modify network interface priorities automatically; it relies on the user's manual configuration.

3. **Enjoy Concurrent Activities**: With FBI, users can download files while simultaneously engaging in other network-dependent activities like streaming without experiencing network conflicts.

### Note

FBI does not automatically change network interface priorities. Users are responsible for adjusting the priorities manually in their Windows Network Connections settings. Please refer to your operating system documentation for instructions on how to adjust network interface priorities.

## Installation

1. Visit the [Releases](https://github.com/saeedkhatami/FBI/releases) page of the FBI repository.
2. Download the latest version of FBI.
3. Extract the downloaded ZIP file.
4. Run the FBI

## Compatibility

FBI is compatible with Windows operating systems.

## Contribution

Contributions to FBI are welcome! Feel free to fork the repository, make improvements, and submit pull requests.


## Disclaimer

FBI is provided as-is without any warranties. Use it at your own risk.

---

Source: <a href="https://github.com/saeedkhatami/AESIC"><i class="large github icon "></i>saeedkhatami/AESIC</a>
