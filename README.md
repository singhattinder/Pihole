# Pihole
Implementing own DNS server with ad blocking 


For this project I am using Orange pi lite 2. Preferably we should use any board with similar specifications and that has an ethernet port.
Lite 2 doesn't has an ethernet port but it does has wifi AC 5Ghz. Which works pretty well in our scenario. 

1. Connect to the pi with SSH or Serial port.
2. Set a static IP address.
Its better to give a static IP in your router to get rid of IP clashes.
  
  <div>type: &nbsp;sudo nano /etc/network/interfaces</div>
<div>&nbsp; replace ....</div>
<div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; auto wlan0 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;// <span style="color: #99ccff;">check your interface first with </span>ifconfig</div>
<div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; iface wlan0 inet dhcp</div>
<div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; .....</div>
<div>&nbsp;</div>
<div>&nbsp; With .....</div>
<div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;auto wlan0</div>
<div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;iface wlan0 inet static</div>
<div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;address 192.168.0.10</div>
<div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;netmask 255.255.255.0</div>
<div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;gateway 192.168.0.1 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; <span style="color: #99ccff;">// check your gateway IP</span></div>
<div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;dns-nameservers 1.1.1.1 1.0.0.1</div>
<div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;.....</div>
       
3. Reboot with sudo shutdown -r now
4. Now install Pi-hole with 
      git clone --depth 1 https://github.com/pi-hole/pi-hole.git Pi-hole
      cd Pi-hole/automated\ install/
      bash basic-install.sh
5. Now follow the instructions.
6. Select ClouldFlare DNS because its faster than the Google DNS(right now).
7. Select Protocols (IPv4 and IPv6).
8. It will again ask for network settings. Make sure your gateway and IP are entered correctly.
9. Follow along with default settings. 
10. In the final step write down the web password for web access.

Your web access page should look like this.

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
  

