
2024-07-01 11:50

Status: #child 

Tags: [[blockchain]] [[solana]]

## Transactions

Transactions are like actions that are submitted to the network to get something done. Transactions includes different tasks to be done, these are called *instructions*, they also needs *signatures*, which is like an approval.

**Parts of a Transaction**

- **Instructions**: These are like the different tasks you want to do. They can include actions such as moving tokens from one account to another.
- **Accounts**: These are like the places where data is stored. Instructions use these accounts to perform actions.
- **Signatures**: These are like the green lights that say the transaction is okay. They show that the actions are authorized by the account holders.

**Details of a Transaction**

- **Signature Format**: Every transaction has one or more signatures that act as approvals.
- **Message Format**: A message is what’s inside a transaction. It has accounts, block information, and instructions.
- **Message Header**: This part of the message contains details like how many signatures are needed, how many accounts are read-only, and how many accounts don’t need signatures.
- **Account Addresses**: These are like the addresses of the places where data is stored. Some accounts are for reading, some for writing, and they’re organized in a specific way.
- **Block-hash**: This is like a special code that tells when a transaction happened. If it’s too old, the network won’t accept it.
- **Instruction Format**: An instruction is like a task for a program to do. It includes details about what program should do it and which accounts it should use.
- **Compact-Array Format**: This is a way to put a bunch of things together in a neat package.
- **Account Address Format**: An account address is like an ID for a place where data is stored.

This structure helps keep everything organized and secure.
*Solana transaction is atomic in nature, if one or more instructions fail, the whole transaction fails*


# References






