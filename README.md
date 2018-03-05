# Xiaomi Air 13 (2017) with Solus Tutorial

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

You can use my ICC profile provided.

### NVIDIA & Intel GPU

Linux Driver Management from Solus doesn't supporter (yet) the Optimus (possibility to switch easily to GPU we want)

There is alternative via [this script](https://github.com/MarechalLima/Solus-Optimus-Switch).

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
