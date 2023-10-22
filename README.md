# TWRP device tree for Samsung Galaxy A13 (SM-A135x)

## Kernel Source 
Available at [here](https://github.com/VThang51/android_kernel_samsung_a13xx)

## Platform Source
Available at [here](https://github.com/VThang51/android_platform_samsung_a13)

## How To Build
1. Create a working directory at `~`
```bash
mkdir ~/TWRP && cd ~/TWRP
```
2. Initialize your local repository using AOSP tree to build TWRP
```bash
repo init -u https://github.com/minimal-manifest-twrp/platform_manifest_twrp_aosp.git -b twrp-12.1
```
Or a more space-saving solution
```bash
repo init --depth=1 -u https://github.com/minimal-manifest-twrp/platform_manifest_twrp_aosp.git -b twrp-12.1
```
3. Sync up
```bash
repo sync
```
4. Clone the device tree
```bash
git clone -b twrp-12.1_v1 https://github.com/VThang51/android_device_samsung_a13.git device/samsung/a13
```
5. Build it
```bash
cd ~/TWRP && export ALLOW_MISSING_DEPENDENCIES=true && . build/envsetup.sh && lunch twrp_a13-eng && mka recoveryimage
```
## What was active in this TWRP device tree?
- A: Active
- P: Partially Active
```bash
Blocking checks
- [A] Correct screen/recovery size
- [P] Working Touch, screen
- [P] Backup to internal/microSD
- [P] Restore from internal/microSD
- [A] reboot to system
- [P] ADB

Medium checks
- [ ] update.zip sideload
- [ ] UI colors (red/blue inversions)
- [P] Screen goes off and on
- [P] F2FS/EXT4 Support, exFAT/NTFS where supported
- [A] all important partitions listed in mount/backup lists
- [ ] backup/restore to/from external (USB-OTG) storage (not supported by the device)
- [ ] backup/restore to/from adb (https://gerrit.omnirom.org/#/c/15943/)
- [ ] decrypt /data
- [ ] Correct date

Minor checks
- [ ] MTP export
- [A] reboot to bootloader
- [A] reboot to recovery
- [A] poweroff
- [P] battery level
- [A] temperature
- [A] encrypted backups
- [A] input devices via USB (USB-OTG) - [A] keyboard, mouse and disks (not supported by the device)
- [P] USB mass storage export
- [A] set brightness
- [A] vibrate
- [A] screenshot
- [ ] partition SD card
```
