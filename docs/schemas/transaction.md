---
title: Transaction
sidebar_position: 8
---

|Field|Type|derivedFrom|Description|
|-|-|-|-|
|id | ID! | | Transaction Hash |
|blockNumber | BigInt! | | Block Number where the transaction was added to the chain |
|timestamp | BigInt! | | Timestamp of the block where the transaction was added to the chain |
|gasUsed | BigInt! | | Amount of Gas Units Consumed to execute the transaction |
|gasPrice | BigInt! | | Cost of one unit Gas paid for the transaction |
|mints | [[Mint](./mint)]! | @derivedFrom(field: "transaction") | [Mint](./mint) entities created in this transaction |
|burns | [[Burn](./burn)]! | @derivedFrom(field: "transaction") | [Burn](./burn) entities created in this transaction |
|swaps | [[Swap](./swap)]! | @derivedFrom(field: "transaction") | [Swap](./swap) entities created in this transaction |
|flashed | [[Flash](./flash)]! | @derivedFrom(field: "transaction") | [Flash](./flash) entities created in this transaction |
|collects | [[Collect](./collect)]! | @derivedFrom(field: "transaction") | [Collect](./collect) entities created in this transaction |
