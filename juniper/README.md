# OSPF lab using Juniper vQFX

This Vagrantfile will spawn 2 instances of vQFX (light) and 2 Ubuntu servers.
Both vQFX will be connected back to back with IP address and OSPF pre-configured on their interfaces.

## Requirement
### Resources
 - RAM : 3G
 - CPU : 1 Core (shared)

### Tools
 - Vagrant and Virtualbox
 - Ansible for provisioning (except for windows)

## Topology

        em0|                              em0|
    =============                      =============
    |           |  em3 OSPF area 0     |           |
    |   vQFX1   | -------------------- |   vQFX2   |
    |           | -------------------- |           |
    =============  em5 OSPF area 1     =============
        em6|                              em6|
    =============                      =============
    |    srv1   |                      |    srv2   |
    =============                      =============

# Provisioning / Configuration
Ansible is used to provision both vQFX with an IP address on their interfaces.
Both servers are preconfigured with an IP address and a route to their respective vQFX.
