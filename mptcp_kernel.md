---
layout: post
title: Build and flash the MPTCP kernel
---

This section will guide you through build and deployment process of the MPTCP kernel.

Start with cloning the Linux kernel and ARM cross compilation toolchain from Github:

```
git clone https://github.com/gdetal/mptcp_nexus5.git
git clone https://github.com/yinquan529/platform-prebuilts-gcc-linux-x86-arm-arm-eabi-4.7.git
```

Now you are ready to build the kernel. First, set some environment variables and make the default config. Then you are ready to go:

```
cd mptcp_nexus5
export ARCH=arm SUBARCH=arm CROSS_COMPILE=../platform-prebuilts-gcc-linux-x86-arm-arm-eabi-4.7/bin/arm-eabi-
make hammerhead_defconfig
make -j8
```

**Note:** If you are using are more recent version of perl, you may encounter the following error:

```
Can't use 'defined(@array)' (Maybe you should just omit the defined()?) at kernel/timeconst.pl line 373.
```

If this happens, you have remove the `if`-statement in line `373` in the file `kerneö/timeconst.pl`.

This will take a while, just be patient.

After the compilation is done, you have to make a bootable image:

```
abootimg -x <PATH_TO_ANDROID_FACTORY_IMG>/boot.img
sed -i 1d bootimg.cfg
abootimg --create mptcp_boot.img -f bootimg.cfg -k arch/arm/boot/zImage-dtb -r initrd.img
```

The final step, boot the created image:

```
adb reboot bootloader
sudo fastboot boot -c "console=ttyHSL0,115200,n8 androidboot.hardware=hammerhead user_debug=31 maxcpus=2 msm_watchdog_v2.enable=1" mptcp_boot.img
```

That's it. You have build and deployed a MPTCP kernel for Android. Please note, that **the change is only in-memory. After rebooting, the stock kernel will be used again and you have to reboot the MPTCP kernel**. Proceed with the [next step of the instructions.](video_stream)
