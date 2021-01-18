# Summary and Benefits

Cover Collaboration Outline

Cover Protocol is a P2P coverage marketplace for the smart contract industry, allowing for fully peer-to-peer provided coverage, with the costs of protection priced entirely by the market. Since our model is entirely decentralized, anyone is able to provide or purchase coverage by staking collateral with no KYC required. This allows for interesting benefits to protocols themselves.

Cover Protocol introduces the concept of protocols providing coverage directly to their users, either by providing liquidity for coverage, or by selling coverage on the market to make it cheaper for their users to stay safe. We believe this opens a lot of potential for protocols to cooperate with Cover in order to keep DeFi safe and its users protected.

## Outline of the Cover Model

To summarize, users stake collateral \(DAI in this example\) on our platform and mint 2 tokens in a 1:1 ratio to the amount of collateral staked. The tokens minted are referred to as CLAIM and NOCLAIM coverage tokens, and they are specific to the protocol being covered, the expiration date of the coverage they represent, and the collateral used to mint them both. CLAIM is redeemable for the underlying collateral 1:1 in the event of a hack, while NOCLAIM is also redeemable 1:1 in the event of no incident occurring.  


These 2 tokens should always add up to 1 unit of collateral \(DAI here, so $1\), with NOCLAIM being priced around $0.90-1.00 assuming the protocol has low risk, and CLAIM trading at what the market considers the price of coverage to be, usually between $0.00 and $0.10.

Once minted, the staker can do whatever they wish with these tokens. If someone wishes to provide coverage to others for a potential profit, they may sell the CLAIM tokens \(which are priced at the “cost” of coverage\) to instantly earn a return while giving up their protection in the event of a hack. They can also provide liquidity to both of these coverage tokens for the duration of the coverage until expiration, to earn revenue from the trading fees \(currently 1%-3%\). As a provider, they should always keep their NOCLAIM so they can redeem their collateral after the coverage has expired.

In the event of a valid incident, since CLAIM will be redeemable 1:1, the market will react to this and immediately trade CLAIM at $1, while NOCLAIM will not be redeemable for anything, and approach $0. To prevent heavy impermanent loss, we have made our coverage token liquidity pools 80/20 CLAIM/DAI and 98/2 NOCLAIM/DAI so providers and market makers can be safe regardless of the outcome.

If you would like to read more details on how we work, please read our [product paper](https://coverprotocol.com/Cover%20Product%20Paper.pdf).

## Potentials as a Protocol

In the Cover model, anyone is able to provide and seek coverage. A protocol’s team may be interested in a “coverage fund” of sorts that is used in the case of an incident to pay out funds back to users. This is easily possible through Cover with a lot of upsides available from the provider side. A provider can immediately profit from providing coverage by selling the minted CLAIM tokens minted from the coverage fund, or using any of their coverage tokens to provide liquidity on the market so high-volume users can reliably purchase coverage, while the provider earns the trading fees.

Below are the benefits of providing coverage from the perspective of a protocol:

* Show confidence in your project's security.
* Boost publicity & reputation of your project.
* Earn premium\(s\) by selling CLAIM tokens.
* Cheap coverage opportunities for your community to stay protected.
* Earn balancer fees by providing liquidity in the pool\(s\).
* Redeem collateral back as long as there is no claim.
* Incentivize your own token as well!

We believe Cover can boost the confidence of DeFi in both the protocols and its users. With protocols displaying confidence in themselves by providing coverage, resulting in users being able to protect themselves at a cost-effective rate, this creates a great connection between the protocols and their users. Protocols have strong incentives aligned with ensuring their platform is secure, while users are able to stay protected and safely use the protocol as needed.

