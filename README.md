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
