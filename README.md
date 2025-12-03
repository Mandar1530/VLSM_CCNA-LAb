Router 0

Router>enable
Router#config t
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#int g0/0
Router(config-if)#ip add 192.168.5.126 255.255.255.128
Router(config-if)#no shutdown

Router(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/0, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/0, changed state to up

Router(config-if)#exit
Router(config)#int g0/1
Router(config-if)#ip add 192.168.5.190 255.255.255.192
Router(config-if)#no shutdown

Router(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/1, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/1, changed state to up

Router(config-if)#exit
Router(config)#
Router(config)#show ip int brief
                ^
% Invalid input detected at '^' marker.
	
Router(config)#do show ip int brief
Interface              IP-Address      OK? Method Status                Protocol 
GigabitEthernet0/0     192.168.5.126   YES manual up                    up 
GigabitEthernet0/1     192.168.5.190   YES manual up                    up 
Serial0/3/0            unassigned      YES unset  administratively down down 
Serial0/3/1            unassigned      YES unset  administratively down down 
Vlan1                  unassigned      YES unset  administratively down down
Router(config)#








Router con0 is now available






Press RETURN to get started.













Router>
Router>enable
Router#config t
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#int s0/3/0
Router(config-if)#ip add 192.168.5.225 255.255.255.252
Router(config-if)#no shutdown

%LINK-5-CHANGED: Interface Serial0/3/0, changed state to down
Router(config-if)#
Router(config-if)#exit
Router(config)#
%LINK-5-CHANGED: Interface Serial0/3/0, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface Serial0/3/0, changed state to up

Router(config)#
Router(config)#
Router(config)#ip route 192.168.5.192 255.255.255.240 192.168.5.226
Router(config)#ip route 192.168.5.208 255.255.255.240 192.168.5.226
Router(config)#do wr
Building configuration...
[OK]
Router(config)#do show ip route
Codes: L - local, C - connected, S - static, R - RIP, M - mobile, B - BGP
       D - EIGRP, EX - EIGRP external, O - OSPF, IA - OSPF inter area
       N1 - OSPF NSSA external type 1, N2 - OSPF NSSA external type 2
       E1 - OSPF external type 1, E2 - OSPF external type 2, E - EGP
       i - IS-IS, L1 - IS-IS level-1, L2 - IS-IS level-2, ia - IS-IS inter area
       * - candidate default, U - per-user static route, o - ODR
       P - periodic downloaded static route

Gateway of last resort is not set

     192.168.5.0/24 is variably subnetted, 8 subnets, 5 masks
C       192.168.5.0/25 is directly connected, GigabitEthernet0/0
L       192.168.5.126/32 is directly connected, GigabitEthernet0/0
C       192.168.5.128/26 is directly connected, GigabitEthernet0/1
L       192.168.5.190/32 is directly connected, GigabitEthernet0/1
S       192.168.5.192/28 [1/0] via 192.168.5.226
S       192.168.5.208/28 [1/0] via 192.168.5.226
C       192.168.5.224/30 is directly connected, Serial0/3/0
L       192.168.5.225/32 is directly connected, Serial0/3/0


Router(config)#
Router(config)#
Router(config)#int s0/3/0
Router(config-if)#ip add 192.168.5.226 255.255.255.252
Router(config-if)#no shutdown

Router(config-if)#
%LINK-5-CHANGED: Interface Serial0/3/0, changed state to up

Router(config-if)#do show ip int 
%LINEPROTO-5-UPDOWN: Line protocol on Interface Serial0/3/0, changed state to up

GigabitEthernet0/0 is up, line protocol is up (connected)
  Internet address is 192.168.5.206/28
  Broadcast address is 255.255.255.255
  Address determined by setup command
  MTU is 1500 bytes
  Helper address is not set
  Directed broadcast forwarding is disabled
  Outgoing access list is not set
  Inbound  access list is not set
  Proxy ARP is enabled
  Security level is default
  Split horizon is enabled
  ICMP redirects are always sent
  ICMP unreachables are always sent
  ICMP mask replies are never sent
  IP fast switching is disabled
  IP fast switching on the same interface is disabled
  IP Flow switching is disabled
  IP Fast switching turbo vector
  IP multicast fast switching is disabled
  IP multicast distributed fast switching is disabled
  Router Discovery is disabled
  IP output packet accounting is disabled
  IP access violation accounting is disabled
  TCP/IP header compression is disabled
  RTP/IP header compression is disabled
  Probe proxy name replies are disabled
  Policy routing is disabled
  Network address translation is disabled
  BGP Policy Mapping is disabled
  Input features: MCI Check
  WCCP Redirect outbound is disabled
  WCCP Redirect inbound is disabled
  WCCP Redirect exclude is disabled
GigabitEthernet0/1 is up, line protocol is up (connected)
  Internet address is 192.168.5.222/28
  Broadcast address is 255.255.255.255
  Address determined by setup command
  MTU is 1500 bytes
  Helper address is not set
  Directed broadcast forwarding is disabled
  Outgoing access list is not set
  Inbound  access list is not set
  Proxy ARP is enabled
  Security level is default
  Split horizon is enabled
  ICMP redirects are always sent
  ICMP unreachables are always sent
  ICMP mask replies are never sent
  IP fast switching is disabled
  IP fast switching on the same interface is disabled
  IP Flow switching is disabled
  IP Fast switching turbo vector
  IP multicast fast switching is disabled
  IP multicast distributed fast switching is disabled
  Router Discovery is disabled
  IP output packet accounting is disabled
  IP access violation accounting is disabled
  TCP/IP header compression is disabled
  RTP/IP header compression is disabled
  Probe proxy name replies are disabled
  Policy routing is disabled
  Network address translation is disabled
  BGP Policy Mapping is disabled
  Input features: MCI Check
  WCCP Redirect outbound is disabled
  WCCP Redirect inbound is disabled
  WCCP Redirect exclude is disabled
Serial0/3/0 is up, line protocol is up (connected)
  Internet address is 192.168.5.226/30
  Broadcast address is 255.255.255.255
  Address determined by setup command
  MTU is 1500
  Helper address is not set
  Directed broadcast forwarding is disabled
  Outgoing access list is not set
  Inbound  access list is not set
  Proxy ARP is enabled
  Security level is default
  Split horizon is enabled
  ICMP redirects are always sent
  ICMP unreachables are always sent
  ICMP mask replies are never sent
  IP fast switching is disabled
  IP fast switching on the same interface is disabled
  IP Flow switching is disabled
  IP Fast switching turbo vector
  IP multicast fast switching is disabled
  IP multicast distributed fast switching is disabled
  Router Discovery is disabled
  IP output packet accounting is disabled
  IP access violation accounting is disabled
  TCP/IP header compression is disabled
  RTP/IP header compression is disabled
  Probe proxy name replies are disabled
  Policy routing is disabled
  Network address translation is disabled
  WCCP Redirect outbound is disabled
  WCCP Redirect exclude is disabled
  BGP Policy Mapping is disabled
Serial0/3/1 is administratively down, line protocol is down (disabled)
  Internet protocol processing disabled
Vlan1 is administratively down, line protocol is down
  Internet protocol processing disabled

Router(config-if)#
Router(config-if)#
Router(config-if)#
Router(config-if)#ip route 192.168.5.0 255.255.255.128 192.168.5.225
Router(config)#no ip route 192.168.5.0 255.255.255.128 192.168.5.225
Router(config)#exit
Router#
%SYS-5-CONFIG_I: Configured from console by console

Router#
Router#enable
Router#config t
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#ip route 192.168.5.0 255.255.255.128 192.168.5.225
Router(config)#ip route 192.168.5.128 255.255.255.192 192.168.5.225
Router(config)#do wr
Building configuration...
[OK]
Router(config)#do show ip route
Codes: L - local, C - connected, S - static, R - RIP, M - mobile, B - BGP
       D - EIGRP, EX - EIGRP external, O - OSPF, IA - OSPF inter area
       N1 - OSPF NSSA external type 1, N2 - OSPF NSSA external type 2
       E1 - OSPF external type 1, E2 - OSPF external type 2, E - EGP
       i - IS-IS, L1 - IS-IS level-1, L2 - IS-IS level-2, ia - IS-IS inter area
       * - candidate default, U - per-user static route, o - ODR
       P - periodic downloaded static route

Gateway of last resort is not set

     192.168.5.0/24 is variably subnetted, 8 subnets, 5 masks
S       192.168.5.0/25 [1/0] via 192.168.5.225
S       192.168.5.128/26 [1/0] via 192.168.5.225
C       192.168.5.192/28 is directly connected, GigabitEthernet0/0
L       192.168.5.206/32 is directly connected, GigabitEthernet0/0
C       192.168.5.208/28 is directly connected, GigabitEthernet0/1
L       192.168.5.222/32 is directly connected, GigabitEthernet0/1
C       192.168.5.224/30 is directly connected, Serial0/3/0
L       192.168.5.226/32 is directly connected, Serial0/3/0
