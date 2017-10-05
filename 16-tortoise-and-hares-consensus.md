Tal Moran

consensus:

- miners compete to solve a puzzle
- first to solve is elected leader and decides on last 10 minutes of history
- gets reward

First permissionless election protocol

The bad:

- limits on throughput due to latency
- high variance / long time to get a reward = encourage centralization
- problems with rationality

Meshcash
========

framework for distributed consensus

- race free consensus
    - no leader election required
    - has nice rationality properties

- idea: a slow but sure tortoise potocol
    - eventual consistence
    - uses traditional byzantine agreement protocols
    - long-term: gaurantees irreversibility
- fast and unreliable hare protocol
    - if it works, consensus is fast
    - deals only with recent blocks

hard to design a single protocol with all properties

Gossip network
============

p2p networking
    - every onde passes on a new gossip to all neighbors

Partially synchronous
    assume bound on network delay
    assume bound on local clock difference

Timing message ordering under adversarial control

messages are always broadcasted

to broadcast m:
    - send m to adversary
    - adversary choose when to deliver m to each honest part
    
bounded asynchrouny

Generalized Blockchain
=======================

Pass, Seeman, shelat

blockchain is an ordered list of messages

Chains of two honest players differe only in last T blocks
Chains at time r,s of an honest player differe only in last T blocks
After T consectuvie messaeges, chains of all honest parties grow by at least T/g
Fraction of blocks contributed by honest parties is at least u

consensus
irreversibility
liveness
fairness

Bitcoin rules
===========

All bocks must have PoW
Only blocks on longest chain are valid
each transaction can appear in at most one block

Transactions ordered according to blocks

Consensus on block ordering is the only important pieces

Why Bitcoin Works
==============

Max block generation rate for Adv is q
Honest users generate blocks at rate (1-q) > q
Longest chain will always grow faster and therefore will always remain longer

honest users want to grow the longest chain

Adv probability of ever catching up depends only on q and lead of longest chain

Incenvitves
==========

block reward for every valid block to miner

transaction fees given to block that includes those TXs, allows users to pay for mining (negligible compared to block reward)

Bitcoin bit-problems
==================

Hard bound on block generation rate
implies long wait for rewards

to speed up blockchain: make blocks larger

Meshcash Motivation
==================

Unbounded block rate
Race free
    honest players reward can't be reduced by other's actions

adv can't win by doing something bad if honesty can't loose

no leader election

Meshcash Overview
=================

Extend chain to mesh (layered DAG)

Enter layer is mined concurrently

unbounded layer width -> unbounded block rate


previous work either:

- no security proof
- assume only rational adversary or give up on full consensus

Meshcash mining
===============

example:

```
  5    5
4   4 4
3   3
2 2 2 2
1 1 1
```

point to every block in previous layer
point to every block that has in-degree 0
increment layer counter if you see Tmin blocks in previous layer

syntactic validity for layer-i block
can by determined from block itself
PoW is valid
all pointed blocks are syntactically valid
Points to at least Tmin layer-(i-1) blocks

Contextual Validitiy
====================

honest parties receive messages in different order
we need total ordering of blocks

longest chain is context validitity in bitcoin

Tortoise consensus
=================

vote on validity

block contains enough data to reconstruct miners vote
add voting edges to recent blocks

voting edge = ?

recursive voting rule: use only blocks in view, discard undecided

honest blocks vote +1

hare consensus
=============

honest users can differ only on very recent blocks

margin for blocks in hare interval always large

Race-freeness
===========

honest blocks guaranteed to be valid

Fallback to tortoise consensus
=============================

adversary can keep honest users balanced between +1/-1 for maliciously-generated blocks

assume a common public coin

open questions
==============

exact linear time tortoise validitity
