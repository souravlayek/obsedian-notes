# Setup User To Docker Group
---
tags: 
Created ON: 2023-04-11 23:26
Relates To: 

---

### To setup user to docker group we need to create a group
```bash
sudo groupadd docker
```

### Now just add your user to Docker
```bash
sudo usermod -aG docker $USER
```

Now Logout and log back in but **Restart** will be a better approach