# Software ROM Releases for Xiaomi Redmi Note 10 (Sunny/Mojito)

Welcome to the ROM repository for the Xiaomi Redmi Note 10 (Sunny/Mojito). All releases listed here are compatible with TWRP, PBRP, and OrangeFox recovery (not preloaded yet).

**Disclaimer**: Please ensure you follow these instructions carefully before seeking support. Flashing a custom ROM can lead to data loss, boot loops, or bricked devices if not done properly. By following these instructions, you acknowledge that any issues arising from improper flashing are your responsibility.

---

## 📱 ROM Releases

1. **CrDroid v11.1** | Android 15.1 | *'Vanilla Special'*
    - 🔧 Custom Patchsets
    - 🔒 Magisk
    - 🛒 Aurora Store
    - 🛡️ AFWall
    - 🚫 AdAway

2. **E/OS e-2.7-u** | Android 14.1 | *'Vanilla Special'*
    - 🔧 Custom Patchsets
    - 🔒 Magisk
    - 🛒 Aurora Store
    - 🛡️ AFWall
    - 🚫 AdAway

3. **LineageOS v22.1** | Android 15.1 | *'Vanilla Special'*
    - 🔧 Custom Patchsets
    - 🔒 Magisk
    - 🛒 Aurora Store
    - 🛡️ AFWall
    - 🚫 AdAway

---

## 🔧 Recovery Options

**TWRP 3.7.1**
- 🟢 Bootable Image
- 🟢 Installable ZIP

---

## 🚀 First-Time Flashing Instructions

Follow these steps carefully to flash a custom ROM on your device:

### 1. Backup Your Data
Make a complete backup of your device, as flashing will erase all data and return the device to factory defaults.

### 2. Download and Flash Stock Firmware
- Download the latest firmware (V14.0.9.0.SKGMIXM) from [MiFirm](https://mifirm.net/download/12791).
- Unpack the firmware image.

### 3. Enter Fastboot Mode
1. Power off your device.
2. Hold **Volume Down + Power** to enter Fastboot mode.

### 4. Connect and Flash Stock Firmware
1. Connect your phone to your PC via USB-C cable.
2. Open a terminal/command prompt.
3. Navigate to the directory of the unpacked firmware and run:
    - **Windows**: `flash_all.bat`
    - **Linux/macOS**: `flash_all.sh`

### 5. Verify and Boot
- Ensure the process completes with a "Success" message.
- If the process fails, repeat step 4 or hold the power button to reboot and retry.
- Wait for the **MIUI** installation screen to appear after the device reboots.

### 6. Flash Custom ROM
1. Download your desired ROM and the `LOS-boot.img` file from this repository.
2. Enter Fastboot mode again (step 3).
3. Open a terminal/command prompt.
4. Boot the recovery image:
    - `fastboot boot LOS-boot.img`
5. In recovery mode, navigate to **Apply Update** using the volume buttons, and confirm with the power button.
6. Select **Apply from ADB** and flash the ROM:
    - `adb sideload your_rom.zip`
7. Once complete, restart the recovery when prompted.
8. In recovery mode, navigate to **Apply Update** using the volume buttons, and confirm with the power button.
9. Flash the custom recovery:
    - `adb sideload your_custom_recovery.zip`

### 7. Factory Reset and Boot
1. Perform a factory reset in the custom recovery:
    - Navigate to **Factory Reset** and confirm twice.
2. Reboot your device to load the new ROM.

### 8. Optional: Install Magisk
If you need root:
1. Download the latest Magisk from [GitHub](https://github.com/topjohnwu/Magisk).
2. Restart to recovery mode again and flash Magisk:
    - `adb sideload Magisk-version.apk`
3. Reboot and complete the Magisk setup.

---

## ⚠️ Common Issues

1. **Black Screen After Booting Custom Recovery**
   - **Cause**: The ROM uses `vendor_boot` as the boot image, preventing custom recoveries or kernels.
   - **Solution**: Use a ROM compatible with non-`vendor_boot` custom recoveries.

2. **Screen Hangs After Booting Custom Recovery**
   - **Cause**: Custom recovery doesn't support encryption, or your data/metadata partition is corrupted.
   - **Solution**: Perform a factory reset or use a recovery that supports decryption.

3. **Touchscreen or Sideloading Not Working in Recovery**
   - **Cause**: Old firmware loaded in the vendor partition by an outdated ROM or firmware.
   - **Solution**: After flashing the ROM (step 6), the new ROM will update the vendor partition and fix the issue.

---

## 📝 Notes
- Always use the latest firmware before flashing custom ROMs.
- Make sure to follow the exact steps to avoid boot loops or bricked devices.
- Use **ADB** and **Fastboot** tools for seamless flashing.

