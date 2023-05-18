<p align="center">
<img src="https://i.imgur.com/tMxbbpd.png alt="Sentinel logo"/>
</p>

<h1> Running Queries (KQL) in Log Analytics Workspaces </h1>
This Lab goes along with our HoneyNet lab. Running a few KQL queries to get data from our unprotected Window VM's.<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines)
- Remote Desktop
- KQL
- Log Analytics Workspace
- Microsoft Sentinel
- Microsoft Cloud Defender 
- Powershell
- Visual Studio Code

<h2>Operating Systems Used </h2>

- MAC OS / Windows 10 (VM)


<h2> Lab Summary </h2>

<p>
<img src="https://i.imgur.com/84KjF7t.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Installing Azure Module for Powershell. This allows us to make commands in Powershell through our Windows VM.
</p>
<br />

<p>
<img src="https://i.imgur.com/6JB1nmf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Simulating a BRUTE FORCE ATTACK to our open Windows VM. The code loops 11 times simulating failed log in attempts. 
</p>
<br />

<p>
<img src="https://i.imgur.com/CHnVqQF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Configured logging for Key Vault instance by enabling dianostic settings and sending it to our Log analytics Workspace instance. 
</p>
<br />

<p>
<img src="https://i.imgur.com/Aq89IUt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 From our Windows Security Event Log in our Windows VM. We get every EventID that equals to 4625. EventID 4625 indicates failed log-in attempts.
</p>
<br />

<p>
<img src="https://i.imgur.com/iA7AyeA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Same as the log above this just shows our 4625 EventId's from Window's Security Event Log as a graph instead. 
</p>
<br />

<p>
<img src="https://i.imgur.com/M1Tj4iX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Here in this query we pull Azure Activity Logs. Upon opening and researching an event we can look at its data like the IP address its associated with. 
</p>
<br />

<p>
<img src="https://i.imgur.com/3cfBsWK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 This query opens up our logs for our Azure Storage Account HoneyNetStorage. 
</p>
<br />

<p>
<img src="https://i.imgur.com/V6Dmo0G.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Azure Active Directory query that produces Mass Authorization failures. Also giving us locations / IP Address / Country / etc. to further help our investigation.
</p>
<br />

<p>
<img src="https://i.imgur.com/dWYMrHW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 This query pulls the data from the attack on our Key Vault instance.  We attempted to retrieve the Key Vaults secret password from our Attacker VM.  
</p>
<br />

<p>
<img src="https://i.imgur.com/jN096mJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Above are various KQL query's that you can use in Log Analytics Workspaces to produce important data in researching alerts or creating new rules. The purpose of each query is commented out above. 
                                                                                                 
