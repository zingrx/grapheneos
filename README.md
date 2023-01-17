Guide for unofficial GrapheneOS builds 
=========================================

**What is GrapheneOS?**

GrapheneOS is the best choice when it comes to privacy and security.

GrapheneOS provides additional security hardening and privacy improvements. It has a hardened memory allocator, network and sensor permissions, and various other security features. For officially supported devices, GrapheneOS also comes with full firmware updates and signed builds, so verified boot is fully supported.

It's the **#1** recommended Android derivative by [**Privacy Guides**](https://www.privacyguides.org/android/#grapheneos).

By default, GrapheneOS is built for Pixel devices only, as per [their statement](https://grapheneos.org/build#build-targets). For unofficial builds, there are some clones and modifications required as listed below.


## Required Clones
---------------

**Vendor:**

```bash
git clone https://github.com/LineageOS/android_vendor_lineage vendor/lineage
```

**Lineage-SDK:**

```bash
git clone https://github.com/LineageOS/android_lineage-sdk/ lineage-sdk
```

**Lineage Interfaces:**

```bash
git clone https://github.com/LineageOS/android_hardware_lineage_interfaces hardware/lineage/interfaces
```

**Livedisplay:**

```bash
git clone https://github.com/LineageOS/android_hardware_lineage_livedisplay hardware/lineage/livedisplay
```

**Telephony:**

```bash
git clone https://github.com/LineageOS/android_vendor_codeaurora_telephony vendor/codeaurora/telephony
```



## Changes to Build system
---------------

**build/soong**

```bash
git fetch https://github.com/LineageOS/android_build_soong
git cherry-pick 8bd9d96f75106184092062af1906e7eb5c6eb23f
```

**build/make/core**

```bash
git fetch https://github.com/zingrx/grapheneos
git cherry-pick 5cfc04f4b7f5d2864cc12aa2888d67698d1f4ba7
git cherry-pick 8446c98c7543412f6986fe530bd5314b3dddc76d
```



## Other changes
---------------

**hardware/qcom-caf/sm8250/display**

```bash
git fetch https://github.com/zingrx/grapheneos
git cherry-pick 2ff99c94e3ffc4b08b988b03663721cb0f9fa4ac
```

## How to build?
---------------
 After downloading your device, kernel and vendor trees, run the following command

 ```bash
 . build/envsetup.sh

 choosecombo debug aosp_$device userdebug

 m
 ```


More info:
---------------
* [**GrapheneOS Website**](https://grapheneos.org/)
* [**GraphenOS GitHub**](https://grapheneos.org/)

