# android_device_xiaomi_raphael
For building TWRP for Xiaomi Redmi K20 / Mi 9T

TWRP device tree for Xiaomi Redmi K20 / Mi 9T

## Features

Works:

- ADB
- Screen brightness settings
- Correct screenshot color
- MTP
- Flashing (opengapps, roms, images and so on)
- Backup/Restore (Needs more testing)
- USB OTG
- Android R Support
- Vibration support

To-do:

- Decryption of /data (policy V2)

## Compile

First checkout minimal twrp with omnirom tree:

```
repo init -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_omni.git -b twrp-9.0
repo sync
```

Then add these projects to .repo/manifest.xml:

```xml
<project path="device/xiaomi/raphael" name="mauronofrio/android_device_xiaomi_raphael" remote="github" revision="android-9.0" />
```

Finally execute these:

```
. build/envsetup.sh
lunch omni_raphael-eng
mka recoveryimage ALLOW_MISSING_DEPENDENCIES=true # Only if you use minimal twrp tree.
```

To test it:

```
fastboot boot out/target/product/raphael/recovery.img
```

## Other Sources
LineageOS kernel

## Thanks
@mauronofrio
