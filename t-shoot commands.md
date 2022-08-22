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
 

test
