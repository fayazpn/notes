
2024-07-07 19:08

Status: #child 

Tags: [[backend]]

# Databases

**Primary Key** - Ids that help a row in table to identify uniqly
**Foreign Key** - *Primary Key* of other tables that exists in different table


We need to disconnect the db when  server is stopped, we achieve it by listening *SIGINT* signal interrupt on *process*, if not db connection will stay open

```js
process.on('SIGNIT', () => {
	server.close(() => functionShutdownDB())
})
```

# References






