# Cybersecurity Lab Setup: Kali Linux on Oracle VirtualBox (External Drive)

A fully optimized, isolated, and portable cybersecurity testing laboratory built using **Oracle VM VirtualBox** and **Kali Linux**, configured to run from an external portable hard drive to protect internal system storage.

---

## 🛠️ Tech Stack & Tools
* **Hypervisor:** Oracle VM VirtualBox
* **Operating System:** Kali Linux (VirtualBox Pre-built VM Image)
* **Storage Strategy:** External Portable Hard Drive (saving internal C: drive space)
* **Download Accelerator:** Free Download Manager (FDM)
* **Archive Extraction:** 7-Zip

---

## ⚙️ Architecture & Design Rationale
1. **Portable Storage Management:** To avoid cluttering the primary OS drive and to accommodate heavy virtual disk expansions (10GB+), the entire virtual machine directory is configured to reside on an external portable hard drive via VirtualBox's *Default Machine Folder* preferences.
2. **Resilient Downloading:** Large virtual machine archives (~3.6 GB) frequently fail on standard unstable network connections when downloaded via web browsers due to session timeouts or resets. **Free Download Manager (FDM)** was utilized to enforce robust multi-threaded and resumable data streaming.

---

## 🚀 Step-by-Chief Installation Guide

### 1. Handling Unstable Networks (Download Phase)
* **Challenge:** Direct browser downloads of large VM files kept crashing or resetting to 0% due to network drops.
* **Solution:** Used **Free Download Manager (FDM)** ([freedownloadmanager.org](https://freedownloadmanager.org)) to handle the 3.6 GB archive. FDM allows session pausing, error recovery, and seamless resumption across network glitches.

### 2. File Extraction & Preparation
* Downloaded the `.7z` pre-built VirtualBox image for Kali Linux.
* Extracted the archive cleanly using **7-Zip** directly onto a dedicated folder within the portable external hard drive.

### 3. Hypervisor & Virtual Drive Configuration
* Configured Oracle VirtualBox **Preferences > General > Default Machine Folder** to point directly to the external portable hard drive directory.
* Imported the appliance configuration file (`.vbox`) into VirtualBox.

### 4. Network & Baseline Verification
* Booted the Kali Linux virtual machine instance.
* Verified proper network interface behavior (NAT / Wired connection settings).
* Tested internet access (browsing and media playback verification).
* **Snapshot Created:** Took a clean baseline system snapshot immediately after verification to preserve a stable initial state for future cybersecurity labs.

---

## 📸 Lab Status & Verification
* **Network Status:** Operational (Connected via VirtualBox Network Adapter)
* **Storage Location:** External Portable Hard Drive 
* **Current State:** Baseline Snapshot Active 🟢

---
*Created as part of practical cybersecurity internship preparation and lab architecture design.*
