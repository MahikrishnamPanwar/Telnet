Project Overview

This project demonstrates the configuration of Telnet remote access on Cisco networking devices using Cisco Packet Tracer.

The purpose of this project is to understand how network administrators can remotely access and manage Cisco routers and switches through the Command-Line Interface (CLI).

🎯 Objectives
Understand the basics of Telnet.
Configure remote access on Cisco routers and switches.
Configure usernames and passwords for authentication.
Configure Virtual Terminal (VTY) lines.
Access network devices remotely from a PC.
Verify connectivity and troubleshoot configuration issues.
🛠️ Tools and Technologies
Simulation Tool: Cisco Packet Tracer
Devices: Cisco Router, Switch, and PC
Protocol: Telnet
Configuration Interface: Cisco IOS CLI
Networking Concepts: IPv4 addressing, authentication, and remote device management

🗺️ Network Topology

The project uses a PC connected to a Cisco networking device through a network connection.

Example topology:

+---------+          +----------------+
|   PC    |----------| Cisco Router   |
|         |          |                |
+---------+          +----------------+
     |                       |
     +--- Telnet Access -----+

The PC uses the router's IP address to initiate a Telnet session.

Note: The diagram is illustrative. Your actual Packet Tracer topology may differ.

⚙️ Configuration Steps
Step 1: Configure the Router Interface

Enter privileged EXEC mode and global configuration mode.

Router> enable
Router# configure terminal

Configure the router interface connected to the network.

Router(config)# interface gigabitEthernet 0/0
Router(config-if)# ip address 192.168.1.1 255.255.255.0
Router(config-if)# no shutdown
Router(config-if)# exit
Step 2: Configure a Username and Password

Create a local user account for authentication.

Router(config)# username admin secret Admin@123

This command creates a local user named admin with an encrypted password stored in the device configuration.

Step 3: Configure Telnet Access

Configure the Virtual Terminal (VTY) lines.

Router(config)# line vty 0 4
Router(config-line)# login local
Router(config-line)# transport input telnet
Router(config-line)# exit

Command explanation:

line vty 0 4: Selects the VTY lines numbered 0 through 4.
login local: Uses the locally configured username and password.
transport input telnet: Allows incoming Telnet connections.
Step 4: Configure the PC

Configure the PC's IPv4 settings in Cisco Packet Tracer.

Setting	Example Value
IP Address	192.168.1.2
Subnet Mask	255.255.255.0
Default Gateway	192.168.1.1

The PC and router must have compatible IP configurations and network connectivity.

Step 5: Test Connectivity

From the PC's Command Prompt, test connectivity to the router.

ping 192.168.1.1

If connectivity is working, initiate a Telnet session.

telnet 192.168.1.1

Enter the configured username and password when prompted.

If authentication succeeds, the PC should access the router's CLI remotely.

🔍 Verification Commands

Use these commands on the router to verify the configuration.

Command	Purpose
show ip interface brief	Checks interface IP addresses and status
show running-config	Displays the active configuration
show users	Displays active terminal sessions
show line	Displays terminal line information
ping 192.168.1.2	Tests connectivity to the PC


⭐ If you find this project useful, consider giving the repository a star!

Thank you for visiting my project.
