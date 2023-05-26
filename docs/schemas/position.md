---
title: Position
sidebar_position: 6
---

|Field|Type|derivedFrom|Description|
|-|-|-|-|
|id | ID! | | Position NFT Token ID |
|owner | Bytes! | | Position NFT owner's address |
|pool | [Pool](./pool)! | | [Pool](./pool) where the position staked the tokens |
|token0 | [Token](./token)! | | token0 entity of the pool |
|token1 | [Token](./token)! | | token1 entity of the pool |
|tickLower | [Tick](./tick)! | | Lower [Tick Entity](./tick) of the position |
|tickUpper | [Tick](./tick)! | | Upper [Tick Entity](./tick) of the position |
|liquidity | BigInt! | | Total liquidity added by the position |
|depositedToken0 | BigDecimal! | | Total amount token0 ever deposited to the position |
|depositedToken1 | BigDecimal! | | Total amount token1 ever deposited to the position |
|withdrawnToken0 | BigDecimal! | | Total amount token0 withdrawn to the position (excluding fees) |
|withdrawnToken1 | BigDecimal! | | Total amount token1 withdrawn to the position (excluding fees) |
|collectedFeesToken0 | BigDecimal! | | Total amount token0 fee collected |
|collectedFeesToken1 | BigDecimal! | | Total amount token1 fee collected |
|transaction | [Transaction](./transaction)! | | [Transaction entity](./transaction) in which the position was created |
|feeGrowthInside0LastX128 | BigInt! | | Tracking the amount of token0 fee accumulated by the position |
|feeGrowthInside1LastX128 | BigInt! | | Tracking the amount of token1 fee accumulated by the position |
