
2024-06-27 19:06

Status: #child

Tags: [[backend]] [[programming-language]]


## Linux commands
- `cat` - print
- `mkdir -p ./test/sdf` - create sub folders
- `cd ~` - home directory
- `/` - root
- `touch` - creates file with last modified time
- `rm -rf` - delete recursively
- - every time you change shell config reload it with `source echo $SHELL`
- `echo password >> foo` - adds the text password to the file foo after creating the file
- `gawk` - pattern scanning and processing
- in linux pattern matching is done through columns
- `grep` - command line tool to do pattern matching
	- `ls -la | grep fsfe`
- `ping` - to check if network is up
- `traceroute` - to see the network hops
- `netstat` - displays all the networking information related to the system
- `less` - instead of displaying full file like `cat` it shows like 1 at a time
- `dig` - gathers information about dns servers
- `root` - user of highest level - does not double check anything we do
- `sudo` - superuser do
- `adduser` - to add new user
- `usermod` - user modification
	- `usermod -aG sudo fayaz-pn` - changes the user to sudo user (add to sudo group)
- `su` - switch user command
- `/var/log/auth.log` - contains all the logs of auth
- create a *.ssh* folder in the newly created users *home* dir
- paste the *public key* of ssh to the *authorized_keys* file
	- By doing this we can directly login as the newly created user
	- Also we change the file permission of the ssh file using `chmod 644`
- The reason we disable the root user is
	- The moment we launch a server, random users will be trying to connect to the server
	- So it is important we disable the root login
	- `r` - read
	- `w` - write
	- `x` - execute
- `sudo vi /etc/ssh/sshd_config` - ssh deamon process that is running
	- change the permission to 'no'
	- After changing it to no, you will actually have root user, we are just disabling the root login permission
- `sudo service ssh restart` - whenever a process is edited it needs to be re-started
- Be very careful as you can get locked out of the server
	- Flow - Root user -> create another user -> switch to user 2 -> delete root



## Vim commands 
- `:wq` - write and quit
- `:u` - undo the changes
- `:q!` - force quit without saving
- `echo $0` - name of your shell







