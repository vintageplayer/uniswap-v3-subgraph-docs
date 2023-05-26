---
title: PoolHourData
sidebar_position: 16
---

|Field|Type|derivedFrom|Description|
|-|-|-|-|
|id | ID! | | PoolDayData Entity ID. Format: `<pool.address>-<Timestamp rounded to the hour by dividing by 3600>` |
|periodStartUnix | Int! | | Timestamp rounded to hour by dividing by 86400 |
|pool | [Pool](./pool)! | | [Pool Entity](./pool) for which the daily metrics are tracked |
|liquidity | BigInt! | | In range Liquidity at the end of the hour |
|sqrtPrice | BigInt! | | Pool Price at the end of the hour |
|token0Price | BigDecimal! | | Price of token0 in terms of token1 at the end of the hour |
|token1Price | BigDecimal! | | Price of token1 in terms of token0 at the end of the hour |
|tick | BigInt | | Actice Tick at the end of the hour |
|feeGrowthGlobal0X128 | BigInt! | | Global Fee Marker Value for token0 at the end of the hour |
|feeGrowthGlobal1X128 | BigInt! | | Global Fee Marker Value for token1 at the end of the hour |
|tvlUSD | BigDecimal! | | TVL available at the end of the hour derived in USD |
|volumeToken0 | BigDecimal! | | Total hourly volume in token0 |
|volumeToken1 | BigDecimal! | | Total hourly volume in token1 |
|volumeUSD | BigDecimal! | | Total daily volume in USD |
|feesUSD | BigDecimal! | | Total swap fee taken during the hour in terms of USD |
|txCount | BigInt! | | No. of transactions in pool executed during the hour |
|open | BigDecimal! | | Open Price of token0 |
|high | BigDecimal! | | High Price of token0 |
|low | BigDecimal! | | Low Price of token0 |
|close | BigDecimal! | | Close Price of token0 |