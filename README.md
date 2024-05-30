# Configuring a Static IP Address on Linux

This guide will help you configure a static IP address on your Linux machine using Netplan.

## Steps

### 1. Create a Backup of the Existing Configuration File
First, back up your current Netplan configuration file:

```bash
sudo cp /etc/netplan/00-installer-config.yaml /etc/netplan/00-installer-config.yaml.bck
