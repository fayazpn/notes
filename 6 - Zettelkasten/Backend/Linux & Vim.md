
2024-06-27 19:06

Status: #child

Tags: [[backend]] [[programming-language]]

- Most of the process will be in the `etc` file
- `var` contains files that are used in run time

## Linux commands
- `sudo !!` - run prev command with sudo permission
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
- `grep` - command line tool to do pattern matching - INSIDE THE FILE
	- `grep -i 'fayaz' /var/www`
	- `ls -la | grep fsfe`
- `find` - To find WHERE
	- `find /bar -type f -name foo.txt`
	- `find directory option file/folder name`
- `ping` - to check if network is up
- `traceroute` - to see the network hops
- `netstat` - displays all the networking information related to the system
- `less` - instead of displaying full file like `cat` it shows like 1 at a time
- `head` - display the first part of the file
- `tail` - display the last part of the file
- `dig` - gathers information about dns servers
- `root` - user of highest level - does not double check anything we do
- `sudo` - superuser do
- `adduser` - to add new user
- `usermod` - user modification
	- `usermod -aG sudo fayaz-pn` - changes the user to sudo user (add to sudo group)
- `su` - switch user command
- `/var/log/auth.log` - contains all the logs of auth
- `/var/log/syslog` - contains all the system logs
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
- `sudo vi /etc/ssh/sshd_config` - ssh daemon process that is running
	- change the permission to 'no'
	- After changing it to no, you will actually have root user, we are just disabling the root login permission
- `sudo service ssh restart` - whenever a process is edited it needs to be re-started
- Be very careful as you can get locked out of the server
	- Flow - Root user -> create another user -> switch to user 2 -> delete root
- `chmod 600` -  Used to change the permission of the of the file or folder, 
	- In Unix-like systems, permissions are defined for three types of users:
		1. **Owner**: The user who owns the file.
		2. **Group**: Users who are in the same group as the file.
		3. **Others**: All other users.
	1. Permissions are represented as calculated sum of in octal numbers
		 - **Read (4)** - r
		- **Write (2)** - w
		- **Execute (1)** -  x
			Nothing is set to execute by default
		The command `chmod 600 filename` sets the following permissions:
		
		- **Owner**: Read and write (4 + 2 = 6)
		- **Group**: No permissions (0)
		- **Others**: No permissions (0)
	- Common use cases are Sensitive files and config files.
	- rwx rwx rwx - owner (fayaz) group (sudo/other group) everyone else 
- `ssh -Tv git@github.com`
- `pkill <process>` -  to stop a running process
- `stat -c %a <file_name>` - Permissions as numbers
- `less /etc/services`
- `nmap <server_ip>` - gives you the list of the open ports in a computer, 
	- in our remote server port 3000 will be open by default because of the node app, we need to close it.
- `which bash` - gives the location of the bash
- **Shell script**
	- Begins with localtion of the bash `#! /usr/bin/bash`
- **Cron** - `minute hour day(month) month day(week sh`
	- `crontab -e` - provides the editor to add the cronjob
	- `* * * * * sh /var/www/app/github.sh 2>&1 | logger -t <your-script>`
	- by default the logs of cron are not written in syslog, if not done explicitly
- **Standard Streams** - Every command in Linux have *stdin*, *stdout*, *stderr*
- `>` - overwrite to file, `>>` - append to file

## Vim commands 
- `:wq` - write and quit
- `:u` - undo the changes
- `:q!` - force quit without saving
- `echo $0` - name of your shell
- In *NORMAL* mode just type `/` to search for certain string
- *CR* Means Enter Key - Character Return
- Vim will remember the last cursor position
- **Modes**
	- i is *Insert* new text
	- *Normal* mode is edit more
		- Esc or Ctrl + c
	- *Visual* mode is for highlighting text
	- *:* is command mode for executing command
- `x` - delete single character
- `zz` - centers the screen
- `hjkl` - movement keys
- `w` - hop by word to start of non white space word
- `dd/ shift + v+d` - delete a line
- `u` - undo
- *yank* - to copy to location, it will not goto system clipboard
- `yyp` - yank and paste below
- `yyP` - yank and paste above
- `V` - select the linew
- `V + y / p` - yanks and pastes the visual region
- `d` - delete the selected items in visual mode
- deleted items can be pasted with `p`
- `:reg` - is history of yanked or deleted 
- `i` - insert inside
- `a` - insert outside
- `I` - first non whitespace character in start
- `A` - end of the line with or without whitespace
- `o` - insert mode below the cursor
- `O` - insert mode above the cursor
- `:set scrolloff=8` - scroll view
- `7dd`- delete 7 lines
- `:set number` - sets the number line
- `:set relative` - sets relative number line
- `init.vim` - config for neovim
- `:h option` - gets the help menu of the option
- `:h ctrld + D` - popup menu
	- ` tab`
		- `Ctrl n` - navigate menu options
		- `Ctrl p`
- `G` - goto bottom
- `gg` - goto top
- `vim` - opens folder in vim
- `:Ex` - explore, open another file on the same buffer
- `:Vex` - vertical explore
- `:Sex` - Split explore
- `Ctrl + w` - new window option
	- `+ l` - move to the left window
	- `+ r` -  move to the right window
	- `+ s` -  split navigate
	- `+ v` - vertical navigate
	- `+ O` - closes all the window except the current buffer
- `mapleader` - placeholder for the key
- `nnoremap` - 
	- `n` - mode like insert *i*, command *c*, terminal *t*
	- `nore` - non recursively
	- `map` - covention to map the right aside to the left command 
	- `:so %` - source the file and re-execute the vimrc in the current buffer (*%*)
- Edit
	- `:e` - with `Ctrl + D` gives menu where we can goto the file directly
- Mark
	- `m + <Capital Letter>` - to mark a point in the code
	- `' + <Capital Letter>` - to naviagate to the marked point
	- Lower case - is for buffer level marks
- `:reg` - register of all the executed commands
	- `%` - current file
	- `#` - previous file
- `Ctrl + 6` - alt file switcher from the register - used when editing two files
- `Ctrl + o` - Jumplist, where you navigate back to where you come from
# References
chmod cheatsheet - https://quickref.me/chmod








