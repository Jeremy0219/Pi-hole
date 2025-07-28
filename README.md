# Pi-hole
A customizable Pi-hole setup for network-wide ad blocking and improved privacy.

## Objective

The Pi-hole project was created to add a network-wide ad and tracker blocking solution using a lightweight DNS sinkhole. The focus is on improving network performance and privacy by filtering unwanted content at the DNS level. This project provided me with practical experience in network management, DNS configuration, and enhancing cybersecurity through traffic control.

### Skills Learned

- Advanced knowledge of DNS and network-level ad blocking techniques.
- Experience configuring and managing Pi-hole for optimal performance.
- Understanding of network traffic filtering and privacy enhancement.
- Familiarity with DHCP, DNS server settings, and network infrastructure.
- Practical skills in troubleshooting and maintaining network security tools.

### Tools Used
- Pi-hole for DNS-based ad and tracker blocking.
- Raspberry Pi as the hardware platform for hosting the Pi-hole server.
- Pi-hole web interface for management and monitoring.
- DHCP and DNS configuration tools for network integration.
- Network diagnostic tools for troubleshooting.
- SSH client used to remotely access and configure the Raspberry Pi from a Windows machine.
- Used curl to install Pi-hole and perform web requests in the terminal.
- Used dhcpcd to configure a static IP address on the Pi.
- Used neofetch to verify Pi details.
  
### Project Steps (with Screenshots)

Below is a step-by-step walkthrough of how I set up Pi-hole on my Raspberry Pi using PuTTY, `dhcpcd`, and other tools. Screenshots are included as well.

### 1. SSH into Raspberry Pi
**Tool used:** PuTTY  

Logged in to the Raspberry Pi from my Laptop using PuTTY


<img width="1915" height="1136" alt="putty-ssh-login" src="https://github.com/user-attachments/assets/ca1b3d0b-077d-49e5-bfc5-05b74199a869" />

### 2. Update and Configure the Pi
Ran the system update and configured basic settings with `raspi-config`

```bash
sudo apt update && sudo apt upgrade
sudo raspi-config
```

### 3. Set a Static IP Address
**Tool used:** dhcpcd.conf

Configured the static IP by editing the file:
<img width="1917" height="1140" alt="static-ip-setup" src="https://github.com/user-attachments/assets/3982e949-0d8f-495e-bebc-170672869e9f" />

### 4. Reboot and Reconnect via Static IP
Rebooted and SSH'd back into the Pi using the new static IP

```bash
sudo reboot
```

### 5. Install Pi-hole
**Tool used:** Curl

Ran the official install script using curl
```
curl -sSL https://install.pi-hole.net | bash
```

### 6. Set Web Admin Password
Set a password for the Pi-hole web interface

<img width="923" height="100" alt="setpassword for pihole" src="https://github.com/user-attachments/assets/1dda7745-2e06-4014-b7ba-01db97a737da" />

### 7. Run Neofetch
**Tool Used:** Neofetch

Verified system identity using neofetch

<img width="1898" height="407" alt="neo fetch system info" src="https://github.com/user-attachments/assets/776f2e1c-61d3-45c2-922c-723058a8d31d" />

### 8. Access Pi-hole Dashboard
Opened the Pi-hole web interface in a browser:
(Replace static-ip-address with static IP previously created)

```bash
http://<static-ip-address>/admin
```
<img width="1896" height="1135" alt="image" src="https://github.com/user-attachments/assets/880b1678-fde6-4c50-a133-ad4186d5429f" />

### 9. Change DNS Settings on Laptop
Opened IPv4/TCP Setting in network settings

Set Preferred DNS --> Pi-hole IP

Set Alternate DNS --> 1.1.1.1 or 8.8.8.8

<img width="483" height="553" alt="image" src="https://github.com/user-attachments/assets/dc9c72ae-9771-4486-a896-2694e2a05c9f" />

### 10. Confirm Pi-hole is working
Run
```bash
pihole status
```
Ensure it is running properly, it should say "Pi-hole blocking is enabled"
<img width="1187" height="597" alt="image" src="https://github.com/user-attachments/assets/bf8da0cf-9c46-48bd-93e3-11706916bd9e" />

### 11. Revisit Dashboard to see it in Action
Pull up the web admin dashboard again to show Pi-hole is live and actively blocking.
(This screenshot is from the pi-hole only running for 2 minutes)
<img width="1881" height="1135" alt="image" src="https://github.com/user-attachments/assets/a09f9a12-9574-42a8-b325-f4a5d9713e44" />




