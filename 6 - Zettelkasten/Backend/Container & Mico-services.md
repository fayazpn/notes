
2024-07-08 11:32

Status: #child 

Tags: [[backend]]

# Container & Mico-services

Different types of Architecture patterns are
- **Monolith** - Software architecture of tightly coupled services
- **Micro-services** - Software architecture of loosely connected services
	- Easier to create in your own style
	- Needs co-ordination


### Containers - Docker
We can run chunks of application in separate, leading to *zero-down time*
Containers are OS independent
They are faster startup

When we install node image, we are installing node in *Alpine node* version which is very light version of linux just designed to run this
`FROM node:19-alpine.3.16`

As installed node will run user we need to change it to node user, we need to change the ownership
`RUN mkdir -p /home/node/app/node_modules && chown -R node:node /home/node/app` - create directory for the application
`WORKDIR /home/node/app` -  our working directory,  all the COPY, RUN command will be ran relative to this folder

`COPY package*.json ./` -  copy all package files from local machine to the work directory

`USER node` - change user to node, following executions will be done as node user

`RUN npm install`

`COPY --chown=node:node . .` -  copy entire contents of the local dir to the work directory with the copied files being owned by node user and group

`EXPOSE 3000`

`CMD ["node", "app.js"]`

`docker build -t node-fsfe .` - docker build with name node-fsfe in the current directory

`sudo docker -d -p 3000:3000 node-fsfe` - run docker in the background, with port server-port:docker-port image name

### Orchestration & load balancing

- Managing multiple instances of containers is called orchestration
- Example : Kubernetes
**Load Balancer** - checking the cpu usage and distributing the trffic
Scheduling algorithms -
- Round robin
- IP hashing
- Random choice
- Least connection
- Least Load

##### NGINX Load balancing
```

```




 
# References






