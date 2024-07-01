
2024-06-30 19:23

Status: #child 

Tags: [[blockchain]] [[solana]]

# Intro to Solana

Build to address the limitations faced by block-chain like Etherium & Bitcoin.
One of the main feature is **Speed & High Transaction Volume** - upto 65,000 TPS and average 4000 TPS

One of the unique aspect of Solana is - **Proof of History** - it provides a verifiable and permission-less source of time in the block-chain, which enables parallel processing and networks increased over-all throughput

Solana is built on other tech such as **Proof of Stake** consensus algo and Tower Byzantine Fault Tolerance (BFT) consensus mechanism.

### Proof of Stake

The main problem with Bitcoin's **Proof of Work** consensus is that there can only be one 'winner', which means 99% of the energy used is attributed to the attempts of 'loser', which is not efficient and sustainable.

Solana uses **Proof of Stake** to overcome this problem, also employs unique leader-rotation strategy to manage the validator roles within its system.

*Solana employs a unique leader rotation approach to manage validator roles within its cluster. The system operates with a single leader responsible for generating ledger entries at any given time, enabling all validators to replicate identical ledger copies. This single-leader model, while efficient, presents the risk of a malicious leader censoring votes and transactions. To counter this, the cluster pre defines a leader schedule for each epoch, assigning the leadership role to different nodes in a rotated manner.*

- **Leader Schedule Rotation and Rejecting Blocks:** Imagine in team setting, other people in the team will only accept documents that are created by the designated leader for that turn.
- **Changing Leaders and Identifying Them:** These leader turns are then planned ahead of time. This schedule is regularly updated to keep things fair. 
- **Making Sure Leaders Are Fair:** To prevent any unfair control, the time between updating the schedule and it becoming active is set according to the previous day’s plans. This helps avoid anyone trying to manipulate things for their benefit.
- **Handling Complicated Situations:**  In such cases, the time between updating the schedule is adjusted based on how long these complications last. This adjustment makes sure everyone is on the same page.
- **Choosing Leaders Carefully:** The ones who contribute more have a better chance of being chosen as leaders. This approach helps protect the team from any attempts to harm the process.

### Proof of  History

It is like a clock which establishes order of events. **PoH** generates time-stamps for each transaction and action on the network. Which helps nodes to verify the chronological order of events, enabling parallel processing and improving the scalability.

In Solana, The PoH timestamps are used to enhance the security and efficiency of the PoS consensus. Validators can reference the PoH timestamps to ensure that the blocks they are validating are in the correct order, eliminating the need for additional consensus rounds. This integration of PoH and PoS enables Solana to achieve high transaction throughput, low latency, and overall scalability.

# References
[[Solana - Account Model]]
[[Solana Transactions]]
[[Solana Virtual Machine]]
[[Solana Commands]]





