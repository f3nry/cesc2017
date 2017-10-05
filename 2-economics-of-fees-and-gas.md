Jordan Earls
qtum

Gas = measuring computation resources
IoT = internet of things

Storage is expensive
==================

External code = contract containing data, seldom updated commonly accessed
Internal Code = contract hardcoding, constant data at deployment
Storage = hashmap storage, any commonly updated granular data
Transaction Data = data stored in each transaction, quickly accumulate with more executions

Transaction data method is the most expensive, grows linearly

External data storage is most costly when updating

Rationale for expensive storage
=================

Makes light wallets cheaper
Storage is permanent
More storage slows down future accesses

Whats wrong
========

Storage is free - transaction data is the real cost
External contract storage hurts SPV user experience (download excessive data)
IoT devices benefit from caching in the chain
High gas costs discourage bad practices

sha3 string comparison is cheaper !!

gas models are terrible because of processor variations

Qtum DGP can be used to adjust gas costs on the fly

When measuring gas cost is more expensive than simply executing the code :(

example code: earlz.net
