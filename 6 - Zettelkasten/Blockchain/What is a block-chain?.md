
2024-06-30 18:26

Status: #child 

Tags: [[blockchain]]

# What is a block-chain?

It is the underlying technology with which the bitcoin is implemented,
It is a chain of 'blocks', where data is stored with timestamp at a regular intervals.
In case of the bitcoin, it is a ledger of transactions with time-stamps stored in a block,
Incase a new Txn is made, we don't re-write the block, where as we add it as a new entry to the new block.

These blocks are ordered chronologically and shared across thousands or millions of computer, so there is no single point of failure.
So there are two main benefits.

- Transact and contribute to a shared ledger of information whilst,
- Being able to trust the ledger will always be true

There are two types of blockchains

- **Permission-less blockchain** : It is how the ledger is updated and securely maintained by people who do not trust each other, but here there is incentive for these people who maintain this ledger. ex: Payments for bitcoin mining.
	When a person does a transaction in the BTC network, all the validators compete to create a block full of transactions that is happening in the network.
	The network operates in a consensus mechanism called "PoW" where its like trying billions of keys to open a treasure chest.
	The winner of this competition is decided by solving a puzzle, which takes approx. 10min to solve with computing,
	Once the winner is found, he shares the block with all rest of the BTC network who verify that it is legit.
	The important part of the tech is that system is only secure as long as the *honest* nodes collectively control majority of the mining power (51%). In practice it is almost impossible for a attacking nodes to control of this amount of nodes, as it would be _almost impossible_ for a single entity to gain control of that much hash rate simultaneously.

- **Permission-ed blockchain** - It is mechanically same, but here there are no incentives for the miners as they are trusted for the validating the ledger
	It is mainly used for as a replacement for traditional server systems.





# References






