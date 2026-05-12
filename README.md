# Home Network & VLAN Lab (TP-Link ER707-M2 + Managed Switch)

## Overview
This project documents the design, configuration, and troubleshooting of a home network lab built using a TP-Link ER707-M2 router, an AT&T BGW320 gateway in IP passthrough mode, and a TRENDnet managed switch. The goal was to create a stable, segmented LAN environment for learning enterprise networking concepts including DHCP, VLANs, NAT, and switch management.

---

## 🧰 Hardware Used
- TP-Link ER707-M2 Router
- AT&T BGW320 Gateway (ISP modem/router)
- TRENDnet TEG-3102WS Managed Switch
- Multiple client devices (Windows/Linux PCs)

---

## ⚙️ Network Configuration

```text
Internet
↓
AT&T BGW320 (IP Passthrough Mode)
↓
TP-Link ER707-M2 (Main Router)
↓
TRENDnet Managed Switch
↓
Client Devices
```

### Router Configuration
- LAN Subnet: `192.168.80.0/24`
- Gateway: `192.168.80.1`
- DHCP Server: Enabled
- WAN: Public IP via IP Passthrough

<br>
<img width="1429" height="1271" alt="RouterLanSettings" src="https://github.com/user-attachments/assets/70a46c95-4e8d-439a-846d-6e15e5a65f10" />

<br>


### Switch Configuration
- Management IP: `192.168.80.2`
- Subnet Mask: `255.255.255.0`
- Default Gateway: `192.168.80.1`
- Operating Mode: Layer 2 switching

<br>
<img width="1620" height="1090" alt="SwitchInterface" src="https://github.com/user-attachments/assets/1263bb5e-94c2-4abb-b479-7598b934ca38" />

<br>

---

## 🔀 Key Concepts Implemented

### IP Passthrough
Configured on AT&T BGW320 to allow the TP-Link router to receive a public WAN IP and act as the primary router, eliminating double NAT.

### DHCP Management
Centralized DHCP handled by TP-Link router to assign IPs within `192.168.80.0/24`.

### VLAN Configuration
Initial VLAN misconfiguration caused DHCP conflicts and network isolation. Resolved by correctly assigning switch ports as untagged members of the correct VLAN.

<br>
<img width="1597" height="1007" alt="VLANPortAssignment" src="https://github.com/user-attachments/assets/d60c233d-ca62-4a04-8c02-3bfdf3a6e49c" />
<br>

---

## ⚠️ Issues Encountered & Resolved

### DHCP Conflicts
- Devices were receiving `192.168.0.x` instead of `192.168.80.x`
- Cause: AT&T gateway still partially serving DHCP

### VLAN Misconfiguration
- Ports were incorrectly assigned as both tagged and untagged across VLANs
- Resulted in loss of network access and switch isolation

### Network Lockouts
- Misconfigured VLAN changes caused loss of access to router and switch interfaces
- Resolved by direct PC-to-router connection and restoring correct VLAN port membership


---

## 🧠 Key Learnings

- Difference between NAT, IP passthrough, and routing roles
- VLAN tagging vs untagged traffic behavior
- Layer 2 vs Layer 3 networking responsibilities
- Importance of port membership in managed switches
- Troubleshooting DHCP conflicts in multi-device environments

---

## 📌 Final Outcome

A stable, segmented home network with:
- Clean single-subnet LAN (`192.168.80.0/24`)
- Managed switch integration
- Proper router-to-switch architecture
- Functional IP passthrough setup
- Hands-on VLAN troubleshooting experience

---

## 🚀 Future Improvements
- VLAN segmentation for PCs, IoT, and lab environments
- Firewall rule implementation between VLANs
- Network monitoring using packet analysis tools
- Advanced routing and security configurations
