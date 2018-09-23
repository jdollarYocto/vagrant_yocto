Using for anotes storage for the moment. TODO: Update to repo specific instructions

NOTES

yocto raspberry-pi-board set to value from https://meta-raspberrypi.readthedocs.io/en/latest/layer-contents.html
have to set poky/bitbake/bin to path


After vagrant provision login and navigate to `~/poky/rpi-build`. That is where the generating of the raspberry pi will take place.
from there it should be setup to run `bitbake core-image-base` to generate the sd image

Vagrant needs more ram than what the default value is

set ENABLE_UART = "1" on local.conf
may have performance impact on various raspberry pis

add layers - Add using bitbake-layers or update vagrant template and reprovision
rootfs directory with script to copy everything over to expected directory

Add network information to the local.conf file
copy local and bblayer config over to conf in build folder

example patch generation for bbappends: diff -c a/interfaces b/interfaces > interfaces.patch
