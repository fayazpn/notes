
2024-06-29 12:36

Status: #child 

Tags: [[backend]]

# NGINX Server Config

`root /var/www/html` - Serves the page as the default page when we visit the server IP
`location / {` - we can config routes in NGINX just like our apps
`try_files` - directory like proxy pass

### Proxying NGINX to Node.js file

`curl https://deb.nodesource.com/setup_19.x | sudo -E bash -`
`sudo apt-get install nodejs`
`sudo apt install git`

### Application Setup

1. Establish application file system
	1. Change ownership so that we don't have to keep using the `chown` 
		`sudo chown -R $USER:$USER /var/www` - change ownership recursively assign user to myself 
	2. Create `app` folder in `/var/www` and create a node.js folder
	3. We should create a *virtual configuration* file which establishes control between NGINX and node.js, so that when NGINX receives a request, it identifies and routes to the node.js app, we need to proxy NGINX to the NodeJS server
	4. Create a proxy
		1. `sudo vi /etc/nginx/sites-enabled/fsfe`
```bash
server {

        listen 80 default_server;
        listen [::]:80 default_server;

        root /var/www/html;
        index index.html;

        server_name 134.122.78.52;

        location / {
                proxy_pass http://127.0.0.1:3000/
        }
}
```


`nginx -t` - validates all the config files before running
In the conf file, we should only allow *sites_enabled* for our domain to point nginx to the new server `sudo vi /etc/nginx/nginx.conf`

`pm2` - process manager which will keep the node.js process alive even if we close session from our end

`pm2 start app.js`

To restart the node.js app when events like server reboot, we can config through pm2
`pm2 save`
`pm2 startup`

### GZIP
- Compression algorithm used in nginx
	-  configs can be found in `/etc/nginx/nginx.conf`

### SUBDOMAIN
- Create A record in your self hosted DNS
- Config create server proxy blocks
	- NOTE: this is different from default config
- Config in `nginx.conf`

### WebSocket
```
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection "upgrade";
```
This is applied in `/etc/nginx/sites-enabled/fsfe`
in the `location / {}`
# References
[[Server Security]]





