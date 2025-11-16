# ✨ TwOS Core Prototype v0.1 (gts4lvwifi)

Hello! I am Azeno42, and this repository represents the initial phase of TwOS, a custom Android 14 core project for the Samsung Galaxy Tab S5e (gts4lvwifi).

TwOS is being developed based on the stable, high-performance LineageOS (Android). The V0.1 prototype is currently focusing on achieving a pure Pixel experience combined with enhanced performance.

## 🚀 Project Goals for v1.0

The core philosophy of this prototype is simplicity, speed, and a clean Google experience on the Tab S5e.

- **Pixel Experience:** Full integration of Google services and applications, including Google Camera 9.6, to provide the stock Google Pixel user interface and features.

- **Enhanced Performance:** Removing unnecessary, non-core features from the base LineageOS source (Debloating).

- **Stable Core:** Built on the robust foundation of LineageOS 22.0 (Android 15).

## 🛠️ Build Instructions

This repository requires a standard LineageOS build environment.


## STEP 1: Initialize the Source Tree (LineageOS Manifest)

We will use the official LineageOS 22.2 manifest (Android 15) for the base of our build.

### Create a root directory for your build
> mkdir ~/twos_local_build
> cd ~/twos_local_build

### Initialize the LineageOS repository for the lineage-22.2 branch
> repo init -u [https://github.com/LineageOS/android.git](https://github.com/LineageOS/android.git) -b lineage-22.2


## STEP 2: Implement the TwOS Local Manifest (Overlay)

This is the critical step where we instruct the build system to replace the default LineageOS recovery with your custom TwOS recovery code from this repository.

### Create the Local Manifest Directory:

> mkdir -p .repo/local_manifests


Download the TwOS Manifest File:
We download the twos.xml file, which specifies your custom code paths.

### Downloads your custom manifest and names it 'twos.xml'
> wget [https://raw.githubusercontent.com/Azeno42/TwOS_Core-gts4lvwifi/main/twos.xml](https://raw.githubusercontent.com/Azeno42/TwOS_Core-gts4lvwifi/main/twos.xml) -O .repo/local_manifests/twos.xml


Verify the Manifest Content (Optional):
Ensure the twos.xml file correctly references your repository:

<?xml version="1.0" encoding="UTF-8"?>
<manifest>
  <remote name="twos_remote"
          fetch="[https://github.com/Azeno42/](https://github.com/Azeno42/)"
          revision="main" />
  <project path="bootable/recovery" 
           name="TwOS_Core-gts4lvwifi" 
           remote="twos_remote" />
</manifest>


## STEP 3: Synchronize the Codebase (repo sync)

This command downloads all necessary files from LineageOS AND automatically clones your recovery code into bootable/recovery.

### This will take a while. The -j flag uses all available cores for speed.
> repo sync -j$(nproc --all)

> [!TIP]
> If you get error, simply use
> repo sync


## STEP 4: Extract Proprietary Files (Blobs)

You must now extract the proprietary vendor files (blobs) from your device (SM-T720 running LineageOS 22.2) using ADB.

**Connect Device:** Connect the Tab S5e to your computer and ensure USB Debugging is enabled.

**Verify ADB Connection:** adb devices should show your device.

**Run Extraction Script:**

> source build/envsetup.sh
> breakfast gts4lvwifi
> 
### This script will extract files from the connected device
> ./device/samsung/gts4lvwifi/extract-files.py


## STEP 5: Build TwOS Core!

The final step: compiling your custom ROM.

**Set up the Environment (if not done in Step 4):**

> source build/envsetup.sh


**Select the Device (gts4lvwifi):**

> breakfast gts4lvwifi


**Start the Compilation:**
Use the brunch command.

**Start the build process**
> brunch gts4lvwifi

**Optional: Log the process (recommended for debugging)**
> brunch gts4lvwifi 2>&1 | tee twos_core_build_log.txt


## 🎉 Completion

Your final zip file (e.g., TwOS_Core-gts4lvwifi-v0.1-unsigned.zip) will be located in the out/target/product/gts4lvwifi/ directory upon successful compilation. Good luck with the flash!


⚖️ Licensing

The core Android/LineageOS code base for this project is licensed under the Apache License 2.0.

> [!WARNING]
> This project is currently focused only on the Samsung Galaxy Tab S5e. While the core foundation is open-source (Apache 2.0), any unique modifications and optimizations made by Azeno42 may be kept closed-source to protect the integrity and vision of the TwOS project. See the 

$$LICENSE.md$$

 file for details.

TwOS Core Prototype. Copyright 2025. Developed by Azeno42 (Muratcan Yücepur).
