# Home Network Hardware Lab

This project documents a small home network built with physical networking hardware to practice IP addressing, DHCP configuration, device management, and troubleshooting.

## Hardware Used
- TP-Link Omada VPN Gateway
- TRENDnet 10-Port Multi-Gig Web Smart Switch
- Windows client devices

## Objectives
- Configure static management IP addresses for network infrastructure devices
- Configure DHCP for client devices connected to the switch
- Validate connectivity between endpoints and the gateway
- Practice troubleshooting using common network tools

## Network Configuration
- Omada Gateway: 192.168.80.1
- TRENDnet Switch: 192.168.80.2
- DHCP Pool: 192.168.80.100 - 192.168.80.200

## Configuration Steps
1. Accessed the Omada gateway web interface using its management IP address.
2. Assigned a static management IP address to the gateway.
3. Configured a DHCP address pool for client devices.
4. Accessed the TRENDnet switch web management interface and assigned a static management IP address.
5. Connected client devices through the switch and verified successful DHCP lease assignment.

## Validation
- Confirmed clients received valid IP addresses from the configured DHCP pool.
- Verified default gateway reachability using ping.
- Confirmed local network communication between connected devices.
- Reviewed endpoint network configuration using ipconfig.

## Skills Demonstrated
- TCP/IP addressing
- DHCP configuration
- Web-managed switch administration
- Gateway configuration
- Network troubleshooting
- Physical network hardware deployment
