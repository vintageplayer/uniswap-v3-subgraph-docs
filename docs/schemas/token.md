---
title: Token
sidebar_position: 3
---

|Field|Type|derivedFrom|Description|
|-|-|-|-|
|id | ID! | | Token Contract Address | 
|symbol | String! | | Token Symbol | 
|name | String! | | Token Name | 
|decimals | BigInt! | | No. of decimals in the token value | 
|totalSupply | BigInt! | | Total supply of the token | 
|volume | BigDecimal! | | Total token volume traded in swaps | 
|volumeUSD | BigDecimal! | | Total token value traded in swaps in USD | 
|untrackedVolumeUSD | BigDecimal! | | Total token value traded in USD, including pools with unreliable USD values | 
|feesUSD | BigDecimal! | | Amount of Fees taken from token swaps in derived in USD | 
|txCount | BigInt! | | No. of transactions across all pools that include this token  | 
|poolCount | BigInt! | | No. of pools containing this token | 
|totalValueLocked | BigDecimal! | | Liquidity across all pools for the token | 
|totalValueLockedUSD | BigDecimal! | | Liquidity across all pools for the token in terms of USD value | 
|totalValueLockedUSDUntracked | BigDecimal! | | Liquidity across all pools (including pools with unreliable USD values) for the token in terms of USD value | 
|derivedETH | BigDecimal! | | Price of token relative to ETH | 
|whitelistPools | [[Pool](./pool)!]! | | [Pool](./pool) entities which can can be used for reliable USD pricing of the token | 
|tokenDayData | [[TokenDayData](./tokendaydata)!]! | @derivedFrom(field: "token") | Link to daily stats for the token | 
