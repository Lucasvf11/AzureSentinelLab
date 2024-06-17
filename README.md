# AzureSentinelLab - Failed RDP to IP Geolocation Information

<h2>Description</h2>
In this lab, I setup a virtual machine in Azure and disable its firewall so that it acts as a honeypot. I then setup Azure Sentinel (SIEM) and connect it to the live VM.
<br />
After some time, the VM will start to suffer attacks. We observe live attacks (RDP Brute Force | Windows Event ID = 4625) from all around the world. I use a PowerShell script to look up the attackers' Geolocation information and gather the data to a custom log file. 
<br />
Subsequently, I parse the logs and create a Sentinel workbook to show the events in a world map, plotted by latitude and longitude and number of events.
<br />
<br />
The Powershell script in this repository is responsible for parsing out Windows Event Log information for failed RDP attacks and using a third party API to collect geographic information about the attackers location.
<br />
<br />


<h2>Languages Used</h2>

- <b>PowerShell:</b> Extract RDP failed logon logs from Windows Event Viewer 

<h2>Utilities Used</h2>

- <b>ipgeolocation.io:</b> IP Address to Geolocation API

<h2>Attacks coming in; Custom logs being output with geodata</h2>

<p align="center">
<img src="https://imgur.com/PDoonjk.png" height="85%" width="85%" alt="PowerShell Output"/>
</p>

<h2>Parsing the logs at Azure</h2>

<p align="center">
<img src="https://imgur.com/M1Ryqi3.png" height="85%" width="85%" alt="PowerShell Output"/>
</p>

<h2>World map of incoming attacks after 24 hours</h2>

<p align="center">
<img src="https://imgur.com/UBNM2K7.png" height="85%" width="85%" alt="Geolocation Map"/>
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
