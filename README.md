# PS3HEN 3.5.0 on HFW 4.93.1 via Package Manager

A community-tested method for installing **PS3HEN 3.5.0 on HFW 4.93.1** when the normal PS3HEN installer automatically moves to the newer **PS3HEN 3.6.0**.

This guide documents a method that was successfully tested on a PS3 running **HFW 4.93.1**.

> **Important:** This is an independently documented, community-tested method. It is **not an official downgrade procedure from the PS3HEN developers**, and compatibility with every PS3 model/configuration has not been confirmed. Use it at your own risk.

---

## Table of Contents

* [The Problem](#the-problem)
* [The Tested Method](#the-tested-method)
* [Requirements](#requirements)
* [Step 1 — Start With HFW 4.93.1](#step-1--start-with-hfw-4931)
* [Step 2 — Install PS3HEN 3.6.0](#step-2--install-ps3hen-360)
* [Step 3 — Prepare the USB Drive](#step-3--prepare-the-usb-drive)
* [Step 4 — Verify the HEN 3.5.0 Package](#step-4--verify-the-hen-350-package)
* [Step 5 — Insert the USB](#step-5--insert-the-usb)
* [Step 6 — Open Package Manager](#step-6--open-package-manager)
* [Step 7 — Install HEN 3.5.0](#step-7--install-hen-350)
* [Step 8 — Enable HEN](#step-8--enable-hen)
* [Step 9 — Verify the Result](#step-9--verify-the-result)
* [Why This Works](#why-this-works)
* [Tested Configuration](#tested-configuration)
* [Useful Resources](#useful-resources)
* [Important Notes](#important-notes)
* [Troubleshooting](#troubleshooting)
* [Short Version](#short-version)
* [Credits](#credits)
* [Package Redistribution](#package-redistribution)
* [Compatibility Reports](#compatibility-reports)
* [Disclaimer](#disclaimer)

---

# The Problem

On **HFW 4.93.1**, the normal PS3HEN installation process can install or update to **PS3HEN 3.6.0**.

If you specifically want **PS3HEN 3.5.0**, the normal online installer may not provide an option to select the older version.

During testing, the following method successfully resulted in **PS3HEN 3.5.0 being installed and enabled**:

```text
HFW 4.93.1
     ↓
Install PS3HEN 3.6.0
     ↓
Prepare PS3HEN 3.5.0 HEN.pkg
     ↓
Install HEN.pkg through Package Manager
     ↓
Enable HEN
     ↓
PS3HEN 3.5.0
```

---

# The Tested Method

The key idea is simple:

**Do not try to stop the normal installer from installing 3.6.0.**

Instead:

1. Install **PS3HEN 3.6.0** normally.
2. Obtain the correct **PS3HEN 3.5.0 `HEN.pkg`**.
3. Put it on a **FAT32 USB drive**.
4. Install it manually through **Package Manager**.
5. Run **★ Enable HEN**.

The tested result was:

```text
HFW 4.93.1
      ↓
PS3HEN 3.6.0
      ↓
Install PS3HEN 3.5.0 HEN.pkg
      ↓
★ Enable HEN
      ↓
PS3HEN 3.5.0
```

---

# Requirements

You need:

* A compatible PS3
* **HFW 4.93.1**
* PS3HEN **3.6.0** installed
* A USB flash drive
* USB formatted as **FAT32**
* The correct **PS3HEN 3.5.0 `HEN.pkg`**
* Access to **Package Manager**
* A backup of important PS3 data is recommended

This guide **does not provide or redistribute the HEN package**.

Obtain the required files from appropriate original/legitimate sources.

---

# Step 1 — Start With HFW 4.93.1

Your PS3 should already be running:

```text
HFW 4.93.1
```

You can check the firmware version from:

**Settings → System Settings → System Information**

The system software should show:

```text
4.93.1
```

Do not assume this guide applies to other firmware versions. The tested configuration documented here is **HFW 4.93.1**.

---

# Step 2 — Install PS3HEN 3.6.0

The first part of this method intentionally installs **PS3HEN 3.6.0**.

Use the normal PS3HEN installation procedure appropriate for **HFW 4.93.1**.

Allow the installer to install **PS3HEN 3.6.0**.

Once HEN 3.6.0 is installed and working, you do not need to repeatedly run the online installer.

### Why install 3.6.0 if the goal is 3.5.0?

This is the unusual part of the workaround.

Instead of trying to force the online installer to stay on 3.5.0, allow it to install the newer 3.6.0 first.

After that, install the desired **3.5.0 package manually through Package Manager**.

The important sequence is:

```text
HFW 4.93.1
     ↓
HEN 3.6.0
     ↓
Manually install HEN 3.5.0
```

---

# Step 3 — Prepare the USB Drive

Format the USB flash drive as:

```text
FAT32
```

Create the following folder structure:

```text
USB ROOT
└── PS3
    └── HEN.pkg
```

The complete path should therefore be:

```text
/PS3/HEN.pkg
```

### Correct

```text
USB/
└── PS3/
    └── HEN.pkg
```

### Incorrect

```text
USB/
└── HEN.pkg
```

The `HEN.pkg` file must be inside the `PS3` folder.

---

# Step 4 — Verify the HEN 3.5.0 Package

Before installing anything, make sure the package you are using is actually the intended **PS3HEN 3.5.0 package**.

Do not assume that every file named:

```text
HEN.pkg
```

is PS3HEN 3.5.0.

Do **not** simply rename a different package to `HEN.pkg`.

The purpose of this guide is specifically:

```text
PS3HEN 3.6.0
       ↓
PS3HEN 3.5.0
```

Use the appropriate original/legitimate source for the required package.

---

# Step 5 — Insert the USB

Once the USB is prepared:

1. Safely eject the USB from your computer.
2. Insert the USB into the PS3.
3. Turn on the PS3 if it is currently off.
4. Allow the PS3 to boot normally.

---

# Step 6 — Open Package Manager

From the PS3 XMB:

**Game → Package Manager**

Then select:

**Install Package Files**

Then select:

**Standard**

The PS3 should scan the USB for installable packages.

You should see:

```text
HEN.pkg
```

Select the package.

---

# Step 7 — Install HEN 3.5.0

Select `HEN.pkg`.

Allow the package installation to complete.

**Do not turn off the PS3 during installation.**

The tested result was that the **3.5.0 package installed over the existing 3.6.0 HEN installation**.

Once installation is complete, continue to the next step.

---

# Step 8 — Enable HEN

After the package installation finishes, return to:

**Game → ★ Enable HEN**

Select:

**★ Enable HEN**

Allow the process to finish normally.

The PS3 should return to the XMB with HEN enabled.

---

# Step 9 — Verify the Result

The intended final state is:

```text
Firmware:
HFW 4.93.1

HEN:
PS3HEN 3.5.0
```

The complete tested sequence is:

```text
HFW 4.93.1
     ↓
Install HEN 3.6.0
     ↓
Prepare HEN 3.5.0 HEN.pkg
     ↓
USB:/PS3/HEN.pkg
     ↓
Game → Package Manager
     ↓
Install Package Files
     ↓
Standard
     ↓
Install HEN.pkg
     ↓
★ Enable HEN
     ↓
PS3HEN 3.5.0
```

---

# Why This Works

The important part of the method is installing **HEN 3.6.0 first**.

This gets the PS3 into a working HEN state.

The **HEN 3.5.0 `HEN.pkg`** can then be installed manually through **Package Manager**, instead of relying on the online installer to determine which HEN version to install.

The workaround can therefore be summarized as:

> **Install 3.6.0 first, then manually install the 3.5.0 HEN.pkg through Package Manager.**

This README documents the observed result on the tested configuration. It does not claim that this is an officially supported PS3HEN downgrade mechanism.

---

# Tested Configuration

| Component           | Tested Version  |
| ------------------- | --------------- |
| PS3 Firmware        | HFW 4.93.1      |
| Initial HEN         | PS3HEN 3.6.0    |
| Package Installed   | PS3HEN 3.5.0    |
| Final HEN           | PS3HEN 3.5.0    |
| Installation Method | Package Manager |
| USB Filesystem      | FAT32           |

### Tested Result

**HFW 4.93.1 → HEN 3.6.0 → HEN 3.5.0 `.pkg` → HEN 3.5.0**

This method was successfully tested on one PS3 configuration.

---

# Useful Resources

## HEN Alternate Installer for HFW 4.93

PSX-Place resource:

https://www.psx-place.com/resources/hen-alternate-installer-for-hfw-4-93.1689/

This resource may be useful for users working with HFW 4.93 and PS3HEN installation.

## This Guide

GitHub repository:

https://github.com/TanishThakur77/PS3HEN-3.5.0-4.93.1-Guide

---

# Important Notes

* This is **not an official PS3HEN downgrade guide**.
* This guide documents a **community-tested workaround**.
* The tested firmware was **HFW 4.93.1**.
* Compatibility may vary between PS3 models and firmware configurations.
* Always verify the HEN package version before installing it.
* Do not randomly install packages from unknown sources.
* Back up important PS3 data before modifying system software.
* Do not shut down the PS3 or remove the USB while a package is actively being installed.
* If the PS3 freezes during browser-based installation, avoid repeatedly forcing shutdowns unless necessary.
* This guide does not provide or redistribute HEN packages.
* Obtain required files from appropriate original/legitimate sources.

---

# Troubleshooting

## Package Manager does not show `HEN.pkg`

Check the following:

1. The USB is formatted as **FAT32**.
2. The folder is named exactly:

```text
PS3
```

3. The file is located at:

```text
/PS3/HEN.pkg
```

4. The package has the `.pkg` extension.
5. The USB is properly connected.
6. The package is not corrupted.

The intended structure is:

```text
USB/
└── PS3/
    └── HEN.pkg
```

---

## HEN 3.6.0 is still showing

Make sure that:

1. The **3.5.0 `HEN.pkg`** was actually installed.
2. The package installation completed successfully.
3. You rebooted/re-enabled HEN if required.
4. You are checking the HEN version using an appropriate method rather than assuming the version from the installer used previously.

---

## ★ Enable HEN does not appear

Make sure the package installation completed successfully and that the PS3 has returned to the normal XMB.

If necessary, restart the PS3 and check the Game column again.

---

## The PS3 freezes during browser installation

Browser-based PS3HEN installation can sometimes behave unexpectedly.

If the system becomes completely unresponsive, a forced restart may be necessary, but avoid repeatedly interrupting the console during system or package operations.

Once HEN 3.6.0 is successfully installed, this guide's 3.5.0 portion uses **Package Manager rather than the browser**.

---

# Short Version

If you already know what you're doing:

```text
HFW 4.93.1
     ↓
Install HEN 3.6.0
     ↓
FAT32 USB
     ↓
USB:/PS3/HEN.pkg
     ↓
HEN 3.5.0 package
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

---

# Credits

This guide is based on the author's own testing and documents the PS3HEN installation behavior/workaround described above.

**PS3HEN itself is not my software.**

All PS3HEN code, releases, and associated files belong to their respective original developers and contributors.

Please refer to the original **PS3HEN / PS3Xploit** projects for:

* Official releases
* Source code
* Licensing
* Development information
* Original documentation

This repository is an **independent community guide** and is not affiliated with, endorsed by, or officially supported by the PS3HEN or PS3Xploit developers.

---

# Package Redistribution

This repository **does not redistribute `HEN.pkg`**.

Users should obtain PS3HEN packages from appropriate original/legitimate sources and follow the applicable licenses and distribution terms.

---

# Compatibility Reports

If you successfully use this method, consider reporting your configuration.

Useful information includes:

```text
PS3 model:
HFW version:
Initial HEN version:
Installed HEN version:
Package Manager installation: Successful / Failed
★ Enable HEN: Successful / Failed
```

For example:

```text
PS3 model: CECH-xxxx
HFW: 4.93.1
Initial HEN: 3.6.0
Final HEN: 3.5.0
Package Manager: Successful
Enable HEN: Successful
```

Community reports can help determine whether this method works consistently across different PS3 configurations.

---

# Disclaimer

This README documents a community-tested procedure and is provided for informational and educational purposes.

The author is not responsible for data loss, system instability, failed installations, or other issues resulting from following these instructions.

Modifying PS3 system software carries risks. Always back up important data and use appropriate original/legitimate files.

**Tested configuration: HFW 4.93.1 → HEN 3.6.0 → HEN 3.5.0 via Package Manager.**
