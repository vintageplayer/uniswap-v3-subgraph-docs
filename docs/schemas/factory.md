---
title: Factory
sidebar_position: 1
---

|Field|Type|derivedFrom|Description|
|-|-|-|-|
|id | ID! |  | Factory Contract address |
|poolCount | BigInt! |  | No. of pools created using the factory |
|txCount | BigInt! |  | No. of all the transactions through pools mananged by the factory |
|totalVolumeUSD | BigDecimal! |  | Total Volume all time in derived USD |
|totalVolumeETH | BigDecimal! |  | Total Volume all time in derived ETH |
|totalFeesUSD | BigDecimal! |  | Total Swap Fees all time in derived USD |
|totalFeesETH | BigDecimal! |  | Total Swap Fees all time in derived ETH |
|untrackedVolumeUSD | BigDecimal! |  | Total Volume all time, including less reliable USD values |
|totalValueLockedUSD | BigDecimal! |  | TVL derived in USD |
|totalValueLockedETH | BigDecimal! |  | TVL derived in ETH |
|totalValueLockedUSDUntracked | BigDecimal! |  | TVL including tokens with unreliable USD prices in USD |
|totalValueLockedETHUntracked | BigDecimal! |  | TVL including tokens with unreliable USD prices in ETH |
|owner | ID! |  | Current Owner of the factory contract |