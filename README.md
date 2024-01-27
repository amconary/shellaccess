<h1>Gain Shell Access</h1>

 <h2>Description</h2>
Project consists of performing techniques to gain shell access to a machine on a vulnerable Windows home lab.
<br />


<h2>Languages and Utilities Used</h2>

- <b>Metasploit</b> 
- <b>Impacket-psexec</b>

<h2>Environments Used </h2>

- <b>Kali Linux</b>

<h2>Project walk-through:</h2>

<p align="center">
Gaining Shell Access 
<br />
<br />
First we will start up Kali Linux and open a terminal and run msfconsole to start up Metasploit. <br />
<img src="https://i.imgur.com/1XujfEu.png" height="80%" width="80%" alt="ShellAccess"/>
<br />
<br />
We are going to attempt to use the hashes we gathered previously from SMB to gain access. Lets search the exploits to see if we can find one that will help us accomplish that. <br />
Using “search type:exploit smb” we can list all the modules we can use for SMB:  <br/>
<img src="https://i.imgur.com/5TPvC5u.png" height="60%" width="60%" alt="ShellAccess"/>
<br />
<br />
We are going to use the smb/psexec option. Next we will need to set the options. <br />
Set all of your options according to your environment and run the exploit:  <br/>
<img src="https://i.imgur.com/FAeX4p2.png" height="60%" width="60%" alt="ShellAccess"/>
<br />
<br />
The exploit completed successfully and we gained a meterpreter shell on the Win 10 VM. <br />
Here is the same exploit except this time we are using the local Administrator account and the hash that we grabbed previously in our SMB relay attack.  <br/>
<img src="https://i.imgur.com/Aww1zfS.png" height="60%" width="60%" alt="ShellAccess"/>
<br />
<br />
We can also utilize the credential info we obtained to perform the same attack using impacket-psexec to gain shell access:  <br/>
<img src="https://i.imgur.com/9zKZ00k.png" height="60%" width="60%" alt="ShellAccess"/>
<br />
<br />
Using the password hash will also work for the impacket-psexec technique: <br />
<img src="https://i.imgur.com/SEhFrKa.png" height="60%" width="60%" alt="ShellAccess"/> 
<br />
<br />
We successfully gained shell access to the target machine!
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
