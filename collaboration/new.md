---
description: >-
  For Cover Protocol to support coverage a new project, we need to collect some
  metrics and data regarding their TVL, safety, and other incentives the
  protocol is willing to provide on launch.
---

# Adding a Protocol

### Fill Out Form

#### [Protocol Proposal Form](https://forms.gle/btvrYEVLW4wNbfxJ)

If you are a protocol team member, fill out the [Protocol Proposal Form](https://forms.gle/btvrYEVLW4wNbfxJ).

[https://forms.gle/btvrYEVLW4wNbfxJ9](https://forms.gle/btvrYEVLW4wNbfxJ9)

#### Community Protocol Request Form

If you are a community member, fill out the Protocol Community Request Form.

[https://forms.gle/uZeafWNdLUqWBxUY6](https://forms.gle/uZeafWNdLUqWBxUY6)

### Contact the Cover Team

Once you ****have submitted the form, reach out to the team through contact@coverprotocol.com with preferred contact information.

Once you passed screening, we will proceed to add your protocol.

We charge a fee of **1 ETH** to cover deployment costs. Please send it to our dev multi-sig: **0x15957f0CA310d35b2E73fB5070Ce44A5B0141AB1**.

Once the fee is received, the Cover Team will handle contract deployments. We will mint the first coverage for you protocol, deploy the cover vault, two covTokens, and create Balancer Pools for each covToken.

### Mint Coverage & Add Liquidity to Pools

Go to [_**Cover App**_](https://app.coverprotocol.com/app/mint) and mint CLAIM and NOCLAIM covTokens for your protocol. The first coverage will deploy 3 contracts. The Cover contract \(which holds the collateral\), the CLAIM token contract and the NOCLAIM token contract.  
Make sure you have enough DAI left to add liquidity to the balancer pools.

Once mint, add liquidity to the Balancer Pools for covTokens.

### **Add "Protected by Cover Protocol" Stamp** 

Add the  ****[**"Protected by Cover Protocol"** stamp](https://docs.coverprotocol.com/website-links/logos) on your site and link it to [the app ](https://app.coverprotocol.com/app/marketplace)where users can buy coverage on your protocol.

### Appendix

#### Balancer Pools Specs

This step will deploy the Balancer pools for the two tokens. Please use the below rules to create the pools. Contact the Cover team if you want to check the math.

**CLAIM / Dai pool**

* Use 10 CLAIM tokens ONLY to create the pool
* 80/20 CLAIM token / Dai \(**not yDai** here\)
* Recommend 3% swap fee
* Calculate the initial price based on the coverage expiry. As a basis:
  * 6 month expiry costing 25% annually, would cost ~$0.04.
  * 6 month expiry costing 50% annually, would cost ~$0.08.
  * 3 month expiry costing 25% annually, would cost ~$0.08.
  * 3 month expiry costing 50% annually, would cost ~$0.16.
  * 1 month expiry costing 25% annually, would cost ~$0.02.
  * 1 month expiry costing 50% annually, would cost ~$0.04.
* Use the above to calculate the ratio of CLAIM to DAI to create the pool with.

**NOCLAIM / Dai pool**

* Use 10 NOCLAIM tokens ONLY to create the pool
* 98/2 NOCLAIM token / Dai \(**not yDai** here\)
* Recommend 1% swap fee
* Calculate the initial price based on the above CLAIM token price. Ultimately, **1 CLAIM + 1 NOCLAIM  == 1 Collateral**

### \*\*\*\*

\*\*\*\*



