# Change Hostname of the server
---
tags: #self-hosted 
Created ON: 2023-04-09 01:38
Relates To: [[Setup a new server]]

---

Type the following command to edit /etc/hostname using nano or vi text editor:  
```bash
sudo nano /etc/hostname
```  
    Delete the old name and setup new name.
Next Edit the /etc/hosts file:  
  ```bash
  sudo nano /etc/hosts
  ```
Replace any occurrence of the existing computer name with your new one.
Reboot the system to changes take effect:  
```bash
sudo reboot
```
