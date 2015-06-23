chipsee_kernel3.14_support
==========================

Contains Files required to Boot beaglebone black with chipsee 7 inch capacitive LCD with Yocto daisy bsp

By Default yocto beaglebone black daisy bsp doesn't support Booting BBB with Chipsee 7 inch LCD.
Moreover Chipsee comapny doen't give binaries supporting Linux kernel 3.14.

For booting BBB and Chipsee LCD booting following steps are required.
1. Download Yocto daisy and build it for beaglebone black.
2. Replace dtb in directory /yocto/poky/build/tmp/work/beaglebone-poky-linux-gnueabi/linux-yocto/3.14+gitAUTOINC+09424cee64_0143c6ebb4-r0/linux/arch/arm/boot/dts
with one provided in this repo.
3. Build dtb using command "bitbake -f -c install virtual/kernel"
4. copy dtb in the microsd card BOOT folder.
5. Extract RFS in the ROOT folder of microsd card.
6. Replace RFS inittab file with one given in this repo.
7. Power up BBB and Chipsee LCD.

Attention!!!! As of today i.e. 14/10/2014 i am not able to see Angstrom UI but i am able to see prompt on serial terminal

This files will be updated as and when i have some progess on making LCD work.

Update:
========
I could bring up the Chipsee LCD by compiling Linux kernel seperately from Robert Nelson's kernel branch i.e. https://github.com/beagleboard/linux

I am yet to create Linux custom kernel recipe for the same but meantime if you want to bring up Chipsee LCD + Yocto + kernel 3.14 follow steps mentioned in answer of stack overflow website.
http://stackoverflow.com/questions/30723261/building-robert-nelsons-linux-kernel-into-yoctodaisy-for-beaglebone-black/30833458#30833458 
