Steven Goldfeder

problem: difficulty reconciling physical receipt of goods with transfer of money online

traditional solution: intermediary takes risk

cryptocurrency payments are irreversible, escrow is necessary

Silk Road protocol
==========

buyer -> silk road
buyer thumbs up
silk road -> shop

vulnerable to hacks

how can trust of mediator be minimized?
============

limit mediator role

deposit money in escrow without mediator
can withdraw without mediator as long as no dispute

malicious mediators = theft, DoS

privacy = internal hide use of escrow, hide evidence of dispute from external

escrow via multisig
============

t of N multisig

buyer key1
shop key2
mediator key3

requires 2 of 3 parties involved to complete transaction

optimisic protocol

implementations:

escrowmybits
bitrated
openbazaar

downside: not externally hiding, not dispute hiding, vulnerable to denial of service

escrow via encrypt-and-swap
==============

ECDSA Dist-KeyGen

happy path: distribute private keys initially until buyer says i received books, then seller can withdraw

sad path: mediator decrypts full key from buyer share of key and then buyer withdraws

downside: still vulnerable to denial of service

mediator still needs to be online

escrow via encrypt-and-swap with group escrow
===============

majority vote from group of mediators

surety bonds
==========

mediator proof of stake implementation


