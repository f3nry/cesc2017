Dmitry Meshkov

Nodes in a blockchain store a State, required to validate transactions

State size continuously increasing

Big state problem
===============

Not validatablbe on low end hardware
Long validation on commodity hardware
users move to centralized services

Possible solution [improving auth dynamic dictionaries]:

Authenticated state
provide a proof of transaction correctness

limit state size economically
SPV mining do not keep state

Fee types
========

- Network fee
- Computation fee
- storage fee = K * size * lifetime
 
 fee = F[feeN, feeC, feeS]

 prepaid fee = rent box for at most Lmax blocks, paid in advance.
 postpaid fee = pay for resource used when output spent
 scheduled fee = decrease output periodically, after som e duration anyone can spend output, putting money back to the same script

 State size = sqrt((2 * Sblock * Ncoins) / K)

mining reward
==============

rewards align miner rationale
Additional blocks reward Ssize * K

Lost coin recirculation
======================

space-time fee provides a way to return coins into circulation

individual money is burned if fees not paid???

Links
====

ergoplatform.org
iohk.io
