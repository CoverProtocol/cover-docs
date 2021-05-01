---
description: >-
  V1.0.1 describes our new improvement to the liquidity structure used for
  coverage tokens.
---

# Version 1.0.1

### Introducing Unified Coverage Liquidity with Flash Swaps

Cover Protocol is implementing a new user experience for all participants of the Cover ecosystem that streamlines the product immensely. Instead of using separate balancer pools for CLAIM \(80/20 CLAIM/DAI\) and NOCLAIM \(98/2 NOCLAIM/DAI\), we are now merging them into 1 50/50 \(NOCLAIM/DAI\) pool. 

**Note:** this change only relates to the balancer pools and will only affect newly launched protocols/expiries after today. The fundamental fungible tokens model of Cover V1 has NOT changed. This is not Cover V2.

### **Benefits of Flash Coverage Swaps**

Using a single 50/50 NOCLAIM/DAI pool is a large improvement over our previous dual pool model, and we would like to detail the main benefits of this new model below:

* **Cheaper coverage and less slippage!** With our new model, farmers buy NOCLAIM to farm for rewards and/or earn trading fees, which effectively decreases the price of CLAIM tokens \( 1 CLAIM = 1 - NOCLAIM token price\). In our previous liquidity model, incentivizing liquidity for the CLAIM/DAI pool was difficult because,
  * Market Makers wanted to keep their CLAIM to hedge
  * Farmers would purchase CLAIM to farm, which would distort the price of coverage. 
* **More trading fees for NOCLAIM pool liquidity providers!** Due to our usage of flash liquidity, for every CLAIM $ amount traded, there is always a greater NOCLAIM $ amount worth of volume. This essentially means any CLAIM trading volume generates 5-20x as much trading volume in the NOCLAIM pool. Combined with minimal impermanent loss, market making becomes much more attractive!
* **More platform revenue!** Through flash loans, for every CLAIM token purchased, $1 of value will pass through the protocol and trigger the 0.1% protocol fee. This means that the protocol will directly benefit from CLAIM trading volume in the form of increased fee revenue.
* **Operation cost savings!** Balancer pools are notoriously expensive to deploy \(almost 1 ETH each\). With the new change, we will only have to deploy a single Balancer pool per coverage

The catch is that because flash coverage swaps are more complex than a balancer trade, they will incur a higher transaction cost. We will be looking into ways to improve this for our users.  


### How Flash Swaps Work

In order to maintain a smooth user experience for the new 50/50 NOCLAIM/DAI pools, we leverage flash loans for any trading participation on our platform.

We have built zaps to interact with the protocol using flash loans. This will make the user experience of purchasing and selling CLAIM, easier.

The process of buying CLAIM is as follows:

1. A user wishes to buy CLAIM, and executes our zap.
2. The zap then flash loans DAI from dydx \(with lowest fee ~2wei\).
3. The loaned DAI is deposited into Cover Protocol to mint CLAIM/NOCLAIM.
4. The newly minted NOCLAIM is then sold on market for DAI.
5. The newly minted CLAIM is sent to the user.
6. The user is charged remaining costs and fees in DAI.
7. This received DAI is then used to pay back the flash loan.

The process of the zap for selling CLAIM is as follows:

1. A user wishes to sell their CLAIM on market and uses our zap.
2. The zap flash loans DAI from dydx \(with lowest fee ~2wei\).
3. The flash loaned DAI is used to market buy NOCLAIM from Balancer.
4. The zap takes the users CLAIM.
5. Now that the zap has both NOCLAIM and CLAIM, it redeems them for DAI.
6. The zap uses most of the DAI from redemption to pay back the flash loan.
7. With the flash loan paid, the remaining DAI after trading fees and protocol fees is sent back to the user.

The process for buying/selling NOCLAIM is simply using the balancer pool as you normally would.  




