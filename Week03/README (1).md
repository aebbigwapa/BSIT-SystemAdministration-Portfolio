# Week 3 — Enterprise Server Deployment and Operating System Installation

**Course:** ITEP 414 – System Administration and Maintenance
**Program:** Bachelor of Science in Information Technology (BSIT)
**Role:** Junior System Administrator, ABC Startup Solutions

---

## Project Overview

This project focuses on the deployment of a new Ubuntu Server virtual machine for ABC Startup Solutions. The project involves installing Ubuntu Server, configuring essential server settings, enabling secure remote administration through SSH, verifying server functionality, and documenting the complete deployment process.

The project also includes research and comparison of BIOS and UEFI firmware, an Ubuntu boot process flowchart, installation of Windows Server Evaluation, and a comparison of Windows Server, Ubuntu Server, and Rocky Linux.

The purpose of this project is to demonstrate the foundational skills required of a Junior System Administrator, including operating system deployment, virtualization, server configuration, troubleshooting, verification, security, and professional technical documentation.

---

## Learning Objectives

After completing this project, I should be able to:

* Explain the purpose of an operating system in an enterprise environment.
* Differentiate BIOS and UEFI firmware.
* Explain the stages of the computer boot process.
* Compare Ubuntu Server, Windows Server, and Rocky Linux.
* Install Ubuntu Server in a virtual machine.
* Configure a server hostname, user account, storage, networking, and SSH.
* Verify server functionality using Linux commands.
* Troubleshoot basic virtualization and server configuration problems.
* Produce professional technical documentation.
* Document server deployment procedures that can be followed by future administrators.

---

## Virtual Machine Specifications

| Component       | Configuration               |
| --------------- | --------------------------- |
| Name            | `Ubuntu-Server-Week03`      |
| RAM             | 4 GB (4096 MB)              |
| CPU             | 2 Virtual Processors        |
| Storage         | 40 GB                       |
| Disk Type       | VDI                         |
| Disk Allocation | Dynamically Allocated       |
| Network         | NAT                         |
| Optical Drive   | Ubuntu Server 26.04 LTS ISO |

The virtual machine was created using Oracle VirtualBox. The configuration follows the minimum specifications provided in the Week 3 project instructions.

---

## Installation Summary

* **Operating System:** Ubuntu Server 26.04 LTS
* **Language:** English
* **Keyboard Layout:** English (US)
* **Network Configuration:** DHCP
* **Hostname:** `server01`
* **Non-root Administrative User:** `studentadmin`
* **Disk Partitioning:** Guided – Use Entire Disk
* **Partition Scheme:** GPT
* **File System:** ext4
* **Disk Size:** 40 GB
* **OpenSSH Server:** Installed during Ubuntu Server installation
* **Additional Packages:** None

The Ubuntu Server virtual machine was configured with 4 GB of RAM, 2 virtual processors, a 40 GB VDI virtual disk, NAT networking, and the Ubuntu Server LTS installation ISO.

A non-root administrative account named `studentadmin` was planned for normal server administration instead of using the root account directly.

---

## Configuration Summary

| Configuration         | Result                                               |
| --------------------- | ---------------------------------------------------- |
| Hostname              | `server01`                                           |
| Network Mode          | NAT                                                  |
| Network Configuration | DHCP                                                 |
| IP Address            | DHCP-assigned; exact address recorded from `ip addr` |
| Administrative User   | `studentadmin`                                       |
| SSH Server            | OpenSSH Server                                       |
| Additional Packages   | None                                                 |

The NAT configuration allows the Ubuntu Server virtual machine to access the internet through the host computer while keeping the virtual machine behind VirtualBox's NAT network.

---

## Verification Results

The following commands are used to verify the functionality of the Ubuntu Server.

| Task                  | Command                                  | Result                                                |
| --------------------- | ---------------------------------------- | ----------------------------------------------------- |
| Login                 | Log in using the administrative account  | Pass after successful login                           |
| Hostname              | `hostname`                               | Expected: `server01`                                  |
| IP Address            | `ip addr`                                | DHCP address assigned; exact address recorded from VM |
| Internet Connectivity | `ping -c 4 google.com`                   | Pass after receiving successful replies               |
| System Update         | `sudo apt update && sudo apt upgrade -y` | Pass after updates complete successfully              |
| SSH Service           | `systemctl status ssh`                   | Expected: `active (running)`                          |

Screenshots for each verification task are stored in the `screenshots/` directory.

The final verification results should be updated after the commands are actually executed on the Ubuntu Server virtual machine.

---

## BIOS vs UEFI Highlights

BIOS and UEFI are firmware technologies responsible for initializing computer hardware and starting the operating system.

BIOS, or Basic Input/Output System, is the traditional firmware interface used by older computer systems. It performs hardware initialization and searches for a bootable device. BIOS systems commonly use the Master Boot Record (MBR) partitioning scheme.

UEFI, or Unified Extensible Firmware Interface, is the modern replacement for traditional BIOS. UEFI supports modern storage technologies through the GUID Partition Table (GPT), provides features such as Secure Boot, and offers a more flexible environment for starting operating systems.

UEFI has largely replaced BIOS in modern computers because it provides better support for modern hardware, larger storage devices, and improved security features.

### BIOS vs UEFI Comparison

| Feature         | BIOS                                                                                      | UEFI                                                    |
| --------------- | ----------------------------------------------------------------------------------------- | ------------------------------------------------------- |
| Definition      | Traditional firmware interface used to initialize hardware and start the operating system | Modern firmware interface designed to replace BIOS      |
| Boot Process    | Performs hardware initialization and searches for a bootable device                       | Initializes hardware and uses a modern boot manager     |
| Partition Style | MBR                                                                                       | GPT                                                     |
| Disk Support    | Traditionally associated with MBR's approximately 2 TB limitation                         | Supports very large disks through GPT                   |
| Security        | Limited built-in security features                                                        | Supports Secure Boot and other modern security features |
| Speed           | Generally slower                                                                          | Generally faster and more flexible                      |
| Advantages      | Simple, mature, and compatible with older systems                                         | Modern, flexible, secure, and supports large storage    |
| Disadvantages   | Older technology with storage and feature limitations                                     | More complex than traditional BIOS                      |
| Modern Usage    | Primarily used for legacy systems                                                         | Standard in most modern computers                       |

Understanding BIOS and UEFI is important for system administrators because firmware settings can affect operating system installation, disk partitioning, boot configuration, virtualization, troubleshooting, and system security.

---

## Boot Process Flowchart

The Ubuntu Server boot process follows these major stages:

**Power On → BIOS/UEFI Initialization → Boot Device Detection → Boot Loader (GRUB) → Linux Kernel → init/systemd → Services Start → Login Prompt**

### Boot Process Explanation

1. **Power On** — The computer or virtual machine is powered on.
2. **BIOS/UEFI Initialization** — Firmware initializes the available hardware and prepares the system for booting.
3. **Boot Device Detection** — The firmware identifies the device containing the operating system.
4. **Boot Loader (GRUB)** — GRUB loads and prepares the Linux operating system.
5. **Linux Kernel** — The Linux kernel is loaded into memory and begins managing system resources.
6. **init/systemd** — Ubuntu uses systemd to initialize the operating system and manage system services.
7. **Services Start** — Required system services are started.
8. **Login Prompt** — The system presents the user with the login prompt.

The completed flowchart will be stored in:

```text
diagrams/boot-process.png
BootProcessFlowchart.pdf
```

---

## Challenges Encountered

During the initial virtual machine setup, a virtualization error occurred when attempting to start the Ubuntu Server virtual machine.

VirtualBox displayed the error:

```text
AMD-V is disabled in the BIOS
VERR_SVM_DISABLED
```

This occurred because AMD hardware virtualization was disabled in the computer's BIOS/UEFI firmware. VirtualBox requires hardware virtualization to run the virtual machine properly.

The solution was to enable **SVM Mode/AMD virtualization** in the computer's BIOS/UEFI settings. After enabling the feature, the Ubuntu Server virtual machine could be started and the installation process could continue.

This troubleshooting experience demonstrated the importance of understanding both software virtualization platforms and the hardware-level virtualization settings that support them.

---

## Reflection

This Week 3 project helped me understand that deploying an enterprise server involves much more than simply installing an operating system. A Junior System Administrator must consider hardware resources, virtualization, storage, networking, user accounts, security, remote administration, troubleshooting, verification, and documentation before a server can be considered ready for use.

The first part of the project involved creating an Ubuntu Server virtual machine using Oracle VirtualBox. I configured the virtual machine with 4 GB of RAM, 2 virtual processors, 40 GB of storage, NAT networking, and an Ubuntu Server LTS ISO. This gave me practical experience in preparing a virtual server environment before installing the operating system.

One of the challenges I encountered was a virtualization error when I attempted to start the virtual machine. VirtualBox reported that AMD-V was disabled in the BIOS. This showed me that virtualization depends not only on software such as VirtualBox but also on hardware-level features configured through BIOS or UEFI. Troubleshooting this issue helped me understand the relationship between the physical computer and the virtual environment.

The BIOS and UEFI portion of the project also helped me understand why firmware knowledge is important for system administrators. BIOS and UEFI control important parts of the system startup process, and their settings can affect booting, operating system installation, disk partitioning, security, and virtualization. UEFI is particularly important in modern systems because it supports GPT, large storage devices, and security features such as Secure Boot.

I also learned about the Ubuntu boot process, beginning with power on and firmware initialization, followed by boot device detection, GRUB, the Linux kernel, systemd, system services, and finally the login prompt. Understanding this sequence can help administrators troubleshoot boot problems more effectively.

Overall, this project provided practical experience that is closely related to real-world Junior System Administrator responsibilities. It showed me that successful server deployment requires not only technical skills but also careful planning, troubleshooting, verification, security awareness, and clear documentation. These skills will be useful when managing servers and infrastructure in an actual enterprise environment.

---

## References

* Ubuntu. **Ubuntu Server Documentation.**
* Ubuntu. **Ubuntu Server Installation Documentation.**
* Microsoft Learn. **Windows Server Documentation.**
* Rocky Linux. **Rocky Linux Documentation.**
* Oracle. **Oracle VirtualBox Documentation.**

---

## Project Repository Structure

```text
BSIT-SystemAdministration-Portfolio/
│
├── Week03/
│   ├── InstallationGuide.pdf
│   ├── ProfessionalInstallationManual.pdf
│   ├── BIOS_vs_UEFI.pdf
│   ├── BootProcessFlowchart.pdf
│   ├── README.md
│   │
│   ├── screenshots/
│   │   ├── 01-vm-configuration.png
│   │   ├── 02-login.png
│   │   ├── 03-hostname.png
│   │   ├── 04-ip-address.png
│   │   ├── 05-ping.png
│   │   ├── 06-system-update.png
│   │   ├── 07-ssh-status.png
│   │   └── 08-windows-server.png
│   │
│   ├── diagrams/
│   │   └── boot-process.png
│   │
│   └── references/
```

---

## Project Status

| Requirement                      | Status            |
| -------------------------------- | ----------------- |
| Ubuntu Server VM Created         | ✅ Completed       |
| VM Name Configured               | ✅ Completed       |
| RAM Configured                   | ✅ 4 GB            |
| CPU Configured                   | ✅ 2 CPUs          |
| Storage Configured               | ✅ 40 GB           |
| NAT Networking                   | ✅ Configured      |
| Ubuntu Server ISO Attached       | ✅ Completed       |
| Ubuntu Server Installation       | 🟡 In Progress    |
| Hostname `server01`              | 🟡 To Configure   |
| Administrative User              | 🟡 To Configure   |
| SSH Installation                 | 🟡 To Configure   |
| Login Verification               | ⏳ Pending         |
| Hostname Verification            | ⏳ Pending         |
| IP Address Verification          | ⏳ Pending         |
| Internet Connectivity            | ⏳ Pending         |
| System Update                    | ⏳ Pending         |
| SSH Service Verification         | ⏳ Pending         |
| BIOS vs UEFI Comparison          | ✅ Completed       |
| Boot Process Flowchart           | ⏳ To Be Created   |
| Windows Server Installation      | ⏳ Pending         |
| OS Comparison                    | ⏳ To Be Completed |
| Installation Guide               | ⏳ To Be Completed |
| Professional Installation Manual | ⏳ To Be Completed |
| GitHub README                    | 🟡 In Progress    |
| LinkedIn Reflection              | ⏳ Pending         |
