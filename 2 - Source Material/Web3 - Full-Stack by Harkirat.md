source - https://www.youtube.com/watch?v=zi0iR3UN-u0&ab_channel=HarkiratSingh

Problem statement - Solving problems where there is a need of data-modelling for training LLM Modals. Where in turn user from developing country do minimal tasks of data-labelling and pay the data-labelling users get micro payments through web3

Other problem - Network traffic should always high

**What to learn**
- Upload photos or assets in s3 - uploading through multer can cause assets to get wiped if server dies & security resasons
- Pay through large web3 wallets
- How to do this smart contract
- Handling payouts - solving problems like double payments
- Nextjs

**Web2 part**
- s3/ object stores
- Pre-signed URLS - to upload in s3
- CNDs
- HTTP Servers
- DBs - postgres
- Async arch/ workers - one who talks to the block chain

**Web3 parts**
- wallet adapters - connect buttons
- Signing messages
- Transactions and signing txns - debt & credit
- Indexing blockchains - why and ideal acceptance of payments
- RPCs
- Workers talking to blockchain

**High-level system design**
- Customer will upload thumbnails paying 'x' amount
	- *GET /generatePresignedUrl* -  discussed further below
	- *POST /task* - store image in s3
	- *GET /task* - getting polled by customers to check if it finished or not
- User will get the thumbnails (Helper FE)
	- *GET /nextTask*
	- *POST /submission* - click of preferred thumbnail
	- *GET /balance* - the rewards that are earned
	- *POST /payout* - checkout of balance
- The money paid by the Customer is given in the wallet
- The Users will checkout from the admin wallet
- DB is PG database
- Worker/Txn Sweeper - as blockchain is unreliable, we need  a worker to check if the Txn has paid out or not
- RPC Servers - Servers that lets us talk to the Blockchain (Network of computers that make up the blockchain)
	- When submitting the Txn, we submit to a RPC (We can have our own RPC)
	- Our BE sends req to RPC server with a Txn (QuickNode, triton)
##### Important Architecture Pattern

**Letting a user upload a photo in s3**
- Flow 1
	- Uploads from FE and store in BE 
		- Security vulnerability
		- Fill up the server
		-  Cannot create a distributed system
		- This should always go to a centralized network (CDN)
- Flow 2
	- Upload it in the object store
		- Bring from FE to BE
		- Then BE dumps to the s3
		- DONOT give password to the client, as user can tamper with it
		- CON here is backend is doing a lot of heavy lifting
- Flow 3
	- Pre-Signed URLS
		- instead of giving the user the complete control of s3
		- We give them a specific URL which will let the user upload to the s3 directly with restrictions (1 photo with size etc, limited permissions)
		- We should send req from FE to BE to generate a pre-signed url, no need of taking img to BE and proxying to the object store
		- The uploaded image will gave a url that backend can use 
		- Size and performance bottleneck is avoided as heavy lifting is given to AWS

****
**Letting users pay and verify payment to the backend**
This a web2 + web 3 problem
- Flow 1
	- Whenever a user wants to use your service, they pay and it goes to the admin wallet (easy)
	- When a user made a specific Txn for doing a service specifically (For a specific Task)
		- The user can verify by sending to backend Txn signature along with assets (images here) so the BE can verify
			- The problem here is if the user pays the money but internet goes down, but there is no way for backend to know about this as wallet cannot tell if Txn was made 
				- We are relying on the user to give us the Txn Signature
				- Solution: Store the Txn Signature in localstorage
		- Another user can snipe the Txn Signature and run service with other Users payment
			- Problem is we are not associating user wallets to the user account so that we know the Txn owner
			- Solution: Associate wallet with the user
		- SOLUTION: index the transactions (Ugly way)
			- Link the wallet to the account (Mapping userId with Wallet address)
			- Make useer create a req with Txn Signature (req body & Txn signature)
			- Do verification
				- Reject the Task
				- Or Create the task if approved

**Allowing labelers to payout $s to their own wallet**
- The labelers have their own frontend where they can do tasks and withdraw their cash
- Their frontend will pull out the images from the DB that is stored in the s3
- The usere of this FE will withdraw from from admin wallet
- There should be minimum threshold, where user can withdraw from the admin wallet ($10 after you reach, you can withdraw from the wallet)
- Flow of withdraw
	- The helper user will send the userId and wallet address
	- Backend dont have browser wallets, the pop up is a frontend for the w3 wallet, we can access the private key
	- We can use this private key and store it in the BE and send Txns through solana command line
		- This is an INSECURE way of doing this, as we should not keep private key in the EC2 machine
		- Proper way of doing it in the MPC architecture
		- This will send the Txn to the RPC node
		- The problem with this approach is this is not reliable
		- SOLUTION: we will do a locking mechanism,
			- We will do a lot of reconciliation
			- Once Txn is verified, we can deduce  from the balance
			- Or retry the Txn if not successful
			- Or revert the balance if failed
			- This will be done by the *wroker/Txn Sweeper*
		- The Worker is responsible for scheduling in bg if the 'blockhain clogging'
		- *GET /nextTask* end point gets the next task from the DB
		- *POST /submission* submits the task reponse
		- *GET /payout* is a highly asynchronous endpoint where 
			- it submits to the solana chain the Txn on the chain
			- Poll the Txn in DB which checks the blockchain and update the status like succeded, failed etc
				- if succeeded then deduct from the balance of db
				- if not then retry which will start the whole process again



## Steps to follow

### Web 2

3 applications in monorepo for code sharing

- Create Nodejs express backend
	- init nodejs project
	- configure tsconfig
	- create src directory
	- in index.ts 
		- start a server
- Create aws creds
	- create a bucket
	- name it
	- block all public access
	- cloudfront (CDN of the AWS)
		- significantly cheaper
		- every CDN has a pop (edge server) - where on request it is taken from source and cached in pop
		- So its better to use CDN than getting data from s3 url itself (expensive)
		- off WAF
	- create a cloudfront
		- origin access control settings - create a new one
		- This will give you a policy
		- so create an s3 bucket and serve content through the cloudfront
	- create pre-signed url
		- backend can create a pre-signed url and supply to the user
		- we can directly upload to s3 but it is NO
		- goto IAM
			- Users
				- Create User
				- attach policies directly
				- give Amazons3FullAccess or make narrower permissions
				- create security creds where nodejs process can generate presignedUrl
				- take credentials 
	- do not store aws creds in frontend
- Create 2 frontends
	- last parts
- Design the schema
	- Postgres + prisma
	- create the db in neon.tech
	- get the cred where we can connect BE with DB
	- install prisma
	- init prisma
	- design the database with the schemas
		- User - ones creating actual task
			- id Int @id @default
			- address String @unique
			- name String
			- tasks Task[]
			- (There is no username password, we are logging with the wallet)
		- Worker - same like user
			- will have multiple submissions
			- will have single Balance
			- balance_id
			- pending_amount
			- locked_amount
			- balance 1 to 1 with Balance
		- Balance - 
			- id
			- amiunt
			- worker_id
			- worker Worker - unique for a worker
	- every user can create task
		- Task 
			- id
			- title String
			- options Option[]
			- user_id Int
			- signature Strijg
			- amount string
			- user User
			- submisisons submisitons[]
		- (Every task will have one unique user)
		- Options - every task has multiple options
			- id
			- image_url required
			- option_id Int - makes queries faster
			- single task for each option
			- will have many submissions
	- (foreign key constraints, every Task will have options, means options will have task id related with it , and Task will have multiple tasks)
	- every worker will create submissions
		- model Submission 
			- id
			- worker_id
			- worker - unique worker
			- option_id Int
			- option - submission will have unique option
			- task_id 
			- task - each submission will be unique for a single task
			- amount
	- By default user querying this schema will take time to fetch
	- no we intro a new modal called SubmissionCache {} - cache the number of submissions given task - to get it get all the submissions for all the options of the task
		- make entry in submission cache everytime a submission is made - REMOVED in the video
	- migrate the primsa - way of telling the db that new tables are added
		- name the migrations
- Support the following endpoints
	- POST /signin
		- create user & worker routers
		- import to the index - '/v1/worker' - '/v1/user'
	- GET /preSignedUrl
	- Let users upload the images through FE 1
	- POST /task
	- GET /task
- Support the endpoints in the FE 2
	- POST /signin
	- GET /nextTask
	- POST /submission
	- GET /balance
	- POST /payout -> dummy for now
### Web3 bits

- Let users sign in and link their wallet address to their account (signing messages)
- Make user pay 50$ and generate a txn signature
- Make the backend verify the Txn signature before creating a task
- Store the private key on the server
- Create an RPC server on alchemy
- Let the users request payouts, submit the payout on the blockchain and put the Txn signature in the DB
- Write the worker that polls the DB and marks entries as succeeded/failed/processing 



