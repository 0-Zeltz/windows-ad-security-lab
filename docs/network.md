## Topology

![OPNsense Dashboard](./images/opnsense-interface.png)

### Components

- Windows 11 Pro – Domain-joined workstation  
- Ubuntu Server – Apache Web Server  
- Domain Controller – Active Directory and authoritative DNS  
- Layer 2 Switch – LAN connectivity and VLAN segmentation  
- OPNsense Firewall – Internet gateway, DHCP server, and upstream DNS  

---

## Interfaces

<!-- Insert OPNsense home interface screenshot here -->

The network infrastructure was designed to isolate the internal network from direct Internet access, routing all traffic through the OPNsense firewall to simulate a real enterprise architecture.

---

## Gateway

OPNsense was configured as the default gateway for all internal hosts, using IP address: 
- 192.168.1.1/24

---

## DNS

Initially, OPNsense was configured as the default DNS server for the entire network. However, since Active Directory requires the Domain Controller to act as the authoritative DNS server, client machines were reconfigured to use the DC for name resolution.

---

## Forwarder

The Domain Controller received the DNS Server role and was able to resolve internal Active Directory DNS records and external domain names using DNS root hints. After configuring a DNS forwarder, external name resolution was handled by the upstream DNS server instead.
