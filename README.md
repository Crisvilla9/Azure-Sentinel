<h1>Failed RDP to IP Geolocation Information</h1>

<h2>Description</h2>
<b>Configured Sentinel workbook to display attack data (RDP brute force). Used custom PowerShell script to extract metadata from Windows Event Viewer and forwarded to a third-party API
</b>
<br />
<br />

<h2>Languages Used</h2>

- <b>PowerShell (Custom Script created by Josh Madakor:</b> Extract RDP failed logon logs from Windows Event Viewer

<h2>Utilities Used</h2>

- <b>ipgeolocation.io:</b> IP Address to Geolocation API


<h2>Here is a list of my Resources used in Azure</h2>

<p align="center">
<img src="https://i.imgur.com/uym6xm5.png" height="85%" width="85%" alt="Image Analysis Dataflow"/>
</p>

<h2>This is the website where we get the IP Geolocation API from the original IP gathered in Event Viewer. The Powershell script will then programatically gather that info and send it to log analytics, then to sentinel where it will read the longitude and latitude and plot the attacks on the map</h2>

<p align="center">
<img src="https://i.imgur.com/qCpPANt.png" height="85%" width="85%" alt="Image Analysis Dataflow"/>
</p>

<h2>Here we can see the PowerShell script in action scanning for new attacks exporting them to a hidden file location in my local host, where the script will then gather that info and send it over to Log Analytics </h2>

<p align="center">
<img src="https://i.imgur.com/POoQ5gr.png" height="85%" width="85%" alt="Image Analysis Dataflow"/>
</p>

<h2>A better image of the Geolocation map of each attack, most of my attacks were coming from the Netherlands as you can see below, this recording was a short time frame of roughly 5 minutes.</h2>

<p align="center">
<img src="https://i.imgur.com/DGksZaF.png" height="85%" width="85%" alt="Image Analysis Dataflow"/>
</p>
