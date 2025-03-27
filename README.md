<h1>Deploying a Windows Server and Configuring Active Directory</h1>

<h2>Scenario </h2>
Your organization needs a new Windows Server 2016 to act as a Domain Controller (DC) for managing user authentication, security policies, and devices. In this lab, you will set up a Windows Server 2016 virtual machine, configure Active Directory Domain Services (AD DS), and promote it to a Domain Controller.
<br />

<h2>Environments Used </h2>

- <b>Hyper-V</b>
- <b>Windows Server 2016</b>
- <b>Windows 11</b>

<h2>Install and configure Windows Server 2016:</h2>

<p align="center">
<br/>
<img src="https://imgur.com/wNaj3cd.png" height="130%" width="130%" alt="Disk Sanitization Steps"/>
<br />
<br />
 <br />
I’m renaming the machine, but notice that I haven’t assigned it to a domain yet, as a domain will be created.<br/>
<img src="https://imgur.com/WLLrXXK.png" height="130%" width="130%" alt="Disk Sanitization Steps"/>
<br />
<br />
The computer needs to be restarted for the name change to take effect, but I chose to click "Restart Later" so I can first review the network settings. <br/>
<img src="https://imgur.com/vRWevEt.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<br />
<br />
Go to Start > Settings > Network & Internet > :  <br/>
<img src="https://imgur.com/fckBPyk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
