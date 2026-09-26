# PS3HEN 3.5.0 on HFW 4.93.1 via Package Manager

A community-tested method for installing **PS3HEN 3.5.0 on HFW 4.93.1** when the normal PS3Xploit installer automatically installs the newer **PS3HEN 3.6.0**.

> **Important:** This method was tested on a PS3 running **HFW 4.93.1**. It is not an official PS3Xploit downgrade procedure, so use it at your own risk.

## The Problem

On HFW 4.93.1, the normal PS3HEN installation process may install **PS3HEN 3.5.0** and then offer/download the newer **3.6.0** release.

If 3.6.0 causes problems on your system, you may want to use 3.5.0 instead.

## The Method

The workaround is:

**Install PS3HEN 3.6.0 → install the PS3HEN 3.5.0 `.pkg` through Package Manager**

### Requirements

* PS3 running **HFW 4.93.1**
* PS3HEN 3.6.0 installed
* A FAT32 USB drive
* The correct **PS3HEN 3.5.0 `HEN.pkg`**
* PS3 Package Manager access

## Step 1 — Prepare the USB

Format the USB drive as **FAT32**.

Create this folder structure:

```text
USB:/
└── PS3/
    └── HEN.pkg
```

Place the **PS3HEN 3.5.0 `HEN.pkg`** inside the `PS3` folder.

> Make sure you know which version of `HEN.pkg` you are using. Do not rename an unrelated package and assume it is HEN 3.5.0.

## Step 2 — Install HEN 3.6.0

Use the normal PS3HEN installation method to get **PS3HEN 3.6.0** installed.

Once 3.6.0 is installed, do not keep running the online installer repeatedly.

## Step 3 — Install HEN 3.5.0

On the PS3:

1. Insert the USB drive.
2. Go to **Game**.
3. Open **Package Manager**.
4. Select **Install Package Files**.
5. Select **Standard**.
6. Select the `HEN.pkg` from the USB.
7. Allow the installation to complete.

This installs the **3.5.0 package over the existing HEN installation**.

## Step 4 — Enable HEN

After installation, return to:

**Game → ★ Enable HEN**

Run it normally.

## Step 5 — Verify

Verify that the PS3 is now using the intended **PS3HEN 3.5.0** installation.

If everything works correctly, you can continue using HEN normally.

---

## Why This Works

The important part of this method is that **3.6.0 is installed first**, allowing the PS3 to reach the working HEN state.

The **3.5.0 `HEN.pkg` can then be installed through Package Manager**, rather than relying on the online installer to select the desired version.

This avoids the situation where the online installer automatically chooses the latest available HEN release.

---

## Tested Configuration

| Component           | Version         |
| ------------------- | --------------- |
| PS3 Firmware        | HFW 4.93.1      |
| Initial HEN         | 3.6.0           |
| Final HEN           | 3.5.0           |
| Installation method | Package Manager |
| USB filesystem      | FAT32           |

### Tested Result

**HFW 4.93.1 → HEN 3.6.0 → install HEN 3.5.0 `.pkg` → HEN 3.5.0**

This method was successfully tested on one PS3 configuration.

---

## Important Notes

* This is **not an official downgrade guide** from the PS3HEN developers.
* Do not assume the method is compatible with every HFW/PS3 combination.
* Always verify that the `.pkg` you are installing is actually the intended HEN version.
* Keep a copy of your important PS3 data before modifying system software.
* If your PS3 freezes during the browser-based installation process, do not repeatedly force shutdowns unless necessary. Allow the system to recover and troubleshoot the installation method first.
* Do not install packages from unknown or untrusted sources.

## Short Version

If you just need the procedure:

```text
HFW 4.93.1
      ↓
Install HEN 3.6.0
      ↓
Put HEN 3.5.0 HEN.pkg on FAT32 USB
      ↓
USB:/PS3/HEN.pkg
      ↓
Game → Package Manager
      ↓
Install Package Files → Standard
      ↓
Install HEN.pkg
      ↓
★ Enable HEN
      ↓
HEN 3.5.0
```

## Disclaimer

This README documents a community-tested procedure. It is provided for informational purposes only. The author is not responsible for data loss, system instability, or other issues resulting from following these instructions.

If this method works for you, please report your **PS3 model, HFW version, HEN versions, and result** so compatibility can be documented.
