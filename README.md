# PS3HEN 3.5.0 on HFW 4.93.1 via Package Manager

A community-tested method for getting **PS3HEN 3.5.0 working on a PS3 running HFW 4.93.1** when the normal PS3HEN installer automatically moves to the newer **PS3HEN 3.6.0**.

This guide documents a method that was successfully tested on a PS3 running **HFW 4.93.1**.

> **Important:** This is an independently documented, community-tested method. It is **not an official downgrade procedure** from the PS3HEN developers, and compatibility with every PS3 model/configuration has not been confirmed.

---

# Why This Guide Exists

While installing HEN on **HFW 4.93.1**, the normal installation process can install **PS3HEN 3.5.0** and then detect that **PS3HEN 3.6.0** is the latest available version.

If you specifically want to use **PS3HEN 3.5.0**, the normal installer may therefore leave you on 3.6.0.

During testing, the following method successfully resulted in **PS3HEN 3.5.0 being installed**:

```text
HFW 4.93.1
      ↓
Install PS3HEN 3.6.0
      ↓
Prepare the PS3HEN 3.5.0 HEN.pkg
      ↓
Install HEN.pkg using Package Manager
      ↓
Enable HEN
      ↓
PS3HEN 3.5.0
```

---

# Requirements

You need:

* A compatible PS3
* **HFW 4.93.1**
* PS3HEN **3.6.0**
* A USB flash drive
* USB formatted as **FAT32**
* The correct **PS3HEN 3.5.0 `HEN.pkg`**
* Access to **Package Manager**

This guide does **not** provide or redistribute the HEN package.

Use the original PS3HEN project/release sources to obtain the appropriate files.

---

# Part 1 — Start With HFW 4.93.1

Your PS3 should already be running:

```text
HFW 4.93.1
```

You can check your firmware version from:

**Settings → System Settings → System Information**

The system software should show:

```text
4.93.1
```

Do not follow this guide if you are using a completely different firmware version without first confirming compatibility.

---

# Part 2 — Install PS3HEN 3.6.0

The first part of this method intentionally installs **PS3HEN 3.6.0**.

Use the normal, legitimate PS3HEN installation procedure for your HFW version.

At the end of this step, your PS3 should have:

```text
PS3HEN 3.6.0
```

### Why install 3.6.0 if the goal is 3.5.0?

This is the unusual part of the method.

Instead of trying to make the online installer stay on 3.5.0, we allow it to install the newer 3.6.0 first.

We then use **Package Manager** to install the 3.5.0 package manually.

The tested sequence is therefore:

```text
3.5.0 → 3.6.0 → manually install 3.5.0
```

The important part is that the **3.5.0 package is installed manually through Package Manager**.

---

# Part 3 — Prepare the USB Drive

Use a USB flash drive formatted as:

```text
FAT32
```

The folder structure must be:

```text
USB ROOT
└── PS3
    └── HEN.pkg
```

In other words, the complete path should be:

```text
/PS3/HEN.pkg
```

### Important

The file must be called:

```text
HEN.pkg
```

and it must be inside the:

```text
PS3
```

folder.

Do **not** put it directly in the root of the USB like this:

```text
USB/
└── HEN.pkg
```

That is the wrong structure for this procedure.

The correct structure is:

```text
USB/
└── PS3/
    └── HEN.pkg
```

---

# Part 4 — Make Sure the Package Is PS3HEN 3.5.0

Before installing the package, make sure the `HEN.pkg` you are using is actually the **PS3HEN 3.5.0 package**.

Do not assume that every file named `HEN.pkg` is 3.5.0.

The purpose of this guide is specifically:

```text
PS3HEN 3.6.0
        ↓
PS3HEN 3.5.0
```

The package should come from the appropriate original/legitimate PS3HEN release source.

---

# Part 5 — Insert the USB Into the PS3

Once the USB is prepared:

1. Safely eject the USB from your computer.
2. Insert it into the PS3.
3. Turn on the PS3 if it is currently off.
4. Make sure the PS3 has booted normally.

---

# Part 6 — Open Package Manager

On the PS3 XMB:

**Game → Package Manager**

Then select:

**Install Package Files**

Then select:

**Standard**

The PS3 should scan the USB for installable packages.

You should see the package you placed in:

```text
PS3/HEN.pkg
```

Select it.

---

# Part 7 — Install HEN 3.5.0

Select the `HEN.pkg` and allow the installation to complete.

Do **not** turn off the PS3 while the package is being installed.

The tested result was that the **3.5.0 package installed over the existing 3.6.0 HEN installation**.

After installation, the PS3 should contain the 3.5.0 HEN installation.

---

# Part 8 — Enable HEN

After the package installation finishes:

Go to:

**Game → ★ Enable HEN**

Select:

**★ Enable HEN**

Allow the process to finish.

The PS3 should return to the XMB with HEN enabled.

---

# Part 9 — Verify the Result

The final intended state is:

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

# Tested Configuration

| Item                | Tested Version  |
| ------------------- | --------------- |
| Firmware            | HFW 4.93.1      |
| Initial HEN         | PS3HEN 3.6.0    |
| Package installed   | PS3HEN 3.5.0    |
| Final HEN           | PS3HEN 3.5.0    |
| Installation method | Package Manager |
| USB filesystem      | FAT32           |

---

# Why Not Just Install 3.5.0 Directly?

The problem this guide addresses is that the normal online installation process can automatically offer/install the **latest available HEN version**, which in this situation is **3.6.0**.

Instead of fighting the online installer, this method uses the installer to get HEN working first and then manually installs the desired **3.5.0 package** through Package Manager.

The key part of the workaround is:

> **Install 3.6.0 first, then install the 3.5.0 HEN.pkg through Package Manager.**

---

# Important Warnings

### This is not an official downgrade tool

This repository does not claim that PS3HEN 3.6.0 → 3.5.0 is an officially supported downgrade process.

It documents a method that **worked on the author's PS3 configuration**.

### Compatibility is not guaranteed

The tested configuration was:

```text
HFW 4.93.1
PS3HEN 3.6.0
PS3HEN 3.5.0 HEN.pkg
```

Other HFW versions, PS3 models, or HEN versions may behave differently.

### Do not randomly install packages

Make sure you know exactly which HEN version your package contains before installing it.

### Back up important data

Modifying system software can potentially cause instability or data loss.

Keep backups of important PS3 data before making changes.

### Do not interrupt package installation

Do not shut down the PS3 or remove the USB while a package is actively being installed.

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

Users should obtain PS3HEN packages from the appropriate original/legitimate sources and follow the applicable licenses and distribution terms.

---

# Feedback / Compatibility Reports

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

More community reports can help determine whether this method works consistently across different PS3 configurations.

---

# Disclaimer

This repository is provided for informational and educational purposes.

Modifying PS3 system software carries risks, including instability and potential data loss.

The author is not responsible for damage, data loss, system instability, or other problems resulting from following this guide.

Use the appropriate official/original PS3HEN files and make backups before modifying your system.
