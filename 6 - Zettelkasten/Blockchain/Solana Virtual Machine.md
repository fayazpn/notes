
2024-07-01 11:52

Status: #child 

Tags: [[blockchain]] [[solana]]

# Solana Virtual Machine

**SVM** is high-performance execution engine which is capable of parallel processing of smart-contracts on the SOL chain, it supports large number of parallel-threads, enable fast and efficient execution of complex programs, it is hyper parallelized transaction processing engine designed to scale horizontally across GPUs and SSDs, other blockchains are single threaded computers.

_Solana was one of the first few chains to support parallel transaction execution (not just signature verification) in a single shard_. (A **shard** refers to a single processing unit that supports parallel transaction execution). It works in a way like OS driver technique called scatter-gather, where Txs upfront states what state they will read write while executing.

It also has other features like
 - Specialized memory allocator, which reduces overhead of mem-alloc, and custom thread scheduler which distribute work across multiple threads.



# References






