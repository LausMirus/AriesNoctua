# AriesNoctua
"AriesNoctua — a hidden forge of networks, shadows of Linux, vaults of secrets, and the art of security.”


Aries-Noctua is a private home lab designed for learning, experimentation, and managing personal infrastructure. The lab focuses on multiple areas of IT and cybersecurity, including:

Networking: Configuring and testing secure network setups.

Linux Systems: Practicing Linux administration, commands, and scripting.

Storage & File Sharing: Managing private storage and secure file access.

Web Hosting: Deploying and maintaining self-hosted web services.

Cybersecurity Practice: Testing security setups, penetration testing, and learning defensive techniques.

The lab provides a safe, self-contained environment for hands-on learning, experimentation, and skill development in real-world IT systems.

___

### FINAL ARCHITECTURE
```
Ubuntu Server
 ├── Static IP (Tailscale virtual IP)
 ├── SSH
 ├── Samba
 ├── Shared Folder
 ├── CX access
 └── Tailscale VPN
```
___

## step-by-step guide to setup Server 
---
1. Ubuntu setup
2. Configure Wifi
   _ Setup static ip
   _ Netplan config
   _ Apply config
   _ verify config
3. config SSH
4. Config Samba
5. Create Shared Folder
6. Fix Ownership
7. Set Permissions
