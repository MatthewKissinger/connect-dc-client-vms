<p align="center">
  <img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Microsoft Azure Tutorial</h1>
<h2>Establish connection between Domain Controller and Client VMs</h2>
<p>This tutorial outlines the prerequisites and the process of establishing a connection between a Domain Controller and Client virtual machines in the cloud computing platform Microsoft Azure with Microsoft Remote Desktop Connection.</p> 

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Computer) online portal
- Windows 10 / 11 OS
- Remote Desktop Connection App
- Windows Powershell
- Windows File Explorer

<h2>Operating Systems Used </h2>

- Windows 10 / 11

<h2>List of Prerequisites</h2>

- Microsoft Azure Account (Free version of $200 credits available)
- Personal Computer running Windows 10 or 11
- Completed Part 1 of my tutorial series (https://github.com/MatthewKissinger/vm-ad-setup)
- Completed Part 2 of my tutorial series (https://github.com/MatthewKissinger/rmdc-to-azure-vm)

<h3>We will first learn about Ping and ICMP before tackling the tutorial.</h3>

<h2>What does the Ping Command do?</h2>
<p>Ping is an internet program command that tests if an IP address exists and is able to accept ICMP requests.</p>
<p>We will be using it in this tutorial to verify that the Domain Controller and Client computers are able to communicate and share a network together.</p>

<h2>What is ICMP (Internet Control Message Protocol)?</h2>
<p>ICMP is a protocol on the network layer used by network devices to diagnose communication issues. </p>
<p>The ping command operates using ICMP. In order to use ping to request a connection we will have to activate ICMPv4 on the Domain Controller.</p>

<h3> 1) Connect to both the DC-1 and Client-1 Virtual Machines via Remote Desktop Connection</h3>

<p>If you haven't already, here are the steps to do so in the previous tutorial: (https://github.com/MatthewKissinger/rmdc-to-azure-vm) </p>

<h3>2) Ping DC-1 from Client-1's powershell command line interface</h3>

<p>Copy DC-1's private IP address from the Virtual Machine screen in Microsoft Azure's online Portal</p>

![image](https://github.com/MatthewKissinger/connect-dc-client-vms/assets/48774883/a46a1311-f08b-4cd5-9888-562bb497aa0d)

<p>The Private IP Address of my DC-1 says 10.0.0.4 (yours may be different)</p>

<p>From the Remote Connection of Client-1, open Windows Powershell and ping DC-1's Private IP address [my example below]</p>

![image](https://github.com/MatthewKissinger/connect-dc-client-vms/assets/48774883/12ef79ed-cb61-45ab-809b-fb69c04b975f)

<p>Since we haven't enabled ICMPv4 in the Domain Controller's Windows Firewall, we should see a 100% loss in packets Received.</p>

![image](https://github.com/MatthewKissinger/connect-dc-client-vms/assets/48774883/889fcd54-aecc-4872-a2d7-32e3303978a2)

<h3>3) Enable ICMPv4 Communication Protocol in the Domain Controller Virtual Machine</h3>

<p>In your Domain Controller Virtual Machine type wf.msc in the windows search bar</p>

<p>This search command will pull up the Windows Defender Firewall with Advanced Security. Open the program.</p>

![image](https://github.com/MatthewKissinger/connect-dc-client-vms/assets/48774883/d8803abb-cbc1-4018-ab39-ec0d0a7b27a1)

<p>Click on Inbound Rules</p>

![image](https://github.com/MatthewKissinger/connect-dc-client-vms/assets/48774883/a55c6d52-e7c1-4a44-bf13-d5012b5f7458)

<p>And then click on the Protocol Column at the top to sort by protocol</p>

![image](https://github.com/MatthewKissinger/connect-dc-client-vms/assets/48774883/f854ee72-d299-42bb-9089-ba9e0c59d930)

<p>Only one of the ICMPv4 Protocols are enabled by default: Core Networking - Destination Unreachable</p>

![image](https://github.com/MatthewKissinger/connect-dc-client-vms/assets/48774883/dd4e03fa-3fb6-437a-81ff-5667ef6bfde5)

<p>Right click on each ICMPv4 Inbound Rule and select Enable Rule from the popup menu. </p>

<p>Your ICMPv4 Rules should now all have a green checkmark like this: </p>

![image](https://github.com/MatthewKissinger/connect-dc-client-vms/assets/48774883/65e451b9-7680-4484-b332-4b16c9ca4ccb)

<p>Now with the ICMPv4 Inbound Rules enabled head back into your Client-1 virtual machine</p>

<p>And ping the Private IP Address of the Domain Controller again</p>

![image](https://github.com/MatthewKissinger/connect-dc-client-vms/assets/48774883/c3510a41-06eb-460e-98fa-720fee50f2a4)

<p>With ICMPv4 enabled on the Domain Controller you should see a 0% loss in packets Sent and Received. </p>

![image](https://github.com/MatthewKissinger/connect-dc-client-vms/assets/48774883/977e882c-3074-4d63-ba77-1d7c9137a7c9)

<p>Now the Domain Controller and Client-1 computers can communicate on the network and allow other services like Active Directory to be enabled.</p>

<h4>Thank you for following along!</h4>
  
<p>In the next tutorial we will be connecting ensuring a connection between the 2 virtual machines</p>
