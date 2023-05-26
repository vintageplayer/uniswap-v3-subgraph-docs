---
title: Mint
sidebar_position: 9
---

|Field|Type|derivedFrom|Description|
|-|-|-|-|
|id | ID! | | Mint Entity ID. Format: `<transaction hash>#<index in transaction.mints array>` |
|transaction | [Transaction](./transaction)! | | [Transaction Entity](./transaction) in which the mint event was emitted |
|timestamp | BigInt! | | Timestamp of the block in which which the mint event was emitted |
|pool | [Pool](./pool)! | | [Pool](./pool) in which the mint event was emitted |
|token0 | [Token](./token)! | | token0 entity of the pool |
|token1 | [Token](./token)! | | token1 entity of the pool |
|owner | Bytes! | | owner of the position to which the liquidity was minted |
|sender | Bytes | | the address that minted the liquidity |
|origin | Bytes! | | The EOA address that initiated the transaction |
|amount | BigInt! | | Amount of liquidity minted |
|amount0 | BigDecimal! | | Amount of token0 minted |
|amount1 | BigDecimal! | | Amount of token1 minted |
|amountUSD | BigDecimal | | Mint value derived in USD based on available prices of tokens |
|tickLower | BigInt! | | Lower tick of the position  |
|tickUpper | BigInt! | | Upper tick of the position |
|logIndex | BigInt | | Order of the Mint Event within the logs of the transaction |