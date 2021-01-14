---
description: >-
  Overview of guidelines which should be followed when filing a claim or voting
  on a claim. This should be followed by the community and the CVC.
---

# Claims Guidelines

### Overview

The Claims guide describes which events are covered and not covered by Cover Protocol. It should also be used as a reference document by the Cover Protocol Claims Assessors, COVER token holders and covToken holders when considering any claim.

* These guidelines and exclusions are not hardcoded into the Cover Protocol Smart Contract\(s\).
* All coverage is provided on a discretionary basis, with Cover Protocol Claims Assessors \(token holders and the CVC\), having the final say on which claims are valid and the final payout amount to CLAIM token holders minus protocol fees \(if the claim is successful\).
* There will be a default **3 day grace period** after expiry to make a claim on an incident that occured before the expiry of a specific coverage.
* **When no claim is accepted** there will be a default **10 day** delay for redemption of NOCLAIM tokens.
* **When a claim is accepted** there will be a default **2 day** delay for CLAIM tokens \(and NOCLAIM tokens if partial payout\).
* Up to **3 days of voting for the community** on [snapshot.page](https://snapshot.page/#/cover) and up to **3 days of voting for the CVC -** multisig.

### **Valid Claim Guidelines**

During the **coverage period**, the designated smart contract or **smart contract system**, suffers a hack, bug, exploit or **economic manipulation attack;**

* and there is a **material loss of deposited funds** from the smart contract, or **smart contract system** with funds either moved to another address which the original owner or owners do not control or the funds are made permanently irrecoverable;
* and the coverage purchaser submits a claim within 3 days of the incident.

### Partial Payouts

If a claim is accepted with a 100% payout ratio, then the NOCLAIM token will be worth $0 while the CLAIM will be redeemable for 1 collateral. 

However, our protocol also allows for partial payouts. Partial payouts are utilized when a protocol is exploited for less than their total TVL and the loss is proportionally distributed amongst depositers. In that case, the payout ratio, x, would be less than 100%. CLAIM tokens will be redeemable for x collateral while NOCLAIM will be redeemable for \(1-x\) collateral.

For example: If _**MYPROTOCOL**_ gets exploited for $1 million while the total value locked is $5 million, a payout percentage of 20% would be reasonable. In that case, CLAIM is redeemable for 0.2 collateral and NOCLAIM is redeemable for 0.8 collateral

### Exclusions

**Loss of deposited funds** due to phishing, private key security breaches, malware, exchange hacks or **negligence** on behalf of the user:

* any claims if the smart contract or **smart contract system** was deployed primarily for the purpose of claiming on the coverage and not for real usage;
* for any hacks occurring during the **coverage period** if a hack occurred or a public bug disclosure was made for the designated smart contract address or **smart contract system** before the **coverage period** began;
* Most mainstream Ethereum applications are complex and consist of a number of smart contracts all working together. The intention is for each covToken to cover just one protocol _**\(i.e. if your money is in yearn.finance and the strategy is deployed to curve.fi ; you will not be covered if funds are hacked/stolen/or lost on curve.fi\)**_
* _Loss of rewards or incentives yet to be distributed to a user\(s\) wallet address._

### **Coverage Expiration**

When there has been a successful claim passed on a specific covered protocol relating to the users coverage that was purchased; or the **coverage period** specified at purchase has ended. When a successful claim is passed the claimNonce for the protocol is incremented and new covTokens are created for all relevant expirations for the protocol.

### Definitions

**Coverage period** for a given covToken includes any time before the expiration timestamp parameter of the related Cover smart contract.

**Economic Manipulation Attack** is an attack in which funds are lost due to changes in economic inputs to the smart contract or **smart contract system** where the changes in the inputs were due to manipulation with the intent to exploit the contract or system, not due to regular market forces; i.e flash loan attacks.

**Loss of deposited funds** means the total deposited funds lost caused by the hack not the loss of the individual coverage purchaser.

**Material** means that the amount lost is meaningful relative to the amount of funds deposited in the protocol. Loss amount vs total deposited. Handle on a case by case basis.

**Negligence** refers to the failure to act in a way that a reasonable person would when faced with the same situation.

**Smart Contract System** means a single smart contract or group of directly related smart contracts running on the public Ethereum network excluding any outside inputs to that system such as oracles, miners, the underlying Ethereum network and individuals or groups of individuals interacting with the system. 



