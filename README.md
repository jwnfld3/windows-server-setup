# Installing Windows Server 2022 on a Hyper-V Virtual Machine

## Summary
This step-by-step lab guides you through installing **Windows Server 2022** on a **Hyper-V virtual machine**. You will learn how to install Windows Server, configure essential settings, and prepare the server for future roles. This setup is ideal for testing, training, and building a virtualized lab environment.

---

## Lab Requirements

### Hardware:
- A computer with Windows 10/11 Pro, Enterprise, or Windows Server (Hyper-V enabled)
- Minimum **8GB RAM** (16GB recommended)
- At least **50GB free disk space**
- Internet connection

### Software:
- **Windows Server 2022 ISO** Download from [Microsoft Evaluation Center](https://www.microsoft.com/en-us/evalcenter/download-windows-server-2022?msockid=2c976dd3dcd866de149f78d0ddf5675c.git:target="_blank")
- **Hyper-V Manager** (pre-installed on Windows 10/11 Pro, Enterprise, and Windows Server)

---

## Who, What, When, Where, Why

- **Who:** IT professionals, system administrators, and learners setting up a virtual lab.
- **What:** Installing Windows Server 2022 on a Hyper-V virtual machine.
- **When:** When setting up a virtualized lab environment for testing and learning.
- **Where:** On a local computer running Hyper-V.
- **Why:** To gain hands-on experience with Windows Server virtualization and management.

---

## Step-by-Step Lab Guide

### Step 1: Open Hyper-V Manager and Create a New Virtual Machine
1. Open **Hyper-V Manager** from the Start Menu.
2. In the **Actions** panel on the right, click **New**, then **Virtual Machine**.
![image](https://github.com/user-attachments/assets/c1a06c29-1e5a-456b-95b4-54315860d270)

4. Click **Next** and follow the wizard to configure the virtual machine:
   - **Name**: Enter a name for the VM (e.g., `Server2022-VM`).
   - **Location**: Choose a location for storing the VM files or use the default path.
![image](https://github.com/user-attachments/assets/25e6bb2f-1e09-4570-a322-a65a373daec2)

   - **Generation**: Select **Generation 1** (unless you need UEFI support, in which case, select **Generation 2**).

## What Is UEFI Support and Why It Matters

### Definition
**UEFI (Unified Extensible Firmware Interface)** is a modern firmware interface that replaces the older legacy BIOS system. It is responsible for initializing hardware during the boot process and handing off control to the operating system.

### Key Benefits of UEFI Support

#### 1. Faster Boot Times
- UEFI can initialize hardware more efficiently than legacy BIOS, resulting in quicker startup times for servers and virtual machines.

#### 2. Secure Boot
- UEFI supports **Secure Boot**, a security feature that ensures only trusted operating systems and bootloaders are executed during startup, protecting against rootkits and boot-level malware.

#### 3. Support for Larger Drives
- UEFI uses the **GUID Partition Table (GPT)** instead of MBR, allowing support for drives larger than 2 TB and up to 128 partitions.

#### 4. Enhanced Hardware Compatibility
- UEFI can handle newer hardware architectures and drivers, making it more compatible with modern server and virtualization environments.

#### 5. Graphical and Remote Interfaces
- Offers a graphical user interface and mouse support in some implementations, as well as remote diagnostics and configuration capabilities.

### Relevance in Server 2022 and Virtualization
- UEFI is the default boot option in Windows Server 2022 for both physical servers and virtual machines in platforms like Hyper-V.
- It enables advanced features such as **Shielded VMs** and **VBS (Virtualization-Based Security)**.

> **Note:** While UEFI offers many advantages, it's essential to ensure the operating system and hardware are compatible before switching from legacy BIOS.



![image](https://github.com/user-attachments/assets/f3c8c940-7c46-4486-804e-e475b33c3781)

   - **Memory**: Allocate at least **4GB RAM** (recommend 8GB or more for better performance).
![image](https://github.com/user-attachments/assets/b6be1ebc-bd5f-4371-a2b6-55dc548fc587)

   - **Network**: Select a virtual switch for networking (e.g., Default Switch).
![image](https://github.com/user-attachments/assets/2adc1bcf-1e0d-4988-ad1b-43a90fd341a8)

   - **Hard Disk**: Create a new virtual hard disk (at least 50GB).
![image](https://github.com/user-attachments/assets/59ad5b68-7675-44da-b935-3cda3e20396e)

   - **Installation Options**: Choose **Install an operating system from a bootable image file**, and browse to the **Windows Server 2022 ISO**.
![image](https://github.com/user-attachments/assets/59ab600b-4319-4d88-a6c7-7a7187f4f371)

5. Click **Next** and **Finish**.
![image](https://github.com/user-attachments/assets/43a4d291-4cde-46f6-847d-c4610084cfd3)

### Step 2: Start the Virtual Machine and Boot from the ISO
1. In **Hyper-V Manager**, select the newly created virtual machine.
2. Right-click the VM and select **Connect**.
![image](https://github.com/user-attachments/assets/c1e039bf-4fd2-41af-88bf-a8091f395b17)

4. In the **Virtual Machine Connection** window, click **Start** to power on the VM.
![image](https://github.com/user-attachments/assets/d20a2f3a-8a8e-4820-a8aa-135efc8c4310)

6. When prompted, press any key to boot from the ISO.
7. The **Windows Setup** screen will appear. Choose your **Language, Time, and Keyboard settings**, then click **Next**.
![image](https://github.com/user-attachments/assets/cc743ec8-5f40-4798-8a78-433b5c806738)

### Step 3: Install Windows Server 2022
1. Click **Install Now**.
![image](https://github.com/user-attachments/assets/cdf062c3-b1ef-4a76-9fa7-89a28cab75c4)

3. Select the **Windows Server edition** (Standard or Datacenter, with or without Desktop Experience).
![image](https://github.com/user-attachments/assets/4983d612-dddb-4a6e-8d8c-c5aaf38ba9ec)

5. Click **Next** and accept the license agreement.
![image](https://github.com/user-attachments/assets/2a130e55-71e6-4796-9fc9-f6196188a2e1)

7. Choose **Custom: Install Windows only (advanced)**.
![image](https://github.com/user-attachments/assets/d14a37ed-3fb6-409e-b58c-f244af1ac1f9)

9. Select the virtual hard disk and click **Next** to begin the installation.
![image](https://github.com/user-attachments/assets/4ceff5b5-3b05-4192-a0ac-d34c966baade)

11. The installation will proceed, and the system will reboot automatically.
![image](https://github.com/user-attachments/assets/68d1a788-67b0-4168-b00c-aa58d253fc2b)


### Step 4: Initial Setup and Administrator Account
1. After the reboot, you will be prompted to set an **Administrator password**.
2. Enter a strong password and confirm it.
3. Click **Finish**.
![image](https://github.com/user-attachments/assets/b83b5520-437a-4f64-85a3-8fcfcec7caf6)

5. Press **Ctrl+Alt+Delete**, select the **Administrator account**, and log in.
![image](https://github.com/user-attachments/assets/b9e15be2-609e-4db1-8dc4-fa5c42ef2076)

Since this is a home server setup Yes was clicked for discovery of other PCs.

![image](https://github.com/user-attachments/assets/6061a9d9-eeca-40ff-8295-1acc9a4462e4)

### Step 5: Configure Basic Server Settings
1. Open **Server Manager** (it should open automatically).
2. Click **Local Server** on the left panel.
3. Rename the server:
   - Click the **Computer Name** field.
   - Click **Change** and enter a new name (e.g., `LAB-SERVER2022`).
   - Click **OK** and restart the server when prompted.
![image](https://github.com/user-attachments/assets/ceecb63e-6504-4f38-a9d2-cf443a8b786b)


### Step 6: Configure Network Settings
1. Open **Network and Sharing Center** from the Control Panel.
![image](https://github.com/user-attachments/assets/a3f92d5a-b08a-4419-80db-7ac0e6ac7e0c)
![image](https://github.com/user-attachments/assets/fac78f82-8081-4fa8-ad29-e7b7793d4c46)
![image](https://github.com/user-attachments/assets/57ba78e7-b4e4-4b20-a577-099e9414f616)

3. Click **Change adapter settings** on the left panel.
![image](https://github.com/user-attachments/assets/057c8fb7-3817-49d6-baa4-523f19316e5f)

5. Right-click your network adapter and select **Properties**.
![image](https://github.com/user-attachments/assets/4640e2ba-8d85-4b03-85a5-8bb3490658ce)

7. Select **Internet Protocol Version 4 (TCP/IPv4)** and click **Properties**.
![image](https://github.com/user-attachments/assets/6d53e2df-befa-4fc5-af0c-0636106dec17)

9. Assign a **static IP address**, **subnet mask**, and **DNS settings** as needed.
10. Click **OK** and close all network settings windows.
![image](https://github.com/user-attachments/assets/3a77de11-ea81-4aca-8731-4e5aec23c7d7)

### Step 7: Enable Remote Desktop

## Why Enable Remote Desktop in Server 2022

### Remote Management
- Provides the ability to manage the server from anywhere without needing physical access.  
- Especially useful for headless servers or servers in data centers.

### Efficient Troubleshooting
- Allows IT teams to quickly log in and diagnose issues, apply updates, or perform configurations remotely.

### Multiple Sessions (with RDS)
- When configured with Remote Desktop Services (RDS), multiple users can connect to the server simultaneously in their own sessions.

### Supports Admin Access During Emergencies
- Provides a way to access the server during network or service disruptions where local access is not possible.

### Saves Time and Resources
- Reduces the need to travel to the server’s physical location, saving time and operational costs.



1. Open **Server Manager** and go to **Local Server**.
2. Click **Remote Desktop: Disabled**.
![image](https://github.com/user-attachments/assets/50886ac8-4c89-4f30-b5d0-d40e882cb3dd)

4. Select **Allow remote connections to this computer**.
5. Apply the settings and close the window.
![image](https://github.com/user-attachments/assets/8ecd4b91-555e-47af-8143-4d9727a33358)
![image](https://github.com/user-attachments/assets/5d2d2744-42e7-4e19-89eb-1be0aee19096)

### Step 8: Install Windows Updates
1. Open **Settings > Update & Security**.
2. Click **Check for updates**.
3. Install all available updates and restart the server if required.
![image](https://github.com/user-attachments/assets/8c9b3285-2fd9-424f-a0b0-b67a4b9704d1)
![image](https://github.com/user-attachments/assets/03b645c3-27ff-4534-8002-8af2609d1797)

### Step 9: Configure Security Settings
1. Open **Windows Defender Firewall** and ensure it is enabled.

## Why It Is Important to Ensure Windows Defender Firewall Is Enabled in Server 2022

### 1. First Line of Defense
- Acts as a **barrier between the server and external threats**, helping block unauthorized access.
- Protects against malware, ransomware, and malicious network traffic.

### 2. Traffic Filtering
- Controls **inbound and outbound network traffic** based on defined security rules.
- Only allows authorized applications, ports, and protocols to communicate over the network.

### 3. Supports Compliance Requirements
- Essential for meeting **security standards** that require baseline protections such as firewalls:
  - **SOC 2** – A framework for managing customer data based on five trust principles: security, availability, processing integrity, confidentiality, and privacy.
  - **ISO 27001** – An international standard for information security management systems (ISMS), focusing on risk management and data protection.
  - **HIPAA** – The Health Insurance Portability and Accountability Act, which mandates safeguards for protecting health-related information.
  - **NIST** – The National Institute of Standards and Technology provides security frameworks (like NIST 800-53 and NIST Cybersecurity Framework) used to enhance security posture across federal and private organizations.
- Helps demonstrate that proper security controls are in place.

### 4. Reduces Attack Surface
- Limits exposure to the network by **blocking unused or vulnerable ports** and services.
- Helps prevent lateral movement by attackers within a network.

### 5. Integration with Security Policies
- Can be centrally managed via **Group Policy**, **Microsoft Endpoint Manager**, or **PowerShell**, allowing consistent security enforcement across multiple servers.
- Integrates with **Windows Defender** and **Advanced Threat Protection (ATP)** for layered security.

> **Note:** Always configure firewall rules carefully. While it's important to enable the firewall, legitimate traffic (e.g., Remote Desktop, DNS, web services) should be explicitly allowed to avoid connectivity issues.


![image](https://github.com/user-attachments/assets/9a2a7e47-cc86-4b72-9a52-2a504d2c7745)
![image](https://github.com/user-attachments/assets/68d1651a-6761-4e1b-be39-71bfc1052066)

### Step 10: Create a Checkpoint (Snapshot) in Hyper-V

## Why It Is Important to Create a Checkpoint (Snapshot) in Hyper-V

### 1. Safe Rollback Point
- A checkpoint captures the current **state**, **data**, and **configuration** of a virtual machine (VM).
- If something goes wrong after installing software, applying updates, or making configuration changes, the VM can be easily reverted to its previous working state.

### 2. Testing and Experimentation
- Ideal for **testing environments** or **home labs**, where changes are frequently made.
- Allows users to experiment with different settings, scripts, or deployments without permanent consequences.

### 3. Time-Saving Recovery
- Eliminates the need to reinstall the OS or reconfigure settings if a mistake is made.
- Saves time compared to restoring from full backups.

### 4. Supports Troubleshooting
- Creates a baseline for isolating issues. If a change causes a problem, the checkpoint helps identify the root cause.

### 5. Minimizes Downtime
- Quickly revert a VM to a functional state, reducing downtime in both test and production-like environments.

> **Note:** While checkpoints are powerful, they are not a replacement for regular backups in production environments. Use them for short-term rollback protection during system changes or testing.


1. Open **Hyper-V Manager**.
2. Right-click your VM and select **Checkpoint**.
![image](https://github.com/user-attachments/assets/1dc728e9-239f-454a-b0db-dd1775526f98)
3. Right-Click and select **Rename**
![image](https://github.com/user-attachments/assets/bfbe1390-eb34-4e23-bbb4-f09a940c0f7d)

4. Name the checkpoint (e.g., `Fresh Install`).
![image](https://github.com/user-attachments/assets/9c9b1cad-65a2-4f43-9556-06dc8f2b4016)

This lab helps you **set up a virtualized Windows Server 2022 environment** for testing and learning.
