# ✨ TwOS Core Prototype v0.1 (gts4lvwifi)

Hello! I am Azeno42, and this repository represents the initial phase of TwOS, a custom Android 14 core project for the Samsung Galaxy Tab S5e (gts4lvwifi).

TwOS is being developed based on the stable, high-performance LineageOS (Android). The V0.1 prototype is currently focusing on achieving a pure Pixel experience combined with enhanced performance.

## 🚀 Project Goals for v1.0

The core philosophy of this prototype is simplicity, speed, and a clean Google experience on the Tab S5e.

Pixel Experience: Full integration of Google services and applications, including Google Camera 9.6, to provide the stock Google Pixel user interface and features.

Enhanced Performance: Removing unnecessary, non-core features from the base LineageOS source (Debloating).

Stable Core: Built on the robust foundation of LineageOS 21.0 (Android 14).

## 🛠️ Build Instructions

This repository requires a standard LineageOS build environment.

**1. Set up the Environment**

Ensure all packages required for LineageOS building (OpenJDK, Python, etc.) are installed.

**2. Download the Source Code**

### Get the Repo tool
> mkdir -p ~/twos_local_build
> cd ~/twos_local_build/

### Download the TwOS manifest
> repo init -u [Not Avaible] -b lineage-22.2 

### Synchronize the code (This will take several hours depending on your internet speed)
> repo sync

**3. Start the Build**

**Set up the environment**
> ./build/envsetup.sh

**Select the device (E.g.: gts4lvwifi)**
> breakfast gts4lvwifi

**Build TwOS**
> brunch gts4lvwifi




⚖️ Licensing

The core Android/LineageOS code base for this project is licensed under the Apache License 2.0.

IMPORTANT NOTE:

This project is currently focused only on the Samsung Galaxy Tab S5e. While the core foundation is open-source (Apache 2.0), any unique modifications and optimizations made by Azeno42 may be kept closed-source to protect the integrity and vision of the TwOS project. See the 

$$LICENSE.md$$

 file for details.

TwOS Core Prototype. Copyright 2025. Developed by Azeno42 (Muratcan Yücepur).
