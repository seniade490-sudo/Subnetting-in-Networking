# Subnetting-in-Networking
Subnetting with Cisco Packet Tracer
subnet the current subnet (192.168.1.0/24) into two subnets with as many hosts as possible :-

192.168.1.0 / cidr 24 = 2n = N; 255.255.255.0 /24;
2 raise to the power of 1 is 2, we would have 2 networks, 
for the first network we would have 192.168.1.1 /cidr 25, borrowed host of 1 bit = 128;
subnet mask would be 192.168.1.128 /25
192.168.1.0 = 1stNetwork = 192.168.1.1 /25; LastNetwork = 192.168.1.126; BroadcastNetwork = 192.168.1.127
192.168.1.128 = 1stNetwork = 192.168.1.129 /25; LastNetwork = 192.168.1.254 /25; BroadcastNetwork = 192.168.1.255 /25

First subnet on the left S1; 
Second subnet on the right S2;
1st subnet is 192.168.1.1 : 192.168.1.126;
2nd subnet is 192.168.1.129 : 192.168.1.254;

configure PC's with first IP address in subnet :- 
PC1 ipaddress : 192.168.1.1
PC1 subnetmask : 255.255.255.128
PC1 default-gateway : 192.168.1.126
PC2 ipaddress : 192.168.1.129
PC2 subnetmask : 255.255.255.128
PC2 default-gateway : 192.168.1.254

configure Router with last IP address in subnet :- 
R1 ipaddress : int g0/0/0 192.168.1.126
R1 ipaddress : int g0/0/1 192.168.1.254

The Router is connected between switches, serving as the default gateway for PC and switch;

Configure Switches with second last IP address in subnet :-
SW1 : int vlan 1 = 192.168.1.125, default gateway = 192.168.1.126
SW2 : int vlan 1 = 192.168.1.253, default gateway = 192.168.1.254

All devices can ping each other within the network.

