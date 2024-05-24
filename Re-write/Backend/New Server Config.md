1) Update software - `apt upgrade & apt update`
2) Restart server - `shutdown now -r` - shutdown time and restart
3) Create new user
	- root is highest level of user with no much restrictions
	- Allows unrestricted access to OS
	- `sudo` - super user do, allows you to run commands like root
	- `adduser username`
	- `usermod`
1) Make the new user the superadmin
2) Enable login for the new user
3) Disable root login - always remove root access
	- Create auth key for the new user using ssh
		- create `authorized_keys` file in the .ssh
		- store the public key on the file