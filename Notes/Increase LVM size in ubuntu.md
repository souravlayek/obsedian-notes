# Increase LVM size in ubuntu
---
tags: #ubuntu #self-hosted 
Created ON: 2023-04-09 01:33
Relates To: [[Dev Ops Engineering]]

---

### How to force ubuntu to take the entire LVM storage?

Below commands can help on that
```bash
sudo lvm
```
Above command will open the lvm shell
```bash
lvextend -l +100%FREE /dev/ubuntu-vg/ubuntu-lv
```
This command will add the free available storage Take care of `/dev/ubuntu-vg/ubuntu-lv` This should be the root path main drive name
Exit from lvm by running `ctrl+d OR cmd+d`
Then Run the below command and it will be ready
```bash
sudo resize2fs /dev/ubuntu-vg/ubuntu-lv
```
