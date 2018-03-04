# Xiaomi Air 13 with Solus Tutorial

## Installation

Download ISO from [here](https://solus-project.com/download/)

Choose the version you want. Mate seems to be lighter.

Installation is performed properly with UEFI support.

## HARDWARE

### WIFI

Works perfectly !

### SOUND

Works perfectly !

### BLUETOOTH

I didn't really check.

### KEYBOARD

Backlight works perfectly !

### DISPLAY

You can download a ICC profile from this repo. (WORK IN PROGRESS)

### NVIDIA & Intel GPU

You can install NVIDIA driver via Solus Hardware Drivers software easily.

Now, how to switch from NVIDIA to Intel to preserve some battery energy ?

You can check the primary GPU with

`linux-driver-management status`

check `man linux-driver-management` for more details

You must have some thing like:

```
 ╒ Hardware Platform
 ╞ Platform Vendor : Timi
 ╘ Platform Model  : TM1604>

NVIDIA Optimus

 ╒ Primary GPU (iGPU)
 ╞ Device Name   : HD Graphics 620
 ╞ Manufacturer  : Intel Corporation
 ╞ Product ID    : 0x5916
 ╞ Vendor ID     : 0x8086
 ╞ X.Org PCI ID  : PCI:0:2:0
 ╘ Boot VGA      : yes

 ╒ Secondary GPU (dGPU)
 ╞ Device Name   : Device 1d12
 ╞ Manufacturer  : NVIDIA Corporation
 ╞ Product ID    : 0x1d12
 ╞ Vendor ID     : 0x10de
 ╞ X.Org PCI ID  : PCI:1:0:0
 ╘ Boot VGA      : no
```

Other alternative: [systemd NVIDIA](https://github.com/MarechalLima/Systemd-Nvidia-Entry)

### FINGERPRINT

Xiaomi use a fingerprint from elan tech, this model is not yet supported by libfprint but someone work on it, check [here](https://github.com/iafilatov/libfprint).

Install the packages libfprint, fprint_demo and fprintd from this repo.

Try `sudo fprint_demo` to test the fingerprint

You can also do it via fpintd with `frpintd-enroll` and `fprintd-verify`

**NOT FULLY OPERATIONAL** check also this [link](https://bugs.launchpad.net/ubuntu/+source/libfprint/+bug/1641290)

### BATTERY LIFE

Install TLP with `sudo eopkg it tlp`

`sudo tlp start`
`sudo tlp-stat | grep "TLP power save"`

You should got:

`TLP power save = enabled`

Add TLP for every boot:

`sudo systemctl enable tlp`

Use the tlp configuration file for your conf file: `/etc/default/tlp`
