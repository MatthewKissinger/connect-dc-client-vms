<p align="center">
  <img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Microsoft Azure Tutorial</h1>
<h2>Establish connection between Domain Controller and Client VMs</h2>
<p>This tutorial outlines the prerequisites and the process of establishine a connection between a Domain Controller and Client virtual machines in the cloud computing platform Microsoft Azure with Microsoft Remote Desktop Connection.</p> 

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
<p>Ping ...</p>

<h2>What is ICMP (Internet Control Message Protocol)?</h2>
<p>ICMP ...</p>


  
<h3> 1) Connect to both the DC-1 and Client-1 Virtual Machines via Remote Desktop Connection</h3>
<p>If you haven't already, here are the steps to do so in the previous tutorial: (https://github.com/MatthewKissinger/rmdc-to-azure-vm) </p>



<h3>2)Ping DC-1 from Client-1's powershell command line interface</h3>

<p>Copy DC-1's private IP address from the Virtual Machine screen in Microsoft Azure's online Portal</p>

![image](https://github.com/MatthewKissinger/connect-dc-client-vms/assets/48774883/a46a1311-f08b-4cd5-9888-562bb497aa0d)

<p>The Private IP Address of my DC-1 says 10.0.0.4 (yours may be different)</p>

<p>From the Remote Connection of Client-1, open Windows Powershell</p>




<h4>Thank you for following along!</h4>
  
<p>In the next tutorial we will be connecting ensuring a connection between the 2 virtual machines</p>
