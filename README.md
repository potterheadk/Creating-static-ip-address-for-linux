# Configuring a Static IP Address on Linux

This guide will help you configure a static IP address on your Linux machine using Netplan.

## Steps

### 1. Create a Backup of the Existing Configuration File
First, back up your current Netplan configuration file:

```bash
sudo cp /etc/netplan/00-installer-config.yaml /etc/netplan/00-installer-config.yaml.bck
```

### 1. Create a New Configuration File

 Create a new file named static.yaml:


```bash
sudo touch /etc/netplan/static.yaml
```

### 3. Edit the New Configuration File

Open the static.yaml file in a text editor:

```bash
sudo nano /etc/netplan/static.yaml
```
Paste the following configuration into the file or clone from static.yaml:
```bash
yaml

network:
  version: 2
  renderer: NetworkManager
  ethernets:
    <your-interface-name>:
      addresses:
        - 192.168.1.100/24
      routes:
        - to: 0.0.0.0/0
          via: 192.168.1.1
      nameservers:
        search: [mydomain, otherdomain]
        addresses: [1.1.1.1, 1.0.0.1]
```
    IP Address: Change 192.168.1.100/24 to the desired static IP address.
    Gateway: Replace 192.168.1.1 with your router's gateway address (check on Windows with ipconfig /all and find the Default Gateway).
    Interface Name: Replace <your-interface-name> with your actual network interface name (e.g., enp0s10).

### 4. Apply the Configuration

Save the file and exit the editor. Then apply the new Netplan configuration:

```bash
sudo netplan apply
```
###5. Ignore Warnings (Optional)

You might see warnings about file permissions. You can ignore them, but for better security, set the correct permissions:

```bash
sudo chmod 600 /etc/netplan/static.yaml
```
### 6. Reboot the System

Reboot your system to ensure the changes take effect:

```bash
sudo reboot
```
### 7. Verify the Configuration

After rebooting, check your network configuration to verify that the static IP address is set:

```bash
ifconfig
```
# or
```bash
ip a
```

## You should see your new static IP address configured for your network interface.
## Enjoy!

# Your static IP address is now set up and ready to use.
