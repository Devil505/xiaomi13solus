# Xiaomi Air 13 with Solus Tutorial

## Installation

Download ISO from [here](https://solus-project.com/download/)

Choose the version you want. Mate seems to be lighter.

Installation is performed properly with UEFI support.

## HARDWARE

### WIFI

Works perfectly !

### BLUETOOTH

I didn't really check.

### KEYBOARD

Backlight works perfectly !

### Display

You can download a ICC profile from this repo.

### NVIDIA & Intel GPU

You can install NVIDIA driver via Solus Hardware Drivers software easily.

Now, how to switch from NVIDIA to Intel to preserve some battery energy ?

You can check the primary GPU with

'linux-driver-management status'

check 'man linux-driver-management' for more details

You must have some thing like:

> ╒ Hardware Platform
> ╞ Platform Vendor : Timi
> ╘ Platform Model  : TM1604>
>
>NVIDIA Optimus
>
> ╒ Primary GPU (iGPU)
> ╞ Device Name   : HD Graphics 620
> ╞ Manufacturer  : Intel Corporation
> ╞ Product ID    : 0x5916
> ╞ Vendor ID     : 0x8086
> ╞ X.Org PCI ID  : PCI:0:2:0
> ╘ Boot VGA      : yes
>
> ╒ Secondary GPU (dGPU)
> ╞ Device Name   : Device 1d12
> ╞ Manufacturer  : NVIDIA Corporation
> ╞ Product ID    : 0x1d12
> ╞ Vendor ID     : 0x10de
> ╞ X.Org PCI ID  : PCI:1:0:0
> ╘ Boot VGA      : no

Other alternative: [systemd NVIDIA}(https://github.com/MarechalLima/Systemd-Nvidia-Entry)

### FINGERPRINT

Xiaomi use a fingerprint from elan tech, this model is not yet supported by libfprint but someone work on it, check [here](https://github.com/iafilatov/libfprint).

I will provide packages soon !

### BATTERY LIFE

Install TLP with 'sudo eopkg it tlp'

Use the tlp configuration file from this repo for '/etc/default/tlp'
