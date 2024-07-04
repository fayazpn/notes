
2024-07-04 14:25

Status: #child 

Tags: [[backend]] 

# Server Security

- We use firewall and keep softwares up to date
- **Port** -  communication endpoint which maps to specific process or network service
- Just connecting to computer does not do anything, we need to connect it to a port

### Fire-wall
- **ufw** -  uncomplicated firewall
- Gives options to set if a user is allowed or not allowed
- `ufw allow/deny/reject http/https/ssh` - deny does not give response, which is good against ddos attacks
- Do not close port 22 as it used for SSH, you might lock yourself out of the server


### Updates
As the lack of updates is one of major source of hacks, we can make system do it for us.

`sudo apt install unattended-upgrades` - installs the package
`sudo dpkg-reconfigure --priority=low unattended-upgrades` - turn it on low priority

# References






