# PBEM00 TWRP — F.29 conservative adapt

Based on AmeChanRain/android_device_oppo_PBEM00 (twrp-10).

Changes:
- Restored BOARD_MKBOOTIMG_ARGS for bootimg header v1
- Platform/security patch props floored for recovery
- Extra FBE/crypto and OPPO-friendly TWRP flags
- Still uses original prebuilt kernel/dtbo (no F.29 stock dump available)

Flash tip if recovery still won't stick:
```
fastboot flash vbmeta --disable-verity --disable-verification vbmeta.img
fastboot flash recovery recovery.img
fastboot reboot recovery
```
