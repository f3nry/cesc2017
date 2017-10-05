Karl Floersh

Economic overview of casper
==========================

Layering PoS on top of PoW with Casper the Friendly Finality Gadget

Phase 1 of deploying PoS on ethereum

Becoming a validator = any ETH holder can become a valdiator by depositing ETH into the casper smart contract

- Give larger incentive to work with
- Impose larger economic penatlites to bad actors

if 2/3 of the validators commit on a checkpoint, then finalize

if two conflicting are finalized then at least 1/3 of total deposits will be slashed

Slashing conditions = ??

Economic incentives
==============

Once the checkpoint is finished, validators get rewards

__read: discouragment paper__

Increasing the finality time of a blockchain by a constant factor causes a constant loss of utility

reward scales based on individual contribution to checkpoints

if the chain continues, the forks would diverge and both would finalize

Discouragement Attacks
====================

Validators see high reward for validating

Expected return reduced
total deposited ETH reduced
attacker requires less ETH to violate safety

Casper and Cryptoeconomics
=======================

not perfect :(

considerations:

- cost of violating safety
- cost of violating safety after discouragement
- adding extra protocol costs to attacker
- .. more

Links
====

https://karl.tech
