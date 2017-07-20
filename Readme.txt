

Download:
=========
If you are not already using an AOSP toolchain (included in an AOSP build tree), download the corresponding official android toolchain for the arm-eabi specified above for this device:
        
git clone https://android.googlesource.com/platform/prebuilt  for 4.4.3
git clone https://android.googlesource.com/platform/prebuilts/gcc/linux-x86/arm/arm-eabi-4.6  for 4.6 
git clone https://android.googlesource.com/platform/prebuilts/gcc/darwin-x86/arm/arm-eabi-4.7 for 4.7
(use darwin-x86 in place of linux-x86 for mac)

Build the kernel:
=================
set the following environment variables:

source ./build/envsetup.sh
lunch l9010_blu-user

build kernel:
make kernel -j8


Output Binary Files:
====================
After the build process is finished, there should be a file boot.img

If you have already built and installed a boot.img with root access you can also fastboot boot.img into the device using:
adb reboot bootloader 
fastboot flash boot out/target/product/l9010_blu/boot.img
fastboot reboot

For additional information:
=========================== 
http://htcdev.com
