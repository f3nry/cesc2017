addressing bitcoin's privacy problem

Alessandro Chiesa

Bitcoin
=======

Reveals to the public: sender, receiver, amount

infered details:

- medical info
- current and past location
- merchant cash flow

GLBA: Gramm-Leach-Bliley Act

"Those are just addresses"
=========================

Transaction graph can show patterns across multiple wallet addresses.

Mitigation
==========

Use new address for each payment
Launder money with others (tumbling)

quantitative exploits:

- MMLN17
- KFTS17

Fungibility
==========

__a dollar is a dollar regardless of its history__

Bitcoin is not fungible

- different pople value the same coin differently
- same person values different coins differently
- heuristic: new coins more valuable than old ones
- central party that determines correct value

if data is encrypted, how to check payment valididity?

bitcoin comprismised on privacy in favor of accurate accountability

Zerocash
=======

works on any append-only ledger

sender, receive, and amount are hidden

payment transactions take few seconds to produce,
< 1KB per transaction and take milliseconds to verify

Basic Intution
===========

Add evidence that encrypted data is valid = proof

proof = I am publishing three ciphertexts. They contain sender, receiver and amount. Amount has not been double spent. I have generated a cryptographic proof that all of this is true.

what kind of cryptographic proof?
================================

one-way proof / non-interactive / zero knowledge = nothing revealed beyond the truth of the statement

succient = cheap to verify

ZK-SNARK

libsnark.org

what is the statement being proved?
==============================

Attempt #t

abstract coin =

two transaction types: 

1.
2.

Attempt #1
==========

coin = random string (serial number)

two transaction types: 

1. Consume 1btc to create a value1 coin w serial
2. consume the coin w/ serial number

Good: cannot double spend
Bad: spend linkable to its mint, anyone can spend!

derp

Attempt #2
==========

coin: serial number hash randomness = commitment

two transaction types: 

1. Consume 1btc to create a value1 coin w/ commitment cm.
2. Consume the coin w serial number sn

Good: cannot double spend, others cannot spend
Bad: spend linkable to its mint

derp

Attempt #3
=========

coin: serial number hash randomness = commitment

two transaction types: 

1. Consume 1btc to create a value1 coin w/ commitment cm.
2. (sn, proof) Consume the coin w/ serial number. cm is in list of prior commitments. cm = COMMM(sn; r)

Good: cannot double spend, others cant spend, spend and mint unlinkable
Bad: fixed denomination

Attempt #4
=========

coin: stacked commitment with value

two transaction types: 

1. Consume v btc to create a value v coin w/ commitment cm.
2. (sn, proof) Consume the coin w/ serial number. cm is in list of prior commitments. cm = COMMM(v,k; r) & k = COMM(sn, s)

Good: cannot double spend, others cant spend, spend and mint unlinkable
Bad: value still public, only hides sender

Attempt #5
=========

halp
HIDE ERRYTHING! magically

Attempt #6
=========

spend my coin, create coin for receive

bad: join and split coinsr

Final design
===========

minting and pouring

types:

- payments
- join coins
- split coins
- making change
- pay transaction fees

Beyond Privacy & Fungibility
=====================

can add generic truth statements onto the transaction

**what policies are desirable to balance privacy and fungibility and oversigh/accountablilty?**

further investigation
=====================

could value be a non-integer data field, protecting privacy of anything? yes

what's the algorithm for generating a provably unique serial number?
