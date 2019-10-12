---
layout: post
title: Install Stock Android 4.4.2 with Root Permissions
---

This section will guide you through the Android 4.4.2 installation process.

# Download the Factory Image

First of all, you need the Android 4.4.2 factory image, which can be downloaded [directly from Google](https://dl.google.com/dl/android/aosp/hammerhead-kot49h-factory-3c5d358b.zip). Unzip the downloaded file and execute the following commands:

```
adb reboot bootloader
sudo ./flash-all.sh
```

This takes a while. After Android is booted up, you have to configure it (set language, etc.).
Of course, we need root. Again, pretty simple. Just copy SuperSU to the SD card of the device, flash twrp and install SuperSU. But before that, you have to enable developer settings.
On the phone, go to **Settings -> About phone -> Tap 7x on Build number**. Then, go to **Settings -> Developer options -> enable USB debugging**.
After that, download [SuperSU](https://supersuzip.com/download/SuperSU-v2.82-201705271822.zip) and the [TWRP image](https://dl.twrp.me/hammerhead/twrp-3.2.2-0-hammerhead.img).

When done, run the following commands (replace the names of SuperSU.zip and twrp.img with the downloaded ones):

```
adb push SuperSU.zip /sdcard/supersu.zip
adb reboot bootloader
sudo fastboot flash recovery twrp.img
```

After the flashing is done, select **Boot Revovery** from the booloader menu.
In TWRP, select **install ZIP**, select the **supersu.zip** and follow the on-screen instructions.
After successful flash, boot into Android.

That's it. You have now the a rooted stock Android 4.4.2. You can continue with the [next part of the instructions.](mptcp_kernel)
