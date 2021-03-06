# Kali NetHunter Installer

The NetHunter Installer is basically just a zip file generated by build.py from the folder layout contained here.
Follow the instructions below to create the installer zip.
All you have to do is flash it through TWRP for a complete Kali NetHunter environment and chroot on your device.

The boot image patching script is loosely based on AnyKernel2 by osm0sis.

## Instructions

### Preparing the environment

Before building, you will need to initialize the devices repository.  
As NetHunter devices have an immense binary history, you will probably want to use a shallow clone. (--depth 1)  
To do this, run the command:
```sh
./bootstrap.sh
```

### Build command examples

Example building for the Nexus 5 (hammerhead):
```sh
python build.py -d hammerhead --marshmallow
```
Building the kernel only (useful for testing if kernel works):
```sh
python build.py -d hammerhead --marshmallow -k
```
Building without the kernel (useful for just updating apps):
```sh
python build.py -d hammerhead --marshmallow -nk
```
Building with adding a full chroot (add kalifs-full.tar.xz to rootfs/[arch]/kalifs-full.tar.xz):
```sh
python build.py -d hammerhead --marshmallow --rootfs full
```
Create a release version:
```sh
python build.py -d hammerhead --marshmallow --rootfs full --release v3.0
```
Force download all third party apps:
```sh
python build.py --forcedown
```
Building the uninstaller:
```sh
python build.py --uninstaller
```
Show help:
```bash
python build.py -h
```

## How to add a new/unsupported device

See the README.md located in the NetHunter Devices repository:  
https://github.com/offensive-security/nethunter-devices

## Device changelog

You can view changes in the commit log of the NetHunter Devices repository:  
https://github.com/offensive-security/nethunter-devices/commits

Sat Jul 30 20:09:18 EST 2016
