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
	- POST /task - store image in s3
	- GET /task - getting polled by customers to check if it finished or not
- User will get the thumbnails
	- GET /nextTask
	- POST /submission - click of preffered thumbnail
	- GET /balance - the rewards that are earned
	- POST /payout - checkout of balance
- The money paid by the Customer is given in the wallet
- The Users will checkout from the admin wallet

