
## Lin commands
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
- `root` - user of highest level
- `sudo` - superuser do
- `adduser` - to add new user
- `usermod` - user modification
	- `usermod -aG sudo fayaz-pn` - changes the user to sudo user
- `su` - switch user command
- `/var/log/auth.log` - contains all the logs of auth
- 



## Vim commands 
- `:wq` - write and quit
- `:u` - undo the changes
- `:q!` - force quit without saving
- `echo $0` - name of your shell
