<h1>Failed RDP to IP Geolocation Information</h1>

<h2>Description</h2>
<b>The Powershell script in this repository is responsible for parsing out Windows Event Log information for failed RDP attacks and using a third party API to collect geographic information about the attackers location.
</b>
<br />
<br />
<h2>Utilities Used</h2>
- <b>PowerShell:</b> <b>Extract RDP failed logon logs from Windows Event Viewer
</b><br />
- <b>ipgeolocation.io:</b> <b>IP Address to Geolocation API
</b>
<br />
<br />
The script is used where I setup Azure Sentinel (SIEM) and connect it to a live virtual machine acting as a honey pot.
We will observe live attacks (RDP Brute Force) from all around the world. I will use a custom PowerShell script to
look up the attackers Geolocation information and plot it on an Azure Sentinel Map!
<br />
<br />

<h2>Event Viewer shows IpAddress 197.33.31.42 as the Event 4625 failed login location</h2>

<p align="center">
<img src="https://i.imgur.com/V9nXM2E.png" height="85%" width="85%" alt="Image Analysis Dataflow"/>
</p>

<h2>Using https://ipgeolocation.io as our API, we grab the ipaddress location</h2>

<p align="center">
<img src="https://i.imgur.com/KAXzX4N.png" height="85%" width="85%" alt="Image Analysis Dataflow"/>
</p>
<br />


<h2>Only 30 min. online and hundreds of attacks are coming in</h2>

<p align="center">
<img src="https://i.imgur.com/Awbnrb3.png" height="85%" width="85%" alt="Image Analysis Dataflow"/>
</p>

<h2>Attacks from Egypt coming in; Custom logs being output with geodata</h2>

<p align="center">
<img src="https://i.imgur.com/G91iH3E.png" height="85%" width="85%" alt="Image Analysis Dataflow"/>
</p>

<h2>World map of incoming attacks after 24 hours (built custom logs including geodata)</h2>

<p align="center">
<img src="https://i.imgur.com/6jsplpo.png" height="85%" width="85%" alt="Image Analysis Dataflow"/>
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
