# Pihole
Implementing own DNS server with ad blocking 


For this project I am using Orange pi lite 2. Preferably we should use any board with similar specifications and that has an ethernet port.
Lite 2 doesn't has an ethernet port but it does has wifi AC 5Ghz. Which works pretty well in our scenario. 

1. Connect to the pi with SSH or Serial port.
2. Set a static IP address. Its better to give a static IP in your router to get rid of IP clashes.
  type:  sudo nano /etc/network/interfaces
  replace ....
          auto wlan0                // check your interface first with ifconfig
          iface wlan0 inet dhcp
          ....
  With .....
       auto wlan0
       iface wlan0 inet static
       address 192.168.0.10
       netmask 255.255.255.0
       gateway 192.168.0.1               // check your gateway IP
       dns-nameservers 1.1.1.1 1.0.0.1
       .....
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
