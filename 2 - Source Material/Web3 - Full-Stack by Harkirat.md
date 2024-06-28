source - https://www.youtube.com/watch?v=zi0iR3UN-u0&ab_channel=HarkiratSingh

Problem statement - Solving problems where there is a need of data-modelling for training LLM Modals. Where in turn user from developing country do minimal tasks of data-labelling and pay the data-labelling users get micro payments through web3

Other problem - Network traffic should always high

**What to learn**
- Upload photos or assets in s3 - uploading through multer can cause assets to get wiped if server dies & security reasons
- Pay through large web3 wallets
- How to do this smart contract
- Handling payouts - solving problems like double payments
- Next.js

**Web2 part**
- s3/ object stores
- Pre-signed URLS - to upload in s3
- CDNs
- HTTP Servers
- DBs - postgres
- Async arch/ workers - one who talks to the block chain

**Web3 parts**
- wallet adapters - connect buttons
- Signing messages
- Transactions and signing Txns - debt & credit
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
		- Con here is backend is doing a lot of heavy lifting
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
- The users of this FE will withdraw from from admin wallet
- There should be minimum threshold, where user can withdraw from the admin wallet ($10 after you reach, you can withdraw from the wallet)
- Flow of withdraw
	- The *helper* / *labeler* user will send the userId and wallet address
	- Backend don't have browser wallets, the pop up is a frontend for the w3 wallet, we can access the private key
	- We can use this private key and store it in the BE and send Txns through Solana command line
		- This is an INSECURE way of doing this, as we should not keep private key in the EC2 machine
		- Proper way of doing it in the MPC architecture
		- This will send the Txn to the RPC node
		- The problem with this approach is this is not reliable
		- SOLUTION: we will do a locking mechanism,
			- We will do a lot of reconciliation
			- Once Txn is verified, we can deduce  from the balance
			- Or retry the Txn if not successful
			- Or revert the balance if failed
			- This will be done by the *worker/Txn Sweeper*
		- The Worker is responsible for scheduling in bg if the 'blockchain clogging'
		- *GET /nextTask* end point gets the next task from the DB
		- *POST /submission* submits the task response
		- *GET /payout* is a highly asynchronous endpoint where 
			- it submits to the Solana chain the Txn on the chain
			- Poll the Txn in DB which checks the blockchain and update the status like succeeded, failed etc
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
			- cloudfront is cheaper
			- More secure using 
			- faster than accessing the s3 bucket by itself
	- create pre-signed url
		- create a user that have limited access
		- backend can create a pre-signed url and supply to the user
		- we can directly upload to s3 but it is NO
		- goto IAM
			- Users
				- Create User called *presignedGenerator* which has access to our bucket to create a pre signed url for the user to upload rather than uploading to s3 directly
				- Only has programmatic access
				- attach policies directly
				- give Amazons3FullAccess or make narrower permissions
				- create security creds where nodejs process can generate presignedUrl
				- take credentials that we should put in the backend
					- ``AKS- I8UuGG5OHOII2JMKXSiaPMYas9pEahLmTfx7wo/O``
					- ``AKP - AKIA3FLDXTDRLMA3A7PY``
	- do not store aws creds in frontend
- Create 2 frontends
	- last parts
- Design the schema
	- Postgres + prisma
	- create the db in neon.tech
	- `postgresql://thumbsdb_owner:tR7JUZnmNvu9@ep-polished-dew-a18497y2.ap-southeast-1.aws.neon.tech/thumbsdb?sslmode=require`
	- get the credentials where we can connect BE with DB
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
	- (foreign key constraints, every Task will have options, means options will have task id related with it , and Task will have multiple options)
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
	- POST */signin*
		- create user & worker routers
		- Most web3 application has login with wallet address
		- import to the index - '/v1/worker' - '/v1/user'
			- /v1/user
				- */signin* - add a sign verification logic
					- jwt
						- clients cannot be trusted
						- jwt is created with a private key & secret
					- use jwt to do so
						- if username and password is right - it returns a jwt token from BE to FE
						- all future requests, they will send the jwt back and the BE can confirm
						- here we use address and signed_message then we return  a jwt 
						- check with the prismaClient if user exists
							- prisma.user.upsert (create/update data) -> not related
							- check if the walletAddress is present in the DB
							- if it is, then return the jwt signed userId as response
							- else, create a user with wallet Adress
							- then return the jwt token
	- GET /preSignedUrl
		- how to expose an endpoint where user can upload
		- add bucket name in PostObjectCommand and key -> specific folder
		- add a authMiddleware which verify the JWT token
			- jwt.verify the authHeader
			- if decoded has userId then add it to the req before calling the next() in the end
			- Add decoded userId from the token to the request that can be used by the route
			- else return response with 403 status
		- Generate pre-signed url through PUT pre-signed method
	- Let users upload the images through FE 1
	- POST /task
		-  Validate inputs from the user
		- if inavlid return 411
		- add express json middleware
		- use zod for validation of the input in *types* file
			- createTaskInput
				- options - array of  of objects containing imageUrl
				- title - string optional
				- signature
		- parse the data inside the route
			- if not success return 411, wrong input
			- else create the task
				- Title should be optional in the schema
				- options  - create a transaction (send 2 seperate quries together)
					- tx => { await query task, await createMany}
					- remove optionId from the transaction and migrate
	- GET /task
		- get task id from req
		-  get userId
		- find first with user_id and taskId
		- if no task found return 'you dont have access to this task'
		- findMany submission, and include the option with it
		- create result object which has *count* and *option with imageUrl*
		- iterate through the result and assign the count to 0
		- iterate through the response and add up the total count
		- return the result
- Support the endpoints in the FE 2
	- POST /signin
		- same as user
		- change the secret
		- create middleware
	- GET /nextTask
		- find task that user hasn't made a submission
		- get the userId
		- findFirst task where
			- where submission has no userId
				- select title and options and id
			- and done is false
		- add done to Task schema
		- if task is not found
			- return that there is no more task left to review
		- else return the task
	- POST /submission
		- we should control and check if the user deserves to submit the next task
		- extract the logic of getting the nextTask into db.ts file
		- we just pass userId into it
		- createSubmissionInput
			- taskId - string
			- selection - string
		- if parse is success
		- check if task id of getNextTask is same as the submission taskId
		- prevent user from letting user to make 2 submission and make money
		- ass unique worker_id for a task_id
		- create submission success case
		- give amount of task amount/ total number of submissions
		- return nextTask and amount
		- make a prisma Tx
			- first submission 
			- update the pending amount
			- store the amount in lamports 10^9
			- lamports - do not store floats in db, we store in db as int, we can avoid a lot of precision errors
			- 
	- GET /balance
		- findFirst
	- POST /payout -> dummy for 
		create Payouts schema
### Web3 bits

- Let users sign in and link their wallet address to their account (signing messages)
- Make user pay 50$ and generate a txn signature
- Make the backend verify the Txn signature before creating a task
- Store the private key on the server
- Create an RPC server on alchemy
- Let the users request payouts, submit the payout on the blockchain and put the Txn signature in the DB
- Write the worker that polls the DB and marks entries as succeeded/failed/processing 