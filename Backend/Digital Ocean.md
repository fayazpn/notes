- add your ssh public key
- name your server (droplets)
- to ssh into server
	- default user is root
	- to ssh from your pc, default uses `id_rsa` if you have specific private key link it with `ssh -i ~/.ssh/fsfe root@server_ip` (first user is root hence why `root@)



*** 
- To move nameservers from registrar to our server in DO 
- Add nameservers `ns1.digitalocean.com` (2&3)
- Add custom DNS in namecheap all the nameservers above
	- ns1, ns2, ns3
	- We are moving dns from registrar to DO           
	- We can do email forwarding for free