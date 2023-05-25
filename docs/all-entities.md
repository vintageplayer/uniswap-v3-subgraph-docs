---
title: Entity Types
sidebar_position: 2
---

Following Entity Types are defined in the graph [schema file](https://github.com/Uniswap/v3-subgraph/blob/main/schema.graphql):


||Entity|Description|
|-|-|-|
|1.|[Factory](./schemas/factory.md) | Captures metrics for all the pools deployed by a specific factory contract. |
|2.|[Bundle](./schemas/bundle.md) | Stores the current Eth price in USD. |
|3.|[Token](./schemas/token.md) | Stores the metadata and token level metrics for a token present in any of the pools. |
|4.|[Pool](./schemas/pool.md) | Stores a pool's metadata, current & lifetime metrics and links to events and hourly/daily metrics and references to it's tick entities. |
|5.|[Tick](./schemas/tick.md) | Stores the metadata for a tick in a pool, it's lifetime metrics and current liquidity and fee variables. |
|6.|[Position](./schemas/position.md) | Represents a position created through [NonfungiblePositionManager](../contracts/nonfungiblepositionmanager.md). Stores it's metadata, deposited/withdrawn tokens, fee variables and transactions where it participated. |
|7|[PositionSnapshot](./schemas/positionsnapshot.md) | Saves the state of a position after an action taken on the position. |
|8|[Transaction](./schemas/transaction.md) | Stores the list of mint, burn, swap, flash and collects events emitted within a transaction. |
|9|[Mint](./schemas/mint.md) | Stores details of a mint event emitted while adding liquidity to a pool |
|10|[Burn](./schemas/burn.md) | Stores details of a burn event emitted while removing liquidity from a pool |
|11|[Swap](./schemas/swap.md) | Stores details of a swap event emitted while swapping one token for the other in a pool |
|12|[Collect](./schemas/collect.md) | Stores details of a collect event emitted while removing tokens from a position |
|13|[Flash](./schemas/flash.md) | Stores details of a flash event emitted while a flash loan was taken from a pool |
|14|[UniswapDayData](./schemas/uniswapdaydata.md)| Daily stats for all of Uniswap |
|15|[PoolDayData](./schemas/pooldaydata.md)| Daily stats for each pool |
|16|[PoolHourData](./schemas/poolhourdata.md)| Hourly stats for a pool |
|17|[TickHourData](./schemas/tickhourdata.md)| Stats on Liquidity available & Volume of token traded at a tick for a given hour |
|18|[TickDayData](./schemas/tickdaydata.md)| Stats on Liquidity available & Volume of token traded at a tick on a given day. <br/>(Note: this entity gets saved only if there is a change during the day) |
|19|[TokenDayData](./schemas/tokendaydata.md) | Daily stats for a token across all of Uniswap |
|20|[TokenHourData](./schemas/tokenhourdata.md) | Hourly stats for a token across all of Uniswap | 
