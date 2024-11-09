# SIEM-and-Threat-Intelligence-Feed



<h2>Description</h2>
Enhancing security monitoring within a cloud environment by leveraging Microsoft Azure and Microsoft Sentinel. Created a virtual machine (VM) in Microsoft Azure and enabled Remote Desktop Protocol (RDP) access, setting up an environment that could be monitored for specific security events. Fed the honeypot threats using MISP server. 
<br />


<h2>Languages and Utilities Used</h2>

- <b>Python</b> 


<h2>Environments Used </h2>

- <b>Windows 11 Pro</b> (22H2)
- <b>Linux Ubuntu</b>
- <b>Azure Sentinel<b>

<h2>Program walk-through:</h2>

<p align="center">
Create VM<: <br/>
<img src="https://imgur.com/XiRO8Fp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
 <p align="left">
- <b>Leave rdp port 3389 open</b> 
<br />
   <br />
   <br />
<p align="center">
Create Sentinel:  <br/>
<img src="https://imgur.com/clb4iQX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 
  <p align="left">
- <b>Add Sentinel to the same resource group as vm</b> 
<br />
    <br />
<br />
<p align="center">
Add Log Analytics to Sentinel: <br/>
<img src="https://imgur.com/dNyBUM9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
Add Data Connectors:  <br/>
<img src="https://imgur.com/lfmdoj7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p align="left">
- <b>Add data collectionrule</b>
<br />
- <b>Select VM and select "All Security Events"</b> 
<br />
    <br />
<br />
<p align="center">  
<br />
Create Sentinel rule that checks for successful sign-ins via rdp:  <br/>
<img src="https://imgur.com/4fjDtaE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p align="left">
- <b></b>
<br />
<br />
    <br />
<br />
<p align="center">  
<br />
SIEM successfully deployed:  <br/>
<img src="https://imgur.com/NFLpw3g.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
  <br />
  <br />
<br />
Create MISP server:  <br/>
<img src="https://imgur.com/qo9kPxQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
 <p align="left">
- <b>Create Ubanto VM to host MISP server</b>
  <br />
- <b>Install MISP docker</b>
  <br />
- <b>Verify port 443 is open in VM to enable access</b>   
<br />
<br />
    <br />
<br />
<p align="center">  
<br /> 
<br />
Enable Feed: <br/>
<img src="https://imgur.com/XnXPPB7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
In Sentinel select the MISP Data Connector:  <br/>
<img src="https://imgur.com/pGxkeUY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Register new Application to upload indicator API: <br/>
<img src="https://imgur.com/Y7OZV3R.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Create Function App: <br/>
<img src="https://imgur.com/oO5OJaw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
 <p align="left">
- <b>This app will allow to pull from MISP directly into Sentinel</b> 
<br />
   - <b>Select Python</b>
    <br />
<br />
<p align="center">  
<br />
Deploy Python script to Function App:  <br/>
<img src="https://imgur.com/URtpQLL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Assign Variable Values: <br/>
<img src="https://imgur.com/w1ASIup.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Threat Intelligence Indicators successful:  <br/>
<img src="https://imgur.com/MFoGt0W.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
 <p align="left">
- <b>With the indicators running successfully you can create alerts</b> 
<br />
 - <b>Create custom indicators using rdp</b>   
    <br />
<br />
<p align="center">  
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
