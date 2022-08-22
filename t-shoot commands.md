**Tshoot Commands - IOS-XE**

---

```plaintext
show ap summary
```

AP Name                            Slots    AP Model              Ethernet MAC    Radio MAC       Location                          Country     IP Address                                 State           
\-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------   
ap-0482-3-3315                       2      AIR-AP3802I-B-K9      002a.1034.73cc  00a2.ee17.3d00  default location                  US          172.31.16.115                              Registered      
ap-0482-3-3417                       2      AIR-AP3802I-B-K9      002a.1034.73da  00a2.ee17.3de0  default location                  US          172.31.16.163                              Registered      
ap-0482-2-2217                       2      AIR-AP3802I-B-K9      002a.1034.7916  00a2.ee17.91c0  default location                  US          172.31.16.226                              Registered      

```plaintext
show wireless client summary
```

Number of Clients: 6295

MAC Address    AP Name                                        Type ID   State             Protocol Method     Role  
\-------------------------------------------------------------------------------------------------------------------------  
0000.c00c.89fb ap-0046-3-3004                                 WLAN 4    Run               11n(2.4) MAB        Local               
000a.f594.5d95 ap-0811-4-409r                                 WLAN 1    Run               11ac     Dot1x      Local               
006b.9eed.750c ap-0821-3-308r                                 WLAN 4    Run               11n(2.4) MAB        Local       

```plaintext
show ap uptime
```

Number of APs: 2412

AP Name                          Ethernet MAC    Radio MAC       AP Up Time                                          Association Up Time  
\---------------------------------------------------------------------------------------------------------------------------------------------------  
ap-0608-1-102                    3c51.0e3d.f474  a0b4.39c9.3dc0  82 days 2 hours 38 minutes 5 seconds                82 days 2 hours 35 minutes 1 second            
ap-0608-1-153f                   3c51.0e3d.f3f2  a0b4.39c9.35a0  82 days 2 hours 36 minutes 35 seconds               82 days 2 hours 33 minutes 34 seconds          
ap-0607-0-1                      a0b4.3978.d648  c4b2.3937.8480  82 days 2 hours 35 minutes 55 seconds               82 days 2 hours 32 minutes 46 seconds   

```plaintext
show ap dot11 dual-band summary
```

```plaintext
show ap dot11 24ghz summary
```

```plaintext
show ap dot11 5ghz summary
```

AP Name                           Mac Address     Slot    Admin State    Oper State    Width    Txpwr           Channel                             Mode  
\---------------------------------------------------------------------------------------------------------------------------------------------------------  
ap-0046-5-5005                    0062.ecaa.da90  1       Enabled        Up            20       2/8 (20 dBm)    (149)                               Local        
ap-0046-3-3002                    0062.ecfe.26e0  1       Enabled        Up            20       2/8 (19 dBm)    (36)                                Local        
ap-0046-3-3003                    0062.ecfe.27f0  1       Enabled        Up            20       4/8 (13 dBm)    (40)                                Local        

```plaintext
show ap dot11 24ghz cleanair air-quality summary
```

```plaintext
show ap dot11 5ghz cleanair air-quality summary
```

AP Name               Channel    Avg AQ  Min AQ  Interferers  Spectrum AP Type  
\------------------------------------------------------------------------------  
ap-0086-5-5150        165        100     100     0            CA   
ap-0086-1-1000        161        97      96      0            CA   
ap-0086-1-1000        165        99      99      0            CA   

```plaintext
show ap dot11 24ghz cleanair device type all
```

```plaintext
show ap dot11 5ghz cleanair device type all
```

ClusterID          Mac Address        DevID  Type          AP Name                          ISI  RSSI  DC   Channel  
\-------------------------------------------------------------------------------------------------------------------  
5700.000a.7923     17e5.e4c1.0d50     0x0d50 WiMax Fixed   ap-0086-2-2400-2                 --   -74   0    44,48                 
5700.001a.3a4f     17e5.e4c1.1664     0x1664 WiFi Inv. Ch  ap-0086-2-2400-2                 2    -64   1    144,149               
5700.001a.3b73     17e5.e4c1.1665     0x1665 Continuous TX ap-0086-2-2400-2                 --   -100  100  116         

```plaintext
show ap dot11 24ghz load-info
```

```plaintext
show ap dot11 5ghz load-info
```

AP Name                           Radio MAC       Slot  Channel Utilization (%)  Clients    
\----------------------------------------------------------------------------------------  
ap-0482-2-2238                    00a2.ee15.7ee0     1                        2        0    
ap-0482-2-2141                    00a2.ee15.7fc0     1                        1        0    
ap-0482-3-3315                    00a2.ee17.3d00     1                        2        0    

```plaintext
show ap cdp neighbors
```

AP Name                          AP IP                                     Neighbor Name                              Neighbor Port  
\------------------------------------------------------------------------------------------------------------------------------------------  
ap-0151-4-4800j                  172.31.35.219                             sx1-151ustar-4800b-ebc.net.utah.edu        GigabitEthernet9/29      

Neighbor IP Count: 1  
172.31.2.139                    

ap-0038-1-167                    172.30.17.230                             sx1-038art-138t-lib.net.utah.edu           GigabitEthernet1/0/24    

Neighbor IP Count: 1  
172.30.17.6                    

ap-0008-3-380                    172.30.0.113                              dx1-008aeb-210-lib.net.utah.edu            GigabitEthernet1/0/6      

Neighbor IP Count: 1  
172.30.0.68                       

```plaintext
show ap auto-rf dot11 dual-band
```

```plaintext
show ap auto-rf dot11 24ghz
```

```plaintext
show ap auto-rf dot11 5ghz
```

Nearby APs  
   AP 286f.7f17.b92f slot 1                    :  -82 dBm on (100, 20 MHz) (172.28.3.40)  
   AP 286f.7f18.822f slot 1                    :  -83 dBm on ( 36, 20 MHz) (172.28.3.40)  
   AP 70f0.968e.984f slot 1                    :  -86 dBm on ( 48, 20 MHz) (172.28.3.40)

```plaintext
sh ap auto-rf dot11 5ghz | i Channel changes due to radar|AP Name|Channel Change Count
```

AP Name                                           : ap-0037-2-232  
   Channel Change Count                          : 0  
AP Name                                           : ap-0037-2-232s  
   Channel Change Count                          : 0  
AP Name                                           : ap-0004-a-mech  
   Channel Change Count                          : 0  

```plaintext
show wireless stats ap history
```

AP Name                          Radio MAC       Event      Time               Recent Disconnect Time   Disconnect Reason          Disconnect Count  
\---------------------------------------------------------------------------------------------------------------------------------------------------  
ap-0151-4-4800j                  0027.9048.9540  Joined     06/28/22 22:07:50  NA                       NA                         NA  
ap-0151-4-4800j                  0027.9048.9540  Disjoined  06/28/22 22:07:19  NA                       DTLS close alert from peer 1   
ap-0151-4-4800j                  0027.9048.9540  Joined     06/28/22 21:53:20  NA                       NA                         NA  

```plaintext
show ap tag summary
```

AP Name                           AP Mac           Site Tag Name                     Policy Tag Name                   RF Tag Name                       Misconfigured    Tag Source      
\--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------      
ap-0482-2-2238                    002a.1060.3bfe   U\_0482\_AP                         Optimized                         Optimized\_RF                      No               Filter          
ap-0482-2-2141                    002a.1060.3c0c   U\_0482\_AP                         Optimized                         Optimized\_RF                      No               Filter          
ap-0482-3-3315                    002a.1034.73cc   U\_0482\_AP                         Optimized                         Optimized\_RF                      No               Filter          

```plaintext
show version | i uptime|Installation mode|Cisco IOS Software
```

Cisco IOS Software \[Bengaluru\], C9800 Software (C9800\_IOSXE-K9), Version 17.6.2, RELEASE SOFTWARE (fc7)  
wlc-ha-5 uptime is 24 weeks, 2 days, 13 hours, 13 minutes  
Installation mode is INSTALL  

```plaintext
show redundancy | i ptime|Location|Current Software state|Switchovers
```

 Available system uptime = 24 weeks, 2 days, 13 hours, 13 minutes  
Switchovers system experienced = 3  
              Active Location = slot 2  
       Current Software state = ACTIVE  
      Uptime in current state = 18 weeks, 3 days, 7 hours, 17 minutes  
             Standby Location = slot 1  
       Current Software state = STANDBY HOT   
      Uptime in current state = 18 weeks, 3 days, 7 hours, 4 minutes  

```plaintext
show wireless stats client detail
```

Total Number of Clients : 745

Protocol Statistics

\-----------------------------------------------------------------------------  
Protcol            Client Count  
802.11b              : 0  
802.11g              : 1  
802.11a              : 0  
802.11n-2.4GHz       : 38  
802.11n-5 GHz        : 85  
802.11ac             : 542  
802.11ax-5 GHz       : 81  
802.11ax-2.4 GHz     : 0  
 802.11ax-6 GHz      : 0

Current client state statistics:  
\-----------------------------------------------------------------------------  
 Authenticating         : 15  
 Mobility               : 0  
 IP Learn               : 8  
 Webauth Pending        : 40  
 Run                    : 684  
 Delete-in-Progress     : 0

Client Summary  
\-----------------------------  
Current Clients : 745  
Excluded Clients: 6  
Disabled Clients: 4  
Foreign Clients : 0  
Anchor Clients  : 0  
Local Clients   : 732  
Idle Clients    : 0  

```plaintext
show radius statistics
```

 Access Rejects           :      63739  
Access Accepts           :    3030216  
Average response delay(ms):          6         12          6

```plaintext
show wireless client mac-address 4407.0bc5.6f86 detail
```

Client MAC Address : 4407.0bc5.6f86  
Client MAC Type : Universally Administered Address  
Client DUID: NA  
Client IPv4 Address :   
Client Username : u1250539  
AP MAC Address : 1006.ed42.fb60  
AP Name: ap-0828-2-213b  
AP slot : 1  
Client State : Associated  
Policy Profile : PP-ULink  
Ipsk Tag : f45cb700a602d67e  
Flex Profile : N/A  
Wireless LAN Id: 4  
WLAN Profile Name: ULink  
 

```plaintext
show wireless client username u125053
```

MAC Address         AP Name                           Status             Type  ID             Auth  Protocol     
\-------------------------------------------------------------------------------------------------------------  
04d3.9506.f5ce      ap-0828-1-114r                    Run                WLAN  4              Yes   11n(5)       
4407.0bc5.6f86      ap-0828-3-314r                    Run                WLAN  4              Yes   11ac         
 

```plaintext
wireless client mac-address 4407.0bc5.6f86 deauthenticate
```

```plaintext
show ap name ap-0812-3-312r ethernet statistics
```

Interface Name      Status   Speed       Duplex  Rx Packets    Tx Packets    Discarded Packets       
\-------------------------------------------------------------------------------------------------  
GigabitEthernet0    UP       1000 Mbps   Full    130035569     114084757     0                       
LAN1                DOWN     Auto        Half    0             0             0                       
LAN2                DOWN     Auto        Half    0             0             0                       
LAN3                DOWN     Auto        Half    0             0             0                       
 

```plaintext
ap name ap-0812-3-312r lan port-id 1 enable
```
