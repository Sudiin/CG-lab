Set 1 Q1 Crete 2 vlans 
1. Create topology: 1 switch + 4 PCs.
2. Create VLANs:
	vlan 2
	vlan 3
3. Assign Fa0/1–2 → VLAN 2:
	interface range fa0/1-2
	switchport mode access
	switchport access vlan 2
4. Assign Fa0/3–4 → VLAN 3:
	interface range fa0/3-4
	switchport mode access
	switchport access vlan 3
5. Configure IPs: 10.0.0.1–10.0.0.4.
6. Verify:
	show vlan brief
7. Ping PCs in the same VLAN to verify communication.

==============================================

Set 1 Q 2 
1. Create topology: 1 Server + 1 Switch + PCs/Laptops and connect them.
2. Set Server → Desktop → IP Configuration:
	IP: 192.168.1.2
	Subnet Mask: 255.255.255.0
3. Go to Server → Services → DHCP and turn DHCP ON.
4. Create the DHCP pool:
	Pool Name: LAN
	Default Gateway: 192.168.1.1
	Start IP: 192.168.1.10
5. On each PC/Laptop: Desktop → IP Configuration → DHCP.
6. Verify that devices receive IP addresses automatically.
7. Test using Command Prompt → ipconfig or ping between devices.
===========================================

Set 2 q 1
1. Create topology: 2 routers, 2 switches, 4 PCs and connect them.
2. Assign IP addresses as shown in the diagram.
3. Configure Router 0:
	enable
	conf t
	router rip
	version 2
	network 192.168.1.0
	network 192.168.3.0

4.Configure Router 1:
	enable
	conf t
	router rip
	version 2
	network 192.168.2.0
	network 192.168.3.0

5. Configure PCs with their respective IP addresses and subnet mask 255.255.255.0.
6. Set default gateways:
	PC0/PC1 → 192.168.1.4
	PC2/PC3 → 192.168.2.4
7.Verify RIP
8. Check by pinging

======================================

Set 2 q 2
1. Create topology: 2 switches + 4 PCs and connect the switches.
2. Create VLANs 2 (Sales) and 3 (Marketing) on both switches.
3. Assign PC ports to their respective VLANs.
4. Configure the link between switches as a trunk:
	interface fa0/24
	switchport mode trunk
5. Repeat the trunk configuration on both switches.
6. Assign IPs:
	VLAN 2 → 10.0.0.2, 10.0.0.12
	VLAN 3 → 10.0.0.3, 10.0.0.13
7. Verify trunk:
	show interfaces trunk
8. Ping devices
