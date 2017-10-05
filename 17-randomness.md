1955: Large table of random numbers

Goals
======

Availability: successful protocol termination for up to f = t- 1 malicious nodes
Unpredictablility: output not prematurely revealed
Unbiasability: output distrubted uniformly at random
Verifiability
Scalability

Current Approaches
================

With TTTP: NIST randomness beacon

Without TTP:

- bitcoin
- slow cryptographic hash functions
- lotteries
- financial data

(t, n)-threshold security model:

- coinflipping (Cachin)
- distributed key generation (Kate)

Strawman 3
=========

Secret-share random inputs
Problem: dishonest nodes can send bad shares

Randshare
========

Strawman 3 + verifiable secret sharing (Fieldman, 1987)
O(n^3) computational costs

RandHound
=========

Verifiability by third parties
Performance better than O(n^3)

untrusted client uses a large set of nearly stateless servers
on deman (via configuration file)
one-shot approach

Setup:

Run: announced in advance, publicly available config
Client: lottery authority
Servers: a set of reputable servers
....

Publicly-VSS (Schoenmakers, 1999)
VSS with zero knowledge proofs
no communication between servers

collective signing (Syta, 2016)
client publicly commits to their choices

create protocol transcript from all sent/received messages

Shard participants into constant size groups
- secret sharing with everyone too expensive
- run secret sharing only insides groups
- collective randomness: combination of all group outputs

how to securely assign participants to groups?

client selects server grouping
availability might be affected (self-DoS)

pigeonhole principle: at least one group is not controlled by the adversary
collective signing: fixing the secrets that contribute to randomness

complexity: O(c^2n)

RandHerd
=======

Continuous, leader-coordinated randomness generation
small randomness proof size (Schnorr signature)
better performance than O(n)

Decentralized randomness beacon

built as a collective authority
randomness on demand at frequent intervals

Collective randomness = collective Schnorr signature

problem: failing nodes influence output

solution:

arrange nodes into schnorr signing groups (stinson, 2001)

Approach: setup + round function

Setup

1. Elect a temporary leader via lowest ticket
2. Obtain randomness Z from RandHound
3. Create TSS groups using Z and generate groups keys Xi
4. Certify aggregate public key X using Collective Signing

Randomness generation

1. Cothority leader brodcasts timestamps v
2. TSS-CoSi
    a. produce group schnorr signatures
    b. aggregate into collective schnorr signature
    c. public (c, r) as collective randomness

Complexity: O(c^2log(n))

Links
=====
Go implementations: https://github.com/dedis
Paper: https://eprint.iacr.org/2016/1067.pdf
pretty HTML templates: https://html5up.net/
