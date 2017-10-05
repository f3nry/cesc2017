Lefteris Kokoris-Kogias

Swiss Federal Institute of Technology

Private/permissioned ledgers: HyperLedger, R3

problem: if two miners win at about the same time, the chain forks

Bitcoin-NG, ByzCoin
=================

Permanent transaction commitment in seconds
700 TPS demonstrated
Low-power verification on light mobile devices

Practical Byzantine Fault Tolerance needs a static consensus group

Use collecive signing rounds to implement PBFT prepare, commit phases
efficient tree-structured communication
sign offs compressed into 1 signature

reduce round cost from o(n^2) to O(N)

Opening the consensus group

One share per block = % of shares & hash-power

block mining = two distinct functioniatlities [Transaction Verification, Leader Election]

key blocks { microblock microblock microblock }

SkipChains
========

Traversability, offline verification

forward and backward traversability

many levels of linking

Omniledger
========

Byzcoin doesn't scale up, but maintains Decentralization and security
Elastico maintains decentralization and scale but less security
RsCoin scales with security, but centralization

Componenents: RandHound, ByzCoinX, Atomix

Maintains large list of miners, group miners via randhound

Each shard runs BuzCoin and manages subset of state
Transactions processed by one or a few shards

instead of a tree, use groups

capture causal dependencies
use a Block-DAG (directed acylic graph)

CoSi must be used for compact proofs
Optimistically trust the lient for liveness
anyone can take over the clients job after a time-out

Two layer architecture

- fast shard validate optimistically in seconds
- strong shards ensure safety in minutes
- breaks the latency-throughput tradeoff

summary
======

Skipchain + ByzCoin & RandHound = Omniledger

links
=======
https://bford.github.io/2017/08/01/skipchain
