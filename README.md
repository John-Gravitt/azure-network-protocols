<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1> Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines </h1>
In this project, I will observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. This project will provide me with a greater understanding of how to create and use resources in Microsoft Azure. Also, it will show me hands-on how network traffic is transmitted and received between virtual machines. <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Create a resource group within Azure subscription including a virtual machine running Windows 10 and another virtual machine running Linux Ubuntu.
- Generate a perpetual ping from one virtual machine to the other and use the Network Security Group within the Azure application to disable inbound ICMP traffic.
- Observe network traffic (ICMP, SSH, DHCP, DNS, and RDP) between virtual machines using WireShark application.
- Delete resource group and subsequent virtual machines after the lab is completed to prevent Azure subscription costs.

<h2>Actions and Observations</h2>

<p>
<img src= "https://github.com/John-Gravitt/azure-network-protocols/assets/152338722/84a70616-bac0-4daf-bdf7-e54e0ac8d377" height="80%" width="80%" />
</p>
<p>
Begin the project by navigating to Microsoft Azure, then create a resource group within the Azure subscription. Create one virtual machine operating on Windows 10 and another virtual machine operating on Linux Ubuntu. Observe that the NetworkWatcher resource group was created at the same time as the virtual machines.
<br />

<p>
<img src= " " height="80%" width="80%" />
</p>
<p>
Log on and ICMP
</p>
<br />

<p>
<img src= "https://github.com/John-Gravitt/azure-network-protocols/assets/152338722/5df43769-8f37-4d22-b1f0-e15f93edb9da" height="80%" width="80%" />
</p>
<p>
Deny ICMP
</p>
<br />

<p>
<img src= " " height="80%" width="80%" />
</p>
<p>
SSH
</p>
<br />

<p>
<img src= "https://github.com/John-Gravitt/azure-network-protocols/assets/152338722/2d84492d-5266-419c-adf6-cc379284e50e" height="80%" width="80%" />
</p>
<p>
DHCP
</p>
<br />

<p>
<img src= " " height="80%" width="80%" />
</p>
<p>
DNS
</p>
<br />

<p>
<img src= " " height="80%" width="80%" />
</p>
<p>
RDP
</p>
<br />

<p>
<img src= "https://github.com/John-Gravitt/azure-network-protocols/assets/152338722/42c407d8-2f3c-4aa8-b5a4-800f845257ca" height="80%" width="80%" />
</p>
<p>
Delete resource group
</p>
<br />
