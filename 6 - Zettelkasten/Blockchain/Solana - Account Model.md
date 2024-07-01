
2024-06-30 20:49

Status: #child 

Tags: [[blockchain]] [[solana]]

## Solana - Account Model

**Everything in Solana is an Account**
In other blockchains, like Etherium all the tokens are stored in a single **account**

But in Solana, different tokens stored in our wallets all have their own separate account.

And what is an **Account**? Well _an Account is a data structure which holds information of various kinds so it’s essentially the basic unit of storage on Solana_.
- It is where we store texts
- Store balances of wallet
- Deploy smart contracts

**Account Structure**:  Each account is represented by a 256-bit address. An account can hold various types of data, including cryptocurrency balances, program code for smart contracts, and account-specific state information. Whereas in other blockchain both logic ad the state of the smart contract are stored together.
Ex: For example, the ERC-20 contracts on Ethereum store logic (e.g. transfer function) and state (user balances) in a single account.


In Solana logic and state are stored separately, which makes Solana a highly performant blockchain
- *Program Account* - The account which holds the logic of the program
- *Data Accounts* - Accounts which holds the states


# References





