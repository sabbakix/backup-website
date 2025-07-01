---
title: "Proxmox - remove and rejoint node"
#summary: "How to setup OpenMediaVault as a backup server"
categories: ["Proxmox"]
tags: ["Proxmox"]
date: 2022-01-22
weight: 2
author: "Sabbadin Stefy"
---

Remove a node from the proxmox cluster and then rejoint with same name
Let's say that for this example, our node name pve03.



- Shut down node.

- Remove node

    Enter the shell of another node in the cluster

        pvecm delnode pve03


- Remove node

    Again from other node: 

        rm -r /etc/pve/nodes/pve03

- Remove node entry(ies) from authorized keys file

        nano /etc/pve/priv/authorized_keys

    remove the line associated with our node, ending with pve03

- Reboot all nodes

- Install node and rejoin to cluster

