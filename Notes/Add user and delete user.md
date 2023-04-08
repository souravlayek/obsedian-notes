# Add user and delete user
---
tags: #server #self-hosted 
Created ON: 2023-04-09 01:39
Relates To: [[Setup a new server]]

---

## Add a new user
* Login as root by running `sudo su`
* Run this command `adduser <username>`
* Write all the necessary infromation
* Add to sudo group by running `sudo usermod -aG sudo newuser`

## Delete a user
* Login as different user
* and then login as root `sudo su`
* To delete only the user profile run `deluser newuser`
* To delete the user with home directory run `deluser --remove-home newuser`
