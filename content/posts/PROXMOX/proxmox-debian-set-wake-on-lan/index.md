---
title: "Proxmox - Set wake on lan"
#summary: "How to setup OpenMediaVault as a backup server"
categories: ["Proxmox","Wake on Lan", "Debian", "Linux"]
tags: ["Proxmox","Debian"]
date: 2021-12-23
weight: 2
author: "Sabbadin Stefy"
---

Set your proxmox node to respond at wake-on-lan messages


# Install ethtool

Install ethtool
go to your node shell

    apt install ethtool

# Get your interface name

    ip addr

# Check if wake-on-lan is already activ

You need to find how your interface is named. You cal look for it under System > Network
In our case our interface is named *enp6s0*
Look at the current configuration:

    ethtool enp6s0

If you find this row:

    wake on: d

that mean it's disabled

# Enable wake-on-lan

    ethtool -s enp6s0 wol g

# Set option in the interfaces configuration file

    nano /etc/network/interface

add the following line to the configuration file

    post-up /usr/sbin/ethtool -s enp6s0 wol g

under the iface line of your interface.
The final result should look like this:

    auto enp6s0
        iface enp6s0 inet manual
        post-up /usr/sbin/ethtool -s enp6s0 wol g

save and exit

# Let Proxmox keep the configuration

To keep the configuration we need to reload the proxmox settings inthe gui.
To do this go to your node > System > Network select your WoL interface and click "Edit".
Add the Autostart flag and save.

# Testing time

Now turn off your proxmox node, the from your favorite WoL sender send the magic package to your node. If the node start-up your configuration is set.
