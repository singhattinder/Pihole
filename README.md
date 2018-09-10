# Pi-hole
## Implementing own DNS Relay with ad blocking 


For this project I am using Orange pi lite 2. Preferably we should use any board with similar specifications and that has an ethernet port.
Lite 2 doesn't have an ethernet port but it does has wifi AC 5Ghz. Which works pretty well in our use case. I have ubuntu 16.04.5 LTS installed on this board.

<a href="https://imgbb.com/"><img src="https://image.ibb.co/mo6WN9/Screen_Shot_2018_09_10_at_4_28_50_PM.png" alt="Screen_Shot_2018_09_10_at_4_28_50_PM" border="0"></a>

<p>1. Connect to the pi with SSH or Serial port.</p>
<p><br />2. Set a static IP address. Its better to give a static IP in your router to get rid of IP clashes.</p>
  
 <div>&nbsp; &nbsp; type: &nbsp;sudo nano /etc/network/interfaces</div>
<div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;replace ....</div>
<div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; auto wlan0 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;// <span style="color: #99ccff;">check your interface first with </span>ifconfig</div>
<div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp;iface wlan0 inet dhcp</div>
<div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; .....</div>
<div>&nbsp;</div>
<div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;With .....</div>
<div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; auto wlan0</div>
<div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; iface wlan0 inet static</div>
<div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; address 192.168.0.193</div>
<div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; netmask 255.255.255.0</div>
<div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; gateway 192.168.0.1 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; <span style="color: #99ccff;">// check your gateway IP</span></div>
<div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; dns-nameservers 1.1.1.1 1.0.0.1</div>
<div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; .....</div>
       
<p>5. Now follow the on screen instructions.</p>
<p><br />6. Select ClouldFlare DNS because its faster than the Google DNS(right now).</p>
<p><br />7. Select Protocols (IPv4 and IPv6).</p>
<p><br />8. It will again ask for network settings. Make sure your gateway and IP are entered correctly.</p>
<p><br />9. Follow along with default settings.</p>
<p><br />10. In the final step write down the web password for web access.</p>

### Your web access page should look like this.



<a href="https://ibb.co/jj8xUp"><img src="https://preview.ibb.co/iagHUp/Screen_Shot_2018_09_10_at_3_55_32_PM.png" alt="Screen_Shot_2018_09_10_at_3_55_32_PM" border="0"></a>





Some other Gravity lists for more blocking 

	https://raw.githubusercontent.com/anudeepND/youtubeadsblacklist/master/hosts.txt	
	https://raw.githubusercontent.com/HenningVanRaumle/pihole-ytadblock/master/ytadblock.txt	
	https://tspprs.com/dl/ads	
	https://raw.githubusercontent.com/CHEF-KOCH/CKs-FilterList/master/HOSTS/CK's-Spotify-HOSTS-FilterList.txt	
	https://raw.githubusercontent.com/anudeepND/blacklist/master/adservers.txt	
	https://v.firebog.net/hosts/Easylist.txt	
	https://pgl.yoyo.org/adservers/serverlist.php?hostformat=hosts;showintro=0	
	https://v.firebog.net/hosts/AdguardDNS.txt
  
  
  
I did however used https://smokingwheels.github.io/Pi-hole/allhosts. It contains over 1.2 Million domains but don't use this because it blocks many CDNs and other important domains. Important point to be noted here you cannot block youtube ads because these are coming from same domains as the content.

### Now just point your device to this DNS server.





### you can see ads are being blocked in < 1ms.

<a href="https://ibb.co/n4suaU"><img src="https://preview.ibb.co/cHShUp/Screen_Shot_2018_09_10_at_4_24_30_PM.png" alt="Screen_Shot_2018_09_10_at_4_24_30_PM" border="0"></a>
  

