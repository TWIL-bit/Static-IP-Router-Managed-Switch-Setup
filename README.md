#  Home Network Lab – Static IP Router & Managed Switch Setup



<br>


##  Project Summary  
This project documents the design and implementation of a home network lab environment using real hardware: a dedicated router, a managed switch, and an ISP gateway. The objective is to gain practical experience configuring static IP addressing, LAN/WAN architecture, subnet planning, router/switch management, and preparing for VLAN segmentation.


<br>

##  Project Goals  
- Configure and deploy static IP addressing for router WAN and LAN interfaces.  
- Establish a clear LAN subnet for internal devices (PCs, consoles) with managed DHCP.  
- Integrate a managed switch into the network to support wired devices and provide management interfaces.  
- Document network topology, IP plan, configuration steps and verification procedures.  
- Lay the groundwork for the next phase: VLAN segmentation, multi-subnet environments, inter-VLAN routing and security policies.



##  Hardware & Network Components

| # | Device | Model | Role |
|---|--------|--------|------|
| 1 | ISP Gateway | AT&T BGW320-505 | Provided by ISP. Internet ingress, NAT, initial DHCP. |
| 2 | Core Router | TP-Link Omada ER707-M2 | Acts as primary LAN gateway, DHCP server, routing engine. |
| 3 | Managed Switch | TRENDnet TEG-3102WS (Web-smart L2+) | Wired device connectivity, managed interface, VLAN-ready for upcoming expansion. |
| 4 | End Devices | PCs/Consoles | Wired endpoints within the LAN subnet, requiring consistent internet and local access. |

---

##  Network Topology





##  Steps for Configuration  

### 1. Router (LAN & DHCP Setup)  
- Connected a PC directly to the router’s LAN port.  
- Accessed the router web interface and changed the default LAN IP.
- Enabled DHCP on the LAN, specifying a scope to cover all wired clients.  
- Ensured the LAN subnet is isolated from the ISP gateway’s network for clarity and control.

screenshots of lan ip and dhcp


### 2. Router (WAN Static IP Configuration)  
- After linking the router WAN port to the ISP gateway’s LAN, I configured the router WAN with a fixed IP. 

    screenshots of wan ip page

### 3. Managed Switch Setup  
- Connected the switch to the router’s LAN port and assigned the switch a static management IP.  
- Verified access to the switch’s web interface from multiple wired PCs.  
- Connected all current wired clients to the switch.  

screenshots of management ip page

<br>


## 📚 Skills & Learning Outcomes  
- Defined and implemented a multi-layer network architecture: ISP gateway → router → managed switch → end clients.  
- Applied static IP assignment principles for core network devices (router WAN/LAN, switch).  
- Built familiarity with router DHCP scope, LAN subnet isolation, and switching infrastructure.  
- Gained hands-on experience managing wired device connectivity via managed switch.  
- Prepared a solid foundation for further networking tasks: VLANs, subnets, firewall rules, segmentation and security policies.

