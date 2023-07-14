# TWRP device tree for Samsung Galaxy A13 aka a13

## Kernel source 
Available at [here](https://github.com/VThang51/android_kernel_samsung_a13xx)

## How to build
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
git clone -b TWRP https://github.com/VThang51/android_device_samsung_a13.git device/samsung/a13
```
5. Build it
```bash
cd ~/TWRP && export ALLOW_MISSING_DEPENDENCIES=true && . build/envsetup.sh && lunch twrp_a13-eng && mka recoveryimage
```
