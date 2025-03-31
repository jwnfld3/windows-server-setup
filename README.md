# Windows Server Setup

## Summary
This lab provides a step-by-step guide for setting up a **Windows Server** environment, covering the installation and basic configuration of Windows Server 2016 or newer. The lab includes tasks such as configuring server roles, networking settings, Active Directory setup, and security best practices. Participants will also learn how to integrate the server with other enterprise services and applications, ensuring a secure and optimized server environment.

**Click on the images below to view the full-size version**

## Lab Requirements:
- A physical or virtual machine with at least **4GB of RAM** and **40GB of free disk space**.
- **Windows Server 2016** or newer installation media (ISO or DVD).
- **Administrator access** to the server machine.
- Basic understanding of server hardware and network configuration.
- **Internet connection** for downloading updates and additional tools.
- Optional: Access to **Active Directory** and **DNS** server for testing domain-based configurations.

## Who:
- IT administrators, system engineers, and anyone interested in learning about Windows Server installation and management.
- Individuals looking to expand their knowledge of server infrastructure and configuration.
- Anyone preparing for a **Microsoft Certified: Windows Server** certification or looking to gain hands-on experience with Windows Server.

## What:
- This lab guides participants through setting up a **Windows Server** environment, covering installation, configuration of server roles, Active Directory setup, and basic security measures.
- The lab will involve configuring networking, managing users and groups, and ensuring the server is ready for domain integration.

## When:
- This lab can be set up and completed at any time, with an estimated completion time of **2-3 hours** for the full setup, depending on familiarity with server environments.
- It is recommended to perform the lab during a maintenance window or in a controlled environment to avoid disrupting any live services.

## Where:
- The lab is conducted on a physical or virtual server that is **isolated** from production systems for testing purposes.
- Participants will need access to the **Windows Server 2019** installation media, which can be obtained from Microsoft’s official website or Volume Licensing Service Center.

## Why:
- To provide hands-on experience in setting up a Windows Server environment and understanding the critical roles it plays in enterprise infrastructure.
- To learn how to install, configure, and secure a Windows Server machine, preparing it for use in a domain or networked environment.
- To understand best practices in server management and gain familiarity with the administrative tools available in Windows Server.


<h2>Install and configure Windows Server 2016</h2>

<p align="center">
<br/>
<img src="https://imgur.com/wNaj3cd.png" height="130%" width="130%" alt>
<br />
<br />
 <br />
I’m renaming the machine, but notice that I haven’t assigned it to a domain yet, as a domain will be created.<br/>
<img src="https://imgur.com/WLLrXXK.png" height="130%" width="130%" alt>
<br />
<br />
The computer must be restarted for the name change to take effect, but I selected "Restart Later" to first review the network settings.
 <img src="https://imgur.com/vRWevEt.png" height="50%" width="50%" alt>
<br />
<br />
In the Windows search bar, type "Control Panel" > Network and Internet > Network and Sharing Center > Change adapter settings.  <br/>
<img src="https://imgur.com/fckBPyk.png" height="80%" width="80%" alt>
<br />
<br />
I right-clicked the Ethernet icon and selected Properties.
<br/>
 <br/>
<img src=https://imgur.com/6aGKJk4.png" height="80%" width="80%" alt>
<br />
<br />
I accessed the properties for TCP/IPv4 to configure a static IP address. This is essential because the domain controller requires a static IP to ensure domain-joined computers can locate it, providing stability and proper network configuration.  <br/>
<img src=https://imgur.com/Z5OAsVI.png" height="60%" width="60%" alt>
<br />
<br />
Now, the computer will be restarted for the IP address change to take effect. When restarting a Windows Server, a reason must be provided for future records. Since this was an IP address reconfiguration, I selected "Operating System: Reconfiguration (Planned)."  <br/>
<img src=https://imgur.com/0TKpGD8.png" height="40%" width="40%" alt>
<br />
<br />
The name change was applied.  <br/>
<img src=https://imgur.com/ja7AloT.png" height="30%" width="30%" alt>
<br />
<br />
I navigated to Manage > Add Roles and Features. The Add Roles and Features wizard in Windows Server 2016 allows for the installation and configuration of server roles, role services, and features that enhance the server's functionality.  <br/>
<img src=https://imgur.com/e9JpWPU.png" height="40%" width="40%" alt>
<br />
<br />
<br/>
<img src="https://imgur.com/4RUQyYg.png height="80%" width="80%" alt>
<br />
<br />
Select Role-based or feature-based installation.  <br/>
<img src="https://imgur.com/b36tZZM.png height="80%" width="80%" alt>
<br />
<br />
.  <br/>
<img src="https://imgur.com/EAMO5Y6.png height="80%" width="80%" alt>
<br />
<br />
Active Directory Domain Services (AD DS) must be selected to add it to the server.  <br/>
<img src="https://imgur.com/cVW2fHj.png height="80%" width="80%" alt>
<br />
<br />
For now, only the on-premises server is being installed in this scenario <br/>
<img src="https://imgur.com/vYkXu9e.png height="80%" width="80%" alt>
<br />
<br />
<br/>
<img src="https://imgur.com/0e65EgS.png height="80%" width="80%" alt>
<br />
<br />
After the features were installed, a notification appears under the pennant. Click on "Promote this server to a domain controller."  <br/>
<img src="https://imgur.com/1eo5EpE.png height="45%" width="45%" alt>
<br />
<br />
This is a brand-new server and is not being added to an existing forest. The root domain name has also been selected.  <br/>
<img src="https://imgur.com/lsvCiQz.png height="80%" width="80%" alt>
<br />
<br />
Create a Directory Services Restore Mode (DSRM) password. This password is required to restore Active Directory from a backup in the event of a system failure or other issues.  <br/>
<img src="https://imgur.com/mHotZQr.png height="80%" width="80%" alt>
<br />
<br />
DNS is not installed on this server; however, Active Directory will handle the DNS configuration automatically during the promotion process.  <br/>
<img src="https://imgur.com/gXR1SwE.png height="80%" width="80%" alt>
<br />
<br />
 Name the NetBIOS domain. The NetBIOS domain is a legacy naming convention used by Windows to identify a domain in a network. It is based on the NetBIOS (Network Basic Input/Output System) protocol, which was widely used in earlier Windows environments for network communication and resource sharing.
<br />
<br />
Why It's on Server 2016:
NetBIOS support is included in Windows Server 2016 to ensure backward compatibility. Many older systems and applications still rely on NetBIOS for domain identification. By maintaining NetBIOS domain support, Server 2016 ensures seamless integration with older devices, networks, and applications.<br/>
<br />
<br />
 Locations where the logs and files will be stored.
<img src="https://imgur.com/vWpkpEu.png height="80%" width="80%" alt>
<br />
<br />
Reviewing the changes before proceeding.<br/>
<img src="https://imgur.com/0fsfam8.png height="80%" width="80%" alt>
<br />
<br />
Blue: This message indicates that the server supports older encryption protocols, allowing compatibility with legacy NT servers, enabling them to interact with the domain.
<br />
Green: This message explains that Active Directory will automatically install DNS, which is necessary to establish a database for domain management and name resolution.
<br />
<img src="https://imgur.com/r5VlwoG.png height="80%" width="80%" alt>
<br />
<br />
Once the installation is complete, the server will automatically restart.  <br/>
<img src="https://imgur.com/ajhxW7i.png height="80%" width="80%" alt>
<br />
<br />
GPSVC (Group Policy Client Service) is a Windows service responsible for processing and applying Group Policy settings for users and computers within an Active Directory environment. It ensures that security policies, configurations, and restrictions are applied during startup, login, and refresh intervals. For example, GPSVC can enforce a password policy that requires users to change their password after a specified period.  <br/>
  <br/>
<img src="https://imgur.com/C5aQzba.png height="80%" width="80%" alt>
<br />
<br />
 After the restart was completed, it was confirmed that the DNS records had appeared.
<img src="https://imgur.com/BKxxrcA.png height="80%" width="80%" alt>
<br />
<br />
The Active Directory Users and Computers console has appeared.  <br/>
<img src="https://imgur.com/QCtlxfl.png height="50%" width="50%" alt>
<br />
<br />
Now that the server (WA-LAB) is set up, we need to configure the server's address as the DNS server on the Windows computer. Without this, the computer will be unable to join the domain. Open the Start menu, click on Settings, then go to Network & Internet, and select Ethernet.
  <br/>
 <img src="https://imgur.com/263rExf.png height="40%" width="40%" alt>
 <br/>
 <img src="https://imgur.com/pSx4KQj.png height="80%" width="80%" alt>
 <br/>
 <img src="https://imgur.com/48mCD69.png height="80%" width="80%" alt>
<br />
<img src="https://imgur.com/bDbcuXQ.png height="80%" width="80%" alt>
<br />
Select Manual from the drop-down, enter the server's IP address under Preferred DNS, and click Save.
<img src="https://imgur.com/mblk7hl.png height="50%" width="50%" alt>
<br />
<br />
Rename the Windows 11 computer.<br/>
<img src="https://imgur.com/LeRU12V.png height="50%" width="50%" alt>
<br />
<br />
Now, the computer needs to be joined to the domain. Navigate to Settings<br/>
<img src="https://imgur.com/dEao5GA.png height="30%" width="30%" alt>
<br />
<br />
Navigate to System and scroll down to About.<br/>
<img src="https://imgur.com/i7KhqUQ.png height="50%" width="50%" alt>
<br />
<br />
Click on “Domain or workgroup”<br/>
<img src="https://imgur.com/9RniEKD.png height="30%" width="30%" alt>
<br />
<br />
Click "Change"<br/>
<img src=https://imgur.com/FK1Dy8h.png height="50%" width="50%" alt>
<br />
<br />
After entering the domain name assigned to the server, the system prompts for the administrator username and password. Upon successful authentication, a confirmation message appears indicating that the server has joined the domain.<br/>
<img src="https://imgur.com/TLkgUea.png height="30%" width="30%" alt>
<br />
<br />
The computer must be restarted for the changes to take effect.<br />
<img src="https://imgur.com/CtIvLX5.png height="30%" width="30%" alt>
<br/>
<br />
 To verify the connection to the server, use the administrator credentials created on the server (e.g., domain\administrator). A successful login confirms that the computer has been joined to the domain.<br />
<img src="https://imgur.com/oBrsARB.png height="50%" width="50%" alt>
<br />
<br />












 
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
