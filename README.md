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
* apply the netplan config using the command :-<br>```sudo netplan apply```<br>
* verify the ip using ``` ip a ```.
___
### **3. Install and config SSH**<br>
* **Before installing SSH , update your system using the command** ```sudo apt update```.<br>
* then install ssh ```sudo apt install openssh-server -y```<br>
* then check the SSH service ,using the command ```sudo systemctl status ssh```<br>
* check your ssh service is active ```ssh username@host_ip```<br>
___

### **4. Install and config Samba**<br>
* for installing samba, use the command ```sudo apt install samba -y```<br>
* after install, setup the *smba.conf* file using command
```sudo nano /etc/samba/smb.conf``` and replace the content to [smb.conf](./smb.conf)<br>
* now create a passkey for samba using command ```sudo smbpasswd -a your_password```<br>
* now restart the service using the command ```sudo systemctl restart smbd```<br>

___
### **5. Creating a NAS dir** <br>
* ```sudo mkdir -p /srv/nas```<br>
* **make sure that ownership premission for the NAS is correct, for fixing the permission use the command** ```sudo chown -R username:group /full/path/of/the/NAS``` ***replace the username, group and path with your username, group and path***<br>
* now fix the mode permission, use the command ```sudo chmod -R 775 /full/path/of/the/NAS/dir```***replace the path with your path***<br>
___
### 6. Install and setup Tailscale 
***tailscale is used for remote access to the server***
* ```curl -fsSL https://tailscale.com/install.sh | sh``` use this command to install tailscale<br>
* after install,up the service```sudo tailscale up```<br><br>
 ***now check the ip of tailscale0 interface and use that ip for secure remote login from anywhere***

  ___
  
