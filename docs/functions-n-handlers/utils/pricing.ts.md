---
sidebar_position: 4
title: pricing.ts
---

path: [`/src/utils/pricing.ts`](https://github.com/Uniswap/v3-subgraph/blob/main/src/utils/pricing.ts)

### WETH_ADDRESS
```
- type: string
- value: '0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2'
```
Address of wrapped-ETH (WETH) contract on ethereum mainnet.

#### Referenced at:
1. [WHITELIST_TOKENS](#whitelist_tokens)
2. [findEthPerToken()](#findethpertoken)

### USDC_WETH_03_POOL
```
- type: string
- value: '0x8ad599c3a0ff1de082011efddc58f1908eb6e6d8'
```
Address of Uniswap V3 pool contract between `USDC` and `WETH` `ERC-20` tokens on ethereum mainnet.

#### Referenced at:
1. [getEthPriceInUSD](#getethpriceinusd)

### WHITELIST_TOKENS
A list of tokens which have considerable usage and are likely to have pool pairing with other tokens. These can be used for calculating liquidity in USD by using the tokens price in USD.

The following token addresses are present in the list:

|Symbol|Address|
|-|-|
|WETH|`USDC_WETH_03_POOL`*|
|DAI|0x6b175474e89094c44da98b954eedeac495271d0f|
|USDC|0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48|
|USDT|0xdac17f958d2ee523a2206206994597c13d831ec7|
|TUSD|0x0000000000085d4780b73119b644ae5ecd22b376|
|WBTC|0x2260fac5e5542a773aa44fbcfedf7c193bc2c599|
|cDAI|0x5d3a536e4d6dbd6114cc1ead35777bab948e3643|
|cUSDC|0x39aa39c021dfbae8fac545936693ac917d5e7563|
|EBASE|0x86fadb80d8d2cff3c3680819e4da99c10232ba0f|
|sUSD|0x57ab1ec28d129707052df4df418d58a2d46d5f51|
|MKR|0x9f8f72aa9304c8b593d555f12ef6589cc3a579a2|
|COMP|0xc00e94cb662c3520282e6f5717214004a7f26888|
|LINK|0x514910771af9ca656af840dff83e8264ecf986ca|
|SNX|0xc011a73ee8576fb46f5e1c5751ca3b9fe0af2a6f|
|YFI|0x0bc529c00c6401aef6d220be8c6ea1667f6ad93e|
|1INCH|0x111111111117dc0aa78b770fa6a738034120c302|
|yCurv|0xdf5e0e81dff6faf3a7e52ba697820c5e32d806a8|
|FEI|0x956f47f50a910163d8bf957cf5846d573e7f87ca|
|MATIC|0x7d1afa7b718fb893db30a3abc0cfc608aacfebb0|
|AAVE|0x7fc66500c84a76ad7e9c93437bfc5ac33e2ddae9|
|sETH2|0xfe2e637202056d30016725477c5da089ab0a043a|

\* -> The value is imported from a variable and listed directly in the list declaration.

#### Dependencies:
1. [WETH_ADDRESS](#weth_address)

#### Referenced at:
1. [getTrackedAmountUSD](#gettrackedamountusd)
2. [handlePoolCreated()](../mappings/factory.ts#handlepoolcreated)

### STABLE_COINS
A list of ERC20 token contract addresses which have stable coin prices, i.e., 1 token expected to be valued at 1 USD.

||Address|
|-|-|
|DAI|0x6b175474e89094c44da98b954eedeac495271d0f|
|USDC|0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48|
|USDT|0xdac17f958d2ee523a2206206994597c13d831ec7|
|TUSD|0x0000000000085d4780b73119b644ae5ecd22b376|
|FEI|0x956f47f50a910163d8bf957cf5846d573e7f87ca|
|PRINTS|0x4dd28568d05f09b02220b09c2cb307bfd837cb95|

#### Referenced at:
1. [findEthPertoken()](#findethpertoken)

### MINIMUM_ETH_LOCKED
```
 - type: BigDecimal
 - value: 60
```
While calculating token price in USD, the value of other token locked in the pool in terms of eth has to be greated than `MINIMUM_ETH_LOCKED`.

#### Referenced at:
1. [findEthPertoken()](#findethpertoken)

### sqrtPriceX96ToTokenPrices()
```
Params:
 - sqrtPriceX96 (BigInt): The square root of the price of token1 in terms of token0 in Q64.96 format. Formula: sqrt(token0.price/token1.price)*(2^96)
 - token0 (Token): The first token in the pool pair to calculate the relative price for
 - token1 (Token): The second token in the pool pair to calculate the relative price for

ReturnType: BigDecimal[]
```
Find the price of `token0` and `token1` in the pool relative to each other and returns the two prices.

#### Formula:
```
    num = (sqrtPriceX96^2) # Squaring the root to get the price
    denom = 2^192 # To divide price by 96^2 to convert the Q64.96 number to BigDecimal
    price1 = ((num/denom) * (10^token0.decimals))/ (10^token1.decimals) # Calculating price1
    price0 = 1/price1
```

#### Dependencies:
1. [exponentToBigDecimal()](./index.ts#exponenttobigdecimal)
2. [safeDiv()](./index.ts#safediv)

#### Invoked at:
1. [handleSwap()](../mappings/core.ts#handleswap)


### getEthPriceInUSD()
```
Params: none

ReturnType: BigDecimal
```
Returns the Price of ETH in terms of USD, based on the stable coin pools.
Currently, the `token0Price` for the `pool` represented by `USDC_WETH_03_POOL`. When `pool` entity is not found, returns `ZERO_BD`.

#### Entites:
1. [Pool](../../schemas/pool.md) - Read Entity

#### Dependencies:
1. [USDC_WETH_03_POOL](#usdc_weth_03_pool)
2. [ZERO_BD](./constants.ts#zero_bd)

#### Invoked at:
1. [handleInitialize()](../mappings/core.ts#handleinitialize)
2. [handleSwap()](../mappings/core.ts#handleSwap)

### findEthPerToken()
```
Params:
 - token (Token): Token entity to find the price in terms of ETH

ReturnType: BigDecimal
```
If token is weth, returns 1. If token in `STABLE_COINS`, returns `1/bundle.ethPriceUSD`.

Else, iterates over all the whitelisted pools for the token using `token.whitelistPools`. Finds the pool with largest liquidity value in terms of ETH, as long as the value is atleast `MINIMUM_ETH_LOCKED`. Uses the eth value of the paired token and relative token price between the token pair to find the `token`'s' value in terms of eth.
If there's no whitelisted pool with `MINIMUM_ETH_LOCKED`, returns `ZERO_BD`.

#### Entites:
1. [Bundle](../../schemas/bundle.md) - Read Entity
2. [Pool](../../schemas/pool.md) - Read Entity
3. [Token](../../schemas/token.md) - Read Entity

#### Dependencies:
1. [WETH_ADDRESS](#weth_address)
2. [ONE_BD](./constants.ts#one_bd)
3. [ZERO_BD](./constants.ts#zero_bd)
4. [STABLE_COINS](#stable_coins)
5. [MINIMUM_ETH_LOCKED](#minimum_eth_locked)

#### Invoked at:
1. [handleInitialize()](../mappings/core.ts#handleinitialize)
2. [handleSwap()](../mappings/core.ts#handleSwap)

### getTrackedAmountUSD()
```
Params:
 - tokenAmount0 (BigDecimal):
 - token0 (Token0):
 - tokenAmount1 (BigDecimal):
 - token1 (Token):

ReturnType: BigDecimal
```
Returns the USD value equivalent to `tokenAmoun0` and `tokenAmount1` together. Calculates the USD price using `token.derviedEth*bundle.ethPriceUSD` as the multiplier if the token is present in `WHITELIST_TOKENS`. If both the tokens are present, it adds their individual USD prices. If only one is present, it uses 2X the value of that token. If neither are in the `WHITELIST_TOKENS` list, returns `ZERO_BD`.
#### Entites:
1. [Bundle](../../schemas/bundle.md) - Read Entity

#### Dependencies:
1. [WHITELIST_TOKENS](#whitelist_tokens)
2. [ZERO_BD](./constants.ts#zero_bd)

#### Invoked at:
1. [handleSwap()](../mappings/core.ts#handleSwap)

