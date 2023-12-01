<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1> Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines </h1>
This project will be a walkthrough on how I observed various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. The intended goal of this project is to provide me with a greater understanding of how to create and use resources in Microsoft Azure. Additionally, show me hands-on how network traffic is transmitted and received between virtual machines. <br />


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
<img src= "https://github.com/John-Gravitt/azure-network-protocols/assets/152338722/f941701e-a82c-433f-84c7-5de86d2193ad" height="80%" width="80%" />
</p>
<p>
Log onto the Windows 10 virtual machine using Remote Desktop. Use the username and password that was set when the virtual machine was created.
</p>
<br />

<p>
<img src= "https://github.com/John-Gravitt/azure-network-protocols/assets/152338722/7bf17f84-b312-4734-ad75-698e162e0c9f" height="80%" width="80%" />
</p>
<p>
Now in the Windows virtual machine, download and install WireShark from a web browser. Then open WireShark and Command Prompt.
</p>
<br />

<p>
<img src= "https://github.com/John-Gravitt/azure-network-protocols/assets/152338722/d9c84191-1de9-4cc8-a229-b6ed37c176ac" height="80%" width="80%" />
</p>
<p>
In WireShark filter for ICMP (no port) traffic by using the search bar at the top and then observe the ICMP traffic when sending a ping from Command Prompt to the private IP Address for the second virtual machine (10.0.0.5).
</p>
<br />

<p>
<img src= "https://github.com/John-Gravitt/azure-network-protocols/assets/152338722/5df43769-8f37-4d22-b1f0-e15f93edb9da" height="80%" width="80%" />
</p>
<p>
To stop ICMP traffic from being received by virtual machine #2 (10.0.0.5), use the Network Security Group within Azure to set up a firewall rule to prevent inbound ICMP traffic. Observe that ICMP traffic will fail when sending a perpetual ping to virtual machine #2.
</p>
<br />

<p>
<img src= "https://github.com/John-Gravitt/azure-network-protocols/assets/152338722/688d48b8-0f7f-4ace-ab3e-87f1dfc0ccfb" height="80%" width="80%" />
</p>
<p>
Filter for SSH (tcp.port == 22) in WireShark. Using Command Prompt in virtual machine #1, login to virtual machine #2 by issuing the command ssh username@10.0.0.5 and then entering the password. Observe SSH traffic in WireShark when sending commands via the ssh login.
</p>
<br />

<p>
<img src= "https://github.com/John-Gravitt/azure-network-protocols/assets/152338722/dd42d3e8-8ef6-439f-84aa-f1016a7550aa" height="80%" width="80%" />
</p>
<p>
Filter for DHCP (udp.port == 67/68) in WireShark. Send the command ipconfig /renew on virtual machine #1. Observe that DHCP traffic via WireShark as the IP Address for virtual machine #1 is renewed.
</p>
<br />

<p>
<img src= "https://github.com/John-Gravitt/azure-network-protocols/assets/152338722/c25eb921-da8e-44a1-9c08-d7cb29326bfa" height="80%" width="80%" />
</p>
<p>
Filter for DNS (udp.port == 53) in WireShark. Send the command nslookup www.google.com or any website name on virtual machine #1. Observe the DNS traffic via WireShark as the computer reaches out to the server to identify the IP Address.
</p>
<br />

<p>
<img src= "https://github.com/John-Gravitt/azure-network-protocols/assets/152338722/eed633cd-0fed-4ee2-8ad0-1cf98d7f2e0d" height="80%" width="80%" />
</p>
<p>
Filter for RDP (tcp.port == 3389) in WireShark. Observe that any input to the computer sends RDP traffic because Remote Desktop Connection is being used to access the virtual machine.
</p>
<br />

<p>
<img src= "https://github.com/John-Gravitt/azure-network-protocols/assets/152338722/42c407d8-2f3c-4aa8-b5a4-800f845257ca" height="80%" width="80%" />
</p>
<p>
Navigate back to Azure and go to the resource group page. Delete all resource groups used in the project. All resources (virtual machines) within the resource groups will be subsequently deleted. This removal is essential to prevent accruing costs under the Azure subscription.
</p>
<br />
