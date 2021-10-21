Have Actually tried, it's work in android 9 ARM 64 platform.

1. Put busybox-armv6l into aosp out/target/product/*/system/xbin

2. Re-make systemimage, "make -j32 systemimage"

3. Re-flash systemimage


Or, apply the [patch](./patch/DON-T-MERGE-disable-sepolicy-add-busybox.patch) to aosp. Self-verified on [android 10](https://cs.android.com/android/platform/superproject/+/android-10.0.0_r41:).


<br/>

[Download Binaries](https://busybox.net/downloads/)