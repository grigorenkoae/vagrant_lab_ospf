# OSPF lab using Arista vEOS

This Vagrantfile will spawn 2 instances of vEOS and 2 Ubuntu servers.
Both routers will be connected back to back with IP address and OSPF pre-configured on their interfaces.

## Requirements
### Resources
 - RAM : 5G
 - CPU : 1 Core (shared)

### Tools
 - Vagrant and Virtualbox
 - Ansible for provisioning (except for windows)

## Topology

    =============                      =============
    |           |   e1 OSPF area 0     |           |
    |   vEOS1   | -------------------- |   vEOS2   |
    |           | -------------------- |           |
    =============   e2 OSPF area 1     =============
        e3|                               e3|
    =============                      =============
    |    srv1   |                      |    srv2   |
    =============                      =============

## Provisioning / Configuration
Ansible is used to provision both routers with an IP address and OSPF configuration on their interfaces.
Both servers are preconfigured with an IP address and a route to their respective vEOS.
