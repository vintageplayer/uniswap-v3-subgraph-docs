---
title: UniswapDayData
sidebar_position: 14
---

|Field|Type|derivedFrom|Description|
|-|-|-|-|
|id | ID! | | Timestamp rounded to current day by dividing by 86400 |
|date | Int! | | Timestamp rounded to current day by dividing by 86400 |
|volumeETH | BigDecimal! | | Total daily volume in Uniswap derived in terms of ETH |
|volumeUSD | BigDecimal! | | Total daily volume in Uniswap derived in terms of USD |
|volumeUSDUntracked | BigDecimal! | | total daily volume in Uniswap derived in terms of USD (including tokens with unreliable USD value) |
|feesUSD | BigDecimal! | | Amount of swap fee taken during the day in terms of USD |
|txCount | BigInt! | | No. of transactions that occurred during the day |
|tvlUSD | BigDecimal! | | TVL locked at the end of the day in terms of USD |