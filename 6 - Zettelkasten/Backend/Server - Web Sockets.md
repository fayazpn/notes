
2024-07-04 18:23

Status: #child 

Tags: [[backend]] 

# Server - Web Sockets

 HTTP request close after req-res cycle
 Where as WS is persistent  bi-directional comm bw client and server, The socket is open the whole the time once opened, should be closed explicitly
### Web-socket server

- require the web-socket server
- create a new WebSocketServer `const wss = new WebSocketServer({ server: server})`
- create a listener which has call back function to be called on the connected web-socket
```js
wss.on('connection', () => {
	const noClients = wss.clients.size;
	console.log(noClients)
})
```

`wss.broadcast` - broadcasts to all the connected clients, it is not a build in method, but a custom function used to broadcast to all client using  of `*forEach*` in the function, so that it is re-usable

`wss.readyState` - is the state of the web-socket from the list of enums with values such as `OPEN`

`wss.send` - called on induvidual web-socket connection, used to send data to a specific connected client, used when you need to send response upon request


**WS in HTTP &. HTTPS (Client side)**

In html file, we need to connect the WS on these 2 different protocol

`const proto = window.location.protocol = 'https:' ? 'wss' : 'ws';`

After knowing the protocol create the WS based on it using `new WebSocket(..${window.location.host})`

`ws.onmessage(() => response)`

# References






