---
description: >-
  V1.0.1 describes our new improvement to the liquidity structure used for
  coverage tokens.
---

# Overview

### Introducing Unified Coverage Liquidity with Flash Swaps

Cover Protocol is implementing a new user experience for all participants of the Cover ecosystem that streamlines the product immensely. Instead of using separate balancer pools for CLAIM \(80/20 CLAIM/DAI\) and NOCLAIM \(98/2 NOCLAIM/DAI\), we are now merging them into 1 50/50 \(NOCLAIM/DAI\) pool. 

Doing this greatly benefits our three groups of users:

* Coverage Seekers \(holding CLAIM\): cheaper CLAIM, less slippage, more liquidity
* Coverage Providers \(holding NOCLAIM\): less slippage, more liquidity, market making becomes more attractive
* Market Makers \(providing liquidity and holding CLAIM\): higher trading volume, reliable trading fee earnings, less impermanent loss.

### How Flash Swaps Work

In order to maintain a smooth user experience for the new 50/50 NOCLAIM/DAI pools, we leverage flash loans for any trading participation on our platform.

The process for buying CLAIM is as follows:

1. A user wishes to buy CLAIM, and executes our zap.
2. The zap then flash loans DAI from dydx.
3. Deposits the loaned DAI to mint CLAIM/NOCLAIM.
4. Sells the NOCLAIM on market for DAI.
5. Sends the CLAIM to the user.
6. Charges the user remaining costs like the remainder and fees.
7. Uses the cost for the user to payback the flash loan.

The process for selling CLAIM is as follows:

1. A user wishes to sell their CLAIM on market and uses our zap.
2. The zap flash loans DAI from dydx.
3. Market buys NOCLAIM with the DAI.
4. Takes the users CLAIM.
5. Redeems the CLAIM/NOCLAIM for DAI.
6. Uses most of the DAI from redemption to pay back the flash loan.
7. Sends what is remaining after trading fees and protocol fees back to the user.

 The process for buying/selling NOCLAIM is simply using the balancer pool as you normally would.

### Benefits of Flash Swaps

The benefits of using flash swaps are the following:

* All liquidity is now unified and in 50/50 pools, this means less slippage and lower trading fees!
* All trading volume passes through the protocol, generating protocol fees for every trade!
* There is no more arbitrage between CLAIM and NOCLAIM, the coverage market is now more efficient.
*  Providing liquidity is more attractive now since all the trading volume is in one pool, and market makers can keep all their trading fees if there is no incident!



