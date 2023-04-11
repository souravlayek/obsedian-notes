# Install Docker in Ubuntu
---
tags: #server  
Created ON: 2023-04-11 23:19
Relates To: [[Dev Ops Engineering]] [[Docker]]

---

### Uninstall old docker instance if already exist
```bash
sudo apt-get remove docker docker-engine docker.io containerd runc
```

### Update and Upgrade
```bash
sudo apt-get update && sudo apt-get upgrade -y
```

### Install few pre-requisites
```bash
sudo apt-get install \
   ca-certificates \
   curl \
   gnupg
```

### Add docker's official GPG keys
```bash
sudo mkdir -m 0755 -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

### Use this below command to setup repositories
```bash
echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

## Now ready to install docker

### Update once again
```bash
sudo apt-get update
```

### *Remove GPG keys if there is any error*
```bash
sudo chmod a+r /etc/apt/keyrings/docker.gpg
sudo apt-get update
```

### Install latest Docker with some necessary packages
```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

Now Docker is Ready But you need to run `sudo` before every command to prevent that you can use [[Setup User To Docker Group]] 
