## AireOS vs IOS-XE Controller Commands

---

<table><tbody><tr><td><strong>Configuration Goal</strong></td><td><strong>Slot &nbsp; &nbsp; &nbsp;&nbsp;</strong></td><td><strong>AP Model</strong></td><td><strong>AireOS Controller Commands</strong></td><td><strong>IOS-XE Controller Commands</strong></td></tr><tr><td>Change the AP Name</td><td>-</td><td>ALL</td><td><pre><code class="language-plaintext">config ap name $NEW_NAME $MAC_ADDRESS
config ap name $NEW_NAME $CURRENT_NAME
config ap name $NEW_NAME $SERIAL</code></pre></td><td><pre><code class="language-plaintext">ap name $CURRENT_NAME name $NEW_NAME</code></pre></td></tr><tr><td>Disable 2.4 radio</td><td>-</td><td>1815</td><td><pre><code class="language-plaintext">config 802.11b disable $AP_NAME</code></pre></td><td><pre><code class="language-plaintext">ap name $AP_NAME dot11 24ghz shutdown</code></pre></td></tr><tr><td>Set 2.4 radio power and channel</td><td>Slot 0</td><td>1815</td><td><pre><code class="language-plaintext">config 802.11b disable $AP_NAME
config 802.11b txpower ap $AP_NAME $TXLEVEL
config 802.11b channel ap $AP_NAME $CHANNEL
config 802.11b enable $AP_NAME                         </code></pre></td><td><pre><code class="language-plaintext">ap name $AP_NAME dot11 24ghz shutdown
ap name $AP_NAME dot11 24ghz txpower $TXLEVEL
ap name $AP_NAME dot11 24ghz channel $CHANNEL
ap name $AP_NAME no dot11 24ghz shutdown                  </code></pre></td></tr><tr><td>Set 5 radio power and channel</td><td>Slot 1</td><td>1815</td><td><pre><code class="language-plaintext">config 802.11a disable $AP_NAME
config 802.11a txpower ap $AP_NAME $TXLEVEL
config 802.11a channel ap $AP_NAME $CHANNEL
y
config 802.11a enable $AP_NAME</code></pre></td><td><pre><code class="language-plaintext">ap name $AP_NAME dot11 5ghz shutdown
ap name $AP_NAME dot11 5ghz txpower 1
ap name $AP_NAME dot11 5ghz channel 157
ap name $AP_NAME no dot11 5ghz shutdown</code></pre></td></tr><tr><td>Set flex radio to monitor mode</td><td>Slot 0</td><td>2800/3800</td><td><pre><code class="language-plaintext">config 802.11-abgn disable $AP_NAME
config 802.11-abgn role $AP_NAME manual monitor
config 802.11-abgn enable $AP_NAME</code></pre></td><td><pre><code class="language-plaintext">ap name $AP_NAME dot11 dual-band shutdown
ap name $AP_NAME dot11 dual-band role manual monitor
ap name $AP_NAME no dot11 dual-band shutdown</code></pre></td></tr><tr><td>Set flex radio power and channel</td><td>Slot 0</td><td>2800/3800</td><td><pre><code class="language-plaintext">config 802.11-abgn disable $AP_NAME
config 802.11-abgn role $AP_NAME manual client-serving
config 802.11-abgn channel ap $AP_NAME $CHANNEL
config 802.11-abgn txpower ap $AP_NAME $TXLEVEL
y
config 802.11-abgn enable $AP_NAME</code></pre></td><td><pre><code class="language-plaintext">ap name $AP_NAME dot11 dual-band shutdown
ap name $AP_NAME dot11 dual-band role manual client-serving 
ap name $AP_NAME dot11 dual-band txpower $TXLEVEL
ap name $AP_NAME dot11 dual-band channel $CHANNEL
ap name $AP_NAME no dot11 dual-band shutdown
</code></pre></td></tr><tr><td>Set 5 radio power and channel</td><td>Slot 1</td><td>2800/3800</td><td><pre><code class="language-plaintext">config 802.11a disable $AP_NAME
config 802.11a role $AP_NAME manual client-serving
config 802.11a txpower ap $AP_NAME $TXLEVEL
config 802.11a channel ap $AP_NAME $CHANNEL
y
config 802.11a enable $AP_NAME</code></pre></td><td><pre><code class="language-plaintext">ap name $AP_NAME dot11 5ghz shutdown
ap name $AP_NAME dot11 5ghz txpower $TXLEVLE
ap name $AP_NAME dot11 5ghz channel $CHANNEL
ap name $AP_NAME no dot11 5ghz shutdown</code></pre></td></tr><tr><td>Set flex radio to monitor mode</td><td>Slot 0</td><td>9120</td><td><pre><code class="language-plaintext">config 802.11-abgn disable $AP_NAME
config 802.11-abgn role $AP_NAME manual monitor
config 802.11-abgn enable $AP_NAME
</code></pre></td><td><pre><code class="language-plaintext">ap name $AP_NAME dot11 dual-band shutdown
ap name $AP_NAME dot11 dual-band role manual monitor
ap name $AP_NAME no dot11 dual-band shutdown</code></pre></td></tr><tr><td>Set flex radio power and channel</td><td>Slot 0</td><td>9120</td><td><pre><code class="language-plaintext">config 802.11-abgn disable $AP_NAME
config 802.11-abgn role $AP_NAME manual client-serving
config 802.11-abgn txpower $AP_NAME $TXLEVEL
config 802.11-abgn channel ap $AP_NAME $CHANNEL
config 802.11-abgn enable $AP_NAME</code></pre></td><td><pre><code class="language-plaintext">ap name $AP_NAME dot11 dual-band shutdown
ap name $AP_NAME dot11 dual-band role manual client-serving
ap name $AP_NAME dot11 dual-band txpower $TXLEVEL
ap name $AP_NAME dot11 dual-band channel $CHANNEL
ap name $AP_NAME no dot11 dual-band shutdown</code></pre></td></tr><tr><td>Set 5 radio power and channel</td><td>Slot 1</td><td>9120</td><td><pre><code class="language-plaintext">config 802.11a disable $AP_NAME
config 802.11a txpower ap $AP_NAME 3
config 802.11a channel ap $AP_NAME 48
config 802.11a enable $AP_NAME</code></pre></td><td><pre><code class="language-plaintext">ap name $AP_NAME dot11 5ghz shutdown
ap name $AP_NAME dot11 5ghz txpower $TXLEVEL
ap name $AP_NAME dot11 5ghz channel $CHANNEL
ap name $AP_NAME no dot11 5ghz shutdown</code></pre></td></tr><tr><td>Set 2.4 radio to monitor mode</td><td>Slot 0</td><td>9130</td><td><pre><code class="language-plaintext">config 802.11b disable $AP_NAME
config 802.11b role $AP_NAME manual monitor
config 802.11b enable $AP_NAME</code></pre></td><td><pre><code class="language-plaintext">ap name $AP_NAME dot11 24ghz shutdown
ap name $AP_NAME dot11 24ghz role manual monitor
ap name $AP_NAME no dot11 24ghz shutdown</code></pre></td></tr><tr><td>Set 2.4 radio power and channel</td><td>Slot 0</td><td>9130</td><td><pre><code class="language-plaintext">config 802.11b disable $AP_NAME
config 802.11b txpower ap $AP_NAME $TXLEVEL
config 802.11b channel ap $AP_NAME $CHANNEL
config 802.11b enable $AP_NAME</code></pre></td><td><pre><code class="language-plaintext">ap name $AP_NAME dot11 24ghz shutdown
ap name $AP_NAME dot11 24ghz txpower $TXLEVEL
ap name $AP_NAME dot11 24ghz channel $CHANNEL
ap name $AP_NAME no dot11 24ghz shutdown  </code></pre></td></tr><tr><td>Set 5 macro radio power and channel</td><td>Slot 1</td><td>9130</td><td><pre><code class="language-plaintext">config slot 1 disable $AP_NAME
config slot 1 role $AP_NAME manual client-serving
config slot 1 txpower ap $AP_NAME $TXLEVEL
config slot 1 channel ap $AP_NAME $CHANNEL
config slot 1 enable $AP_NAME</code></pre></td><td><pre><code class="language-plaintext">ap name $AP_NAME dot11 5ghz shutdown
ap name $AP_NAME dot11 5ghz role manual client-serving
ap name $AP_NAME dot11 5ghz txpower $TXLEVEL
ap name $AP_NAME dot11 5ghz channel $CHANNEL
ap name $AP_NAME no dot11 5ghz shutdown</code></pre></td></tr><tr><td>Set 5 micro radio to monitor mode</td><td>Slot 2</td><td>9130</td><td><pre><code class="language-plaintext">config slot 2 role $AP_NAME manual monitor</code></pre></td><td><pre><code class="language-plaintext">ap name $AP_NAME dot 11 5ghz slot 2 shutdown
ap name $AP_NAME dot11 5ghz slot 2 radio role manual monitor
</code></pre></td></tr><tr><td>Disable 2.4 radio</td><td>Slot 0</td><td>9105</td><td><pre><code class="language-plaintext">config 802.11b disable $AP_NAME</code></pre></td><td><pre><code class="language-plaintext">ap name $AP_NAME dot11 24ghz shutdown</code></pre></td></tr><tr><td>Set 2.4 radio power and channel</td><td>slot 0</td><td>9105</td><td><pre><code class="language-plaintext">config 802.11b disable $AP_NAME
config 802.11b txpower ap $AP_NAME $TXLEVEL
config 802.11b channel ap $AP_NAME $CHANNEL
y
config 802.11b enable $AP_NAME</code></pre></td><td><pre><code class="language-plaintext">ap name $AP_NAME dot11 24ghz txpower $TXLEVEL
ap name $AP_NAME dot11 24ghz channel $CHANNEL
ap name $AP_NAME no dot11 24ghz shutdown</code></pre></td></tr><tr><td>Set 5 radio power and channel</td><td>Slot 1</td><td>9105</td><td><pre><code class="language-plaintext">config 802.11a disable $AP_NAME
config 802.11a txpower ap $AP_NAME $TXLEVEL
config 802.11a channel ap $AP_NAME $CHANNEL
y
config 802.11a enable $AP_NAME</code></pre></td><td><pre><code class="language-plaintext">ap name $AP_NAME dot11 5ghz txpower $TXLEVEL
ap name $AP_NAME dot11 5ghz channel $CHANNEL
ap name $AP_NAME no dot11 5ghz shutdown</code></pre></td></tr><tr><td>Configure primary and secondary WLC</td><td>-</td><td>ALL</td><td><pre><code class="language-plaintext">config ap primary-base $WLC_NAME $AP_NAME $WLC_IP
config ap secondary-base $WLC_NAME $AP_NAME $WLC_IP</code></pre></td><td><pre><code class="language-plaintext">ap name $AP_NAME controller primary $WLC_NAME $WLC_IP
ap name $AP_NAME controller secondary $WLC_NAME $WLC_IP</code></pre></td></tr><tr><td>Set static IP for AP</td><td>-</td><td>ALL</td><td><pre><code class="language-plaintext">config ap static-IP enable $AP_NAME $IP $NM #GW</code></pre></td><td><pre><code class="language-plaintext">ap name $AP_NAME static-ip ip-address $IP netmask $NM gateway $GW</code></pre></td></tr><tr><td>Set static domain</td><td>-</td><td>ALL</td><td><pre><code class="language-plaintext">config ap static-IP add domain $AP-NAME net.utah.edu</code></pre></td><td><pre><code class="language-plaintext">ap name $AP_NAME static-ip domain net.utah.edu</code></pre></td></tr><tr><td>Set static name server</td><td>-</td><td>ALL</td><td><pre><code class="language-plaintext">config ap static-IP add nameserver $AP_NAME 172.20.120.20</code></pre></td><td><pre><code class="language-plaintext">ap name $AP_NAME static-ip nameserver 172.20.120.20</code></pre></td></tr></tbody></table>