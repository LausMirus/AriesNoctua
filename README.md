# AriesNoctua
"AriesNoctua — a hidden forge of networks, shadows of Linux, vaults of secrets, and the art of security.”


Aries-Noctua is a private home lab designed for learning, experimentation, and managing personal infrastructure. The lab focuses on multiple areas of IT and cybersecurity,
<details>
 <summary> Including: </summary>

Networking: Configuring and testing secure network setups.

Linux Systems: Practicing Linux administration, commands, and scripting.

Storage & File Sharing: Managing private storage and secure file access.

Web Hosting: Deploying and maintaining self-hosted web services.

Cybersecurity Practice: Testing security setups, penetration testing, and learning defensive techniques.

The lab provides a safe, self-contained environment for hands-on learning, experimentation, and skill development in real-world IT systems.
</details>

___

### FINAL ARCHITECTURE
```
Ubuntu Server
 ├── Static IP (virtual IP)
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
   - Setup static ip
   - Netplan config
   - Apply config
   - verify config
3. config SSH
4. Config Samba
5. Create Shared Folder
6. Fix Ownership
7. Set Permissions
___

### **1. Ubuntu Setup** <br/>

Install Ubuntu OS in any old (potato) pc<br/>
**while Booting Ubuntu OS make sure that** :-
  - Use Ubuntu LTS version
  - Baremetal installation required
  - Avoid full software installation
  - Only install essential net-tools and utils...
 
### **2. Config Wifi** <br>
 * to find current network interface <br>
 ``` ip a ``` <br>
* to setup static ip and disable DHCP, type the  command given below in terminal <br>
 ```sudo nano /etc/netplan/01-network-manager-all.yaml``` <br>
 you can use any other text editor rather than nano <br>
* then add this [netplan](./Netplan.yaml) code and save it.<br>
* apply the netplan config using the command :-<br>```sudo netplan apply```
