# Creating-static-ip-address-for-linux

1)Create backup file of following file in the same directory like follow
cd /etc/netplan/00-installer-config.yaml 
as
mv /etc/netplan/00-installer-config.yaml  /etc/netplan/00-installer-config.yaml.bck

2)so now create file name static.yaml
touch static.yaml

3)open file in editor 
sudo nano static.yaml 
and paste the text present in attach file

4)change the address to 192.168.1.1 (you can put whatever you want.)
in gatway section put your router gateway check in your pc in windows (type : ipconfig /all and in default gateway paste that ip here)

5)below ethernet put your ethernet interface in my case its enp0s10 put yours there.

6) save it .

7) and type sudo netplan apply.

8) dont worry about warnings.

9) sudo reboot now .

10) after rebooting put ifconfig or ip a you will find your static ip address 

enjoy :) 
