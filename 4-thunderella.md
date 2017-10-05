Thunderalla: blockchains with optimistic instant confirmation
Rafael Pass

Two agreements: honest nodes agree on linear order and that txs are available fast

Classical: PBFT, Paxos
===========

fast most of the time
complex, max 10 nodes

Assume 2/3(n+1) is honest
Assume 1/3n malicious

New: Blockchain
===============
Simple, Robust, Slow

slowest as the worst case network speed

Thunderalla
============

Confirmation in 2 actual network rounds in the optimistic case

leader online and honest
3/4 committee honest
blockchain is majority honest

Assume 3/4(n+1) is honest

fall back to blockchain when leader can't be decided

actors = accelerator (leader), blockchain miners, commitee (recent miners, stakeholders, or self-election (?))

Protocol:

leader propose new txn
committee acks with 3/4 majority (notorized)

blockchain records evidence of leader honesty

miners tell blockchain everything they know
miners kick leader or commitee if they see bad k blocks

enter grace period for next k blocks
then slow mode

questions
======

how is the leader and committee elected?
if you can't always trust the leader or committee, then how do you quantify the risk of instant confirmation?
is mining done on the blockchain during optimistic mode?

links
====
chain.com = manual leader election
thundertokens.org
