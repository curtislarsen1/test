## **Using the “radius.State” Wireshark Filter to Match Wired RADIUS Packets with Over The Air EAP Frames** 

#### **By** **Curtis Larsen 11/8/23**

Below is a sample Over The Air (OTA) packet capture for a typical EAP-TLS session with a simple filter:

```plaintext
wlan.addr == dc:e5:5b:36:e2:8e && eap
```

![](https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/9b1bb91334f7ca8e9ea2690c8d37d7f4e293e397b49966da.png)

Adding a column for the EAP-TLS Start frame helps match up the OTA and wired RADIUS capture later on.  To do this, select one of the Request packets and right click on the **“Start :  True”** value, then select **“Apply as column”** as shown below.

![](https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/4f84778eeb6035b0de1c785ccc4a70b874a32c4c3aa4a968.png)

Now the “True” value is shown in the Request frame of the newly added “Start” column.

![](https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/53709002733c5f75451f6d16a65cce7132f6973242c6ad85.png)

Moving from the OTA pcap to the wired RADIUS pcap, the **“radius.Calling\_Station\_Id”** filter is used:

```plaintext
radius.Calling_Station_Id == "dc:e5:5b:36:e2:8e"
```

After applying this filter, about half of the conversation is visible (All of the “Access-Requests”):

![](https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/ff7708c8ee800f28d3bff94e15107e32ee2ae4c88e8dd776.png)

To see the other half of the conversation (Access-Challenges) the **“radius.State”** filter must be added:

```plaintext
(radius.Calling_Station_Id == "dc:e5:5b:36:e2:8e") || (radius.State == 33:37:43:50:4d:53:65:73:73:69:6f:6e:49:44:3d:33:38:30:33:31:43:41:43:30:30:30:30:32:32:36:39:31:42:37:30:42:37:43:44:3b:33:39:53:65:73:73:69:6f:6e:49:44:3d:74:65:64:63:2d:69:73:65:31:2f:34:37:36:36:39:35:35:37:34:2f:31:36:32:31:32:37:39:33:32:3b)
```

This is done by right clicking on the **“State”** value of the **“State”** AVP in the second Access-Request packet as shown below and clicking **“Apply as Filter …or Selected”**

![](https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/383ecd50ea34acb8532b12b4c76dfcf8c2fba10097d560cb.png)

The other half of the conversation is now shown, along with the matching EAP Start frame **(marked True)**, just like in the previous OTA pcap:

![](https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/2cc2da96373bf9fb6ac5ab768cdedf90947255974842f355.png)

When comparing the OTA pcap (left) to the RADIUS pcap (right), there is only one packet missing from the RADIUS pcap - the EAP **“Success” or “Access-Accept”** packet should be the last one in the conversation.

<table><tbody><tr><td><figure class="image"><img src="https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/93fdf26c592546bdb0bd6b1781673f43d047730aeedf2a1d.png" srcset="https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/93fdf26c592546bdb0bd6b1781673f43d047730aeedf2a1d.png/w_200 200w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/93fdf26c592546bdb0bd6b1781673f43d047730aeedf2a1d.png/w_400 400w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/93fdf26c592546bdb0bd6b1781673f43d047730aeedf2a1d.png/w_600 600w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/93fdf26c592546bdb0bd6b1781673f43d047730aeedf2a1d.png/w_800 800w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/93fdf26c592546bdb0bd6b1781673f43d047730aeedf2a1d.png/w_1000 1000w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/93fdf26c592546bdb0bd6b1781673f43d047730aeedf2a1d.png/w_1200 1200w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/93fdf26c592546bdb0bd6b1781673f43d047730aeedf2a1d.png/w_1400 1400w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/93fdf26c592546bdb0bd6b1781673f43d047730aeedf2a1d.png/w_1600 1600w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/93fdf26c592546bdb0bd6b1781673f43d047730aeedf2a1d.png/w_1800 1800w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/93fdf26c592546bdb0bd6b1781673f43d047730aeedf2a1d.png/w_1915 1915w" sizes="100vw" width="1915"></figure></td><td><figure class="image"><img src="https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/67d4d71fefa9fe3098631e83c14e2229ff83224dbac46db9.png" srcset="https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/67d4d71fefa9fe3098631e83c14e2229ff83224dbac46db9.png/w_200 200w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/67d4d71fefa9fe3098631e83c14e2229ff83224dbac46db9.png/w_400 400w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/67d4d71fefa9fe3098631e83c14e2229ff83224dbac46db9.png/w_600 600w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/67d4d71fefa9fe3098631e83c14e2229ff83224dbac46db9.png/w_800 800w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/67d4d71fefa9fe3098631e83c14e2229ff83224dbac46db9.png/w_1000 1000w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/67d4d71fefa9fe3098631e83c14e2229ff83224dbac46db9.png/w_1200 1200w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/67d4d71fefa9fe3098631e83c14e2229ff83224dbac46db9.png/w_1400 1400w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/67d4d71fefa9fe3098631e83c14e2229ff83224dbac46db9.png/w_1600 1600w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/67d4d71fefa9fe3098631e83c14e2229ff83224dbac46db9.png/w_1800 1800w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/67d4d71fefa9fe3098631e83c14e2229ff83224dbac46db9.png/w_1915 1915w" sizes="100vw" width="1915"></figure></td></tr></tbody></table>

The corresponding Access-Accept packet is found by adding the **“Packet Identifier”** field from the last shown “Access-Request” packet to the filter.  In this case, the Packet Identifier was “21” as shown below.    
  
**NOTE:**  If you are capturing high volumes of RADIUS transactions, you will likely find duplicate Packet Identifiers (radius-id's) for other clients, so be sure to verify that the packet was indeed the correct response to the last Access-Request by checking three lines below for the blue underlined note that indicates…

 “The response to this request is in frame XXX", as shown below:

```plaintext
((radius.Calling_Station_Id == "dc:e5:5b:36:e2:8e") || (radius.State == 33:37:43:50:4d:53:65:73:73:69:6f:6e:49:44:3d:33:38:30:33:31:43:41:43:30:30:30:30:32:32:36:39:31:42:37:30:42:37:43:44:3b:33:39:53:65:73:73:69:6f:6e:49:44:3d:74:65:64:63:2d:69:73:65:31:2f:34:37:36:36:39:35:35:37:34:2f:31:36:32:31:32:37:39:33:32:3b)) || (radius.id == 21)
```

![](https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/90bd9f17bbe51299cca16bd937840bbc4df7725ebf4a0295.png)

Now, all of the matching packets from the wired RADIUS pcap are displayed and correspond directly to frames in the OTA pcap:

![](https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/0615228eea7109e349c01cc74a3a2659097da9e634c29407.png)

Finally, one more column is added to make the wired and wireless pcaps even easier to match - the “Code” value in the EAP message can be "Applied as a column".

![](https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/76603a0514f8b16c456f0c361049418cd211f4d6c5a5fb0d.png)

The result is that the two pcaps are easy to compare side by side, lining up the EAP-TLS Start packet, the final Success message and each Request and Response in between.

<table><tbody><tr><td><figure class="image"><img src="https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/99786f44552a2deff219d413dbb86b74b80889e86c9152c7.png" srcset="https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/99786f44552a2deff219d413dbb86b74b80889e86c9152c7.png/w_200 200w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/99786f44552a2deff219d413dbb86b74b80889e86c9152c7.png/w_400 400w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/99786f44552a2deff219d413dbb86b74b80889e86c9152c7.png/w_600 600w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/99786f44552a2deff219d413dbb86b74b80889e86c9152c7.png/w_800 800w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/99786f44552a2deff219d413dbb86b74b80889e86c9152c7.png/w_1000 1000w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/99786f44552a2deff219d413dbb86b74b80889e86c9152c7.png/w_1200 1200w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/99786f44552a2deff219d413dbb86b74b80889e86c9152c7.png/w_1400 1400w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/99786f44552a2deff219d413dbb86b74b80889e86c9152c7.png/w_1600 1600w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/99786f44552a2deff219d413dbb86b74b80889e86c9152c7.png/w_1800 1800w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/99786f44552a2deff219d413dbb86b74b80889e86c9152c7.png/w_1914 1914w" sizes="100vw" width="1914"></figure></td><td><figure class="image"><img src="https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/54a0fe435449f58ec7d3721507e91ce5efbfefe8c2c16bbe.png" srcset="https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/54a0fe435449f58ec7d3721507e91ce5efbfefe8c2c16bbe.png/w_200 200w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/54a0fe435449f58ec7d3721507e91ce5efbfefe8c2c16bbe.png/w_400 400w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/54a0fe435449f58ec7d3721507e91ce5efbfefe8c2c16bbe.png/w_600 600w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/54a0fe435449f58ec7d3721507e91ce5efbfefe8c2c16bbe.png/w_800 800w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/54a0fe435449f58ec7d3721507e91ce5efbfefe8c2c16bbe.png/w_1000 1000w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/54a0fe435449f58ec7d3721507e91ce5efbfefe8c2c16bbe.png/w_1200 1200w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/54a0fe435449f58ec7d3721507e91ce5efbfefe8c2c16bbe.png/w_1400 1400w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/54a0fe435449f58ec7d3721507e91ce5efbfefe8c2c16bbe.png/w_1600 1600w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/54a0fe435449f58ec7d3721507e91ce5efbfefe8c2c16bbe.png/w_1800 1800w, https://33333.cdn.cke-cs.com/kSW7V9NHUXugvhoQeFaf/images/54a0fe435449f58ec7d3721507e91ce5efbfefe8c2c16bbe.png/w_1917 1917w" sizes="100vw" width="1917"></figure></td></tr></tbody></table>

This filtering process helps speed up the 802.1X enterprise Wi-Fi authentication troubleshooting process for services like eduroam.  Matching up the OTA and RADIUS pcaps helps identify where packets might be lost or delayed.  
  
It took me a while to find the “radius.State” filter, so I thought I'd share this information in case it helps someone else in the future.  Let me know if you find it helpful too.  
  
[linkedin.com/in/curtis-k-larsen](https://www.linkedin.com/in/curtis-k-larsen)