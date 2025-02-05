+++
date = '2025-02-04T04:07:11+01:00'
draft = false
author = 'Ayedoun Châ-Fine ADEBI'
description = "Choosing Your Linux Distribution"
tags = ["Linux", "Void Linux", "Tutorial", "Beginner"]
categories = ["Linux"]
lang = "en"
title = 'Choosing Your Linux Distribution and Installing Ubuntu on VirtualBox'
+++


## **Why Linux?** 🐧  
<img src="/images/choisir-sa-distro-linux/pourquoi-linux.jpg" width="200px">

When people first hear about Linux, they often imagine a masked hacker in a Hollywood movie... **But in reality, Linux is much more than that!**  
<img src="/media/posts/2025/02/choisir-sa-distro-linux/hacker.webp" width="200px">  
Think of Linux as **a big family of operating systems**:  
- **The Linux kernel** → The common "core" of all (like the script of a TV series)  
- **Distributions** → Different flavors with unique personalities (like the characters)  

Unlike Windows/macOS, Linux offers you:  
🔓 **Total freedom**: Customize *everything* (interface, security, performance)  
🚀 **Lightweight**: Revive an old PC (e.g., with Lubuntu)  
🛡️ **Security**: Fewer viruses thanks to open source and user privileges  

> "*Choosing Linux is like switching from cable TV to Netflix: you decide what, when, and how to use it.*"  

**My personal favorite**: [Why I Switched from Windows to Void Linux]({{< relref "pourquoi-j-ai-choisi-linux" >}})  

---

## **1. Choosing Your Linux Distribution** 🎯  

### **Top 6 Distros for Beginners**  
| Distribution      | Strengths                                    | Target Audience                 | Link |
|------------------|--------------------------------------------|--------------------------------|------|
| **Linux Mint**   | Windows-like interface, ultra-stable       | Former Windows users          | [📥](https://linuxmint.com) |
| **Ubuntu**       | Long-term support, massive community       | Schools/companies, beginners  | [📥](https://ubuntu.com) |
| **Zorin OS**     | Sleek design, "Windows mode" available    | Designers, general users      | [📥](https://zorin.com/os/) |
| **Fedora**       | Cutting-edge tech (Wayland, PipeWire)      | Developers, tech enthusiasts  | [📥](https://getfedora.org) |
| **Pop!_OS**      | Optimized for gaming/NVIDIA, power management | Gamers, content creators | [📥](https://pop.system76.com) |
| **MX Linux**     | Lightweight, built-in troubleshooting tools | Old machines, tinkerers       | [📥](https://mxlinux.org) |

🔍 **Need help choosing?** Check out [DistroWatch](https://distrowatch.com), the "IMDb of Linux distributions"!

---

## **2. Preparing for Installation on VirtualBox** 🖥️  

### **What is VirtualBox?**  
VirtualBox is a **free** software that allows you to create *virtual machines* (VMs):  
- 🖥️ **Virtual machine** = A simulated PC inside your current PC  
- 🛡️ **Advantage**: Test Linux without touching your main system  

### ✅ **Pre-installation Checklist**  
1. **Download Ubuntu LTS** ([official link](https://ubuntu.com/download/desktop))  
   → *Why LTS?* = Long Term Support version (guaranteed updates for a long period).  
  <img src="/media/posts/2025/02/choisir-sa-distro-linux/down-ubun.png" width="400px">
2. **Install VirtualBox** ([Windows](https://download.virtualbox.org/virtualbox/7.0.14/VirtualBox-7.0.14-161095-Win.exe) / [macOS](https://download.virtualbox.org/virtualbox/7.0.14/VirtualBox-7.0.14-161095-OSX.dmg))  
   → *Installation process*: Double-click the downloaded file and follow the instructions.  
  
3. **Check disk space**:  
   - At least 20 GB for Ubuntu  
   - Recommended: 2 GB of free RAM  

---

### **Creating Your Virtual Machine in 5 Steps**  

#### **Step 1: Launch VirtualBox and Click "New"**  

<img src="/media/posts/2025/02/choisir-sa-distro-linux/Ubuntu-VirtualBox-Installation-00.png" width="400px">

#### **Step 2: Configure Basic Settings**  
- **Name**: `Ubuntu-Tutorial` (no spaces)  
- **Type**: Linux  
- **Version**: Ubuntu (64-bit)  
<img src="/media/posts/2025/02/choisir-sa-distro-linux/Ubuntu-VirtualBox-Installation-011.png" width="400px">

#### **Step 3: Allocate RAM**  
- Minimum: 2048 MB (2 GB)  
- Recommended: 4096 MB (4 GB)  

#### **Step 4: Create the Virtual Hard Disk**  
- Choose **VDI** (VirtualBox native format)  
- Select **Dynamically allocated** (disk grows as needed)  
- Size: At least 20 GB  

#### **Step 5: Mount the Ubuntu ISO**  
1. Select your VM → **Settings** → **Storage**  
2. Click the 📀 icon under "Controller: IDE" → **Choose a disk file**  
3. Select your `ubuntu-XX.XX-lts.iso` file  

---

## **3. Installing Ubuntu** 🛠️  

### **Step-by-Step Visual Guide**  
1. **Start the VM** → Click "Start"  
2. **Language selection** → English  
3. **Installation options**:  
   - ☑️ *Normal installation* (browser, office suite, multimedia tools)  
   - ☑️ *Download updates now*  
4. **Partitioning** → *Erase disk and install Ubuntu*  
   → **⚠️ Safe**: This does not affect your real hard drive!  
5. **User configuration**:  
   - Name: `your-username`  
   - Password: **At least 8 characters** (e.g., `LinuxR0cks!`)  
6. **Wait 10-20 min** → Ubuntu installs automatically  

---

### **Bonus: Post-Installation Customization**  
After rebooting:  
1. Install **Guest Additions** (for copy-paste and full-screen mode):  
   ```bash
   sudo apt install virtualbox-guest-utils -y
   ```  
2. Enable **dark mode** in *Settings > Appearance*  
3. Add useful shortcuts to the sidebar  

---

### **FAQ: Common Issues**  

#### **🖥️ The VM is too slow?**  
- Increase RAM to 4 GB in *Settings > System*  
- Enable 3D acceleration in *Display > Screen*  

#### **⌨️ My keyboard isn’t responding in the VM?**  
Click inside the VirtualBox window and press **Ctrl + Alt + Del** to release focus.  

#### **📁 How to transfer files?**  
Enable **drag and drop** via *Devices > Drag and Drop > Bidirectional*.  

