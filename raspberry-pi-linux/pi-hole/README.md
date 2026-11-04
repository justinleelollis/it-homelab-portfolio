# Pi-hole DNS-Based Ad Blocking

## Project Overview

I installed Pi-hole on a Raspberry Pi 4 to learn how DNS filtering works and how network traffic can be managed to block unwanted domains.

Pi-hole acts as a DNS sinkhole. When a device makes a DNS request, Pi-hole checks the requested domain against its configured blocklists. Requests matching blocked domains are prevented from resolving normally.

## Hardware and Environment

- **Device:** Raspberry Pi 4 (4GB RAM)
- **Operating System:** Raspberry Pi OS
- **Client Device:** Laptop running Fedora Linux
- **Software:** Pi-hole

### Installation Method
I connected to the Raspberry Pi remotely using SSH from my Fedora laptop and performed the Pi-hole installation through the terminal. This allowed me to install and configure the software without needing a monitor, keyboard, or mouse connected directly to the Raspberry Pi.


## Implementation

### 1. Pi-hole Installation
- Installed Pi-hole on the Raspberry Pi.
- Accessed the Pi-hole web administration dashboard.
- Confirmed that the DNS filtering service was running.
  
### 2. Blocklist Configuration
- Added an ad-blocking list containing approximately 77,000 domains.
- Verified that the list was available in Pi-hole.
- Confirmed that DNS requests matching blocked domains were being filtered.

### 3. Fedora DNS Configuration
- Opened the network settings in Fedora Linux.
- Configured the connected Wi-Fi network to use the Raspberry Pi's IP address as its DNS server.
- Reconnected to Wi-Fi to apply the DNS configuration.

### 4. Testing and Verification
- Accessed the Pi-hole Query Log.
- Browsed websites from the Fedora laptop.
- Confirmed that DNS requests appeared in the Query Log.
- Verified that some requests were marked as blocked.

## Challenges and Lessons Learned

One thing I learned is that DNS-based ad blocking does not remove every advertisement. Pi-hole blocks requests to domains included in its filtering rules, but some advertisements are delivered through the same domains as regular website content.

I also learned how to configure a Linux device to use a custom DNS server instead of relying on the DNS server provided automatically by the network.

I learned that my AT&T router does not allow users to manually change their DNS settings. Because of this, Pi-hole is currently configured manually on each device. I will be getting a new router soon and will update this documentation once I have it configured.
## Current Status

**Completed:**
- Pi-hole installation
- Initial adlist configuration
- Fedora manual DNS configuration
- DNS query monitoring
- Verification of blocked requests

**Future Improvements:**
- Expand and evaluate blocklists.
- Investigate advertisements that are not being blocked.
- Integrate Pi-hole into my planned MikroTik router and managed-switch home lab.
- Document DNS troubleshooting and network configuration.

## Skills Practiced

- Linux administration
- SSH and remote server administration
- DNS fundamentals and configuration
- DNS filtering and sinkholing
- Raspberry Pi configuration
- Network troubleshooting
- Log analysis and monitoring
- Technical documentation

This project is part of my ongoing IT home lab portfolio as I develop practical skills in Linux administration, networking, and systems administration.
