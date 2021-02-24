# Product Paper V2

## Overview

Cover Protocol’s long term vision has and always will be to allow anyone to buy coverage on anything. Cover Protocol V2 \(Cover V2\) takes us one step further towards that vision. 

Cover V2 improves upon multiple aspects of V1 in the following ways:

* Addresses concerns raised from V1, including capital efficiency and granular coverage. 
* Open the doors for projects to provide coverage of their products at point of interaction by their end users and create their own coverage markets.
* Expansion into real world risky asset coverage \(phase 1: natural disaster coverage\).

The fundamental model of Cover remains unchanged. It still offers coverage\(s\) with fungible tokens while letting the market set coverage prices.

With Cover V2 as the foundation, there will be 2 lines of products enabled.

* Peer-to-peer coverage market. Same as V1, anyone can come to market make, provide coverage, and purchase coverages for listed risks on Cover Protocol.
* Cover money market. It provides an option to users where they don’t need to worry about expiries of coverages, and can streamline the purchase of coverages.
  * Public cover money market, where anyone can provide and purchase coverages.
  * Private/Semi-private money market where only whitelisted users can provide and/or purchase coverages from the market. It is catered to projects that want to provide affordable coverages to their users at the point of entry. 

## Terminology

**Risk**: a Risk is an underlying \(the smallest unit\) that is covered on Cover Protocol. For example, the yDai vault of Yearn can be considered a Risk.

**Cover Pool**: a Cover Pool consists of multiple **Risks**. For example, Yearn can have a Cover Pool, where each vault is a **Risk** in the Cover Pool. A Cover Pool may be expandable, meaning that new **Risks** may be added to the Cover Pool \(see later on how Cover Providers are hedged from incoming new Risks without any extra action\).

**Coverage**: a Coverage is a contract that represents the coverage for a Cover Pool with a specified collateral and expiry. For example, Yearn Dai 12\_31\_21 is a coverage for Yearn Cover Pool with Dai as collateral \(also payout currency\) that expires at 2021/12/31.

**cToken**: Cover CLAIM and/or Future fungible token. Each **Risk** has a cToken. It represents the right to claim a % of the payment when there is an accepted exploit on the **Risk**.

* Future cToken is one type of cTokens that represents a right to convert into a CLAIM token when a new **Risk** is added to the Cover Pool in the future.

**ncToken**: Cover NOCLAIM fungible token. Each Cover Pool coverage has a ncToken. It represents the right to claim a payment when there is no exploit on the Cover Pool, or a % of the payout when there is an accepted exploit on one or more of the **Risks** covered in the Cover Pool.

**covTokens**: covTokens are collections of **cTokens** and **ncTokens** created by Cover Protocol.

**Cover Money Market**: a marketplace where streamlined coverages purchasing is made possible.

**Cover Reserve**: the custody contract that holds all the coverages in a Cover Money Market. It manages the rollover of the coverages and claims of the Cover Pool for the Cover Money Market.

## Core V2 Model

Cover Core V2 \(Core V2\) is the foundation of Cover Protocol. Core V2 consists of a collection of Cover Pools. There will be new Cover Pools listed as we go after launch.

Each Cover Pool can issue unlimited types of Coverage that vary by collaterals and expiries.

Each Coverage issues **one ncToken** with a specific collateral and expiry. It also issues **multiple cTokens** , one for each Cover Pool Risk, and one future cToken which serves as a placeholder for a potential new risk \(to be added to the pool in the future\).

                    \# of cTokens = \# of Risks + 1 Future Token

### Ticker Symbols of covTokens

The format for ticker symbols for the covTokens is:

{ Direction, C \| NC }\_{ Risk Name \| Future }\_{ Cover Pool }\_{ Nonce }\_{ Collateral }\_{ Expiry }

Example of covTokens for a Yearn Cover Pool with two risks \(3Crv and yCrv\).

In this example, 4 covTokens will be created. One ncToken, one future cToken, and 2 cTokens \(one for each Risk\).

\*  C\_FUT0\_Yearn\_0\_DAI\_12\_31\_20

\*  C\_3Crv\_Yearn\_0\_DAI\_12\_31\_20

\*  C\_yCRV\_Yearn\_0\_DAI\_12\_31\_20

\*  NC\_Yearn\_0\_DAI\_12\_31\_20

### Market Maker

As a market maker, you will hold all the covTokens and provide liquidity on the market.

Using the above example, you will hold all the above 4 types of tokens.

### Coverage Provider

As a coverage provider, you will hold ncToken and future cToken, sell one or more cTokens for Risks in the Cover Pool.

Using the above example, you will hold both 

    NC\_Yearn\_0\_DAI\_12\_31\_20 and C\_FUT0\_Yearn\_0\_DAI\_12\_31\_20

You can choose to sell one or both of the other cTokens \( C\_3Crv\_Yearn\_0\_DAI\_12\_31\_20 and C\_yCRV\_Yearn\_0\_DAI\_12\_31\_20\).

Note that holding the future cToken is the only way to hedge against potential new Risks added to the Cover Pool \(if expendable\) without having to purchase the CLAIM token if you do not wish to expose it to the Risk.

### Coverage Seeker

As a coverage seeker, you will hold one or more cTokens for Risks in a Cover Pool.

Use the above example, you will hold one or both 

C\_3Crv\_Yearn\_0\_DAI\_12\_31\_20 and C\_yCRV\_Yearn\_0\_DAI\_12\_31\_20

### Cover Order Books

Orderbooks provide an attractive option to Coverage Providers enabling them to place limit orders at a price they believe will compensate them properly for the risk of a claim.  Cover v2 will have a dedicated section with a custom UI for orderbooks powered by 0x. Placing an order will be gasless, but cancelling and executing an order will require the trader to pay gas.

## Cover Money Market

### Overview

It is the stated goal of Yearn to have opt-out coverage on all of their vaults.  With the current lack of capacity both on Nexus Mutual and Cover, it is dubious that the market could provide such ambitious coverage in its current state. Cover Money Market will make this possible for Yearn and others.

The Cover Money Market is completely decoupled from Cover Core V2. It is a marketplace built on top of V2. Each Cover Pool can have one or more money markets based on the collateral and expiry. Its goal is to allow streamlining purchase of coverage without worrying about expiry.

The Cover Money Market makes it possible for any project to create its own coverage market with its own rules. The collateral, expiry, premium rate are settable by the creator of the market. A money market can also be: 

* Public where anyone can provide coverages and purchase coverages
* Private/Semi-Private where only whitelisted users can provide and/or purchase coverages from the market.

\(The  collateral and expiry must be whitelisted on Cover Protocol V2 first.\)

In the coverage money market, there will be no Market Makers, only Coverage Providers deposit to **Cover Reserve** and Coverage Seekers purchase from **The Money Market**.

### Cover Reserve

**Cover Reserve** is the custody contract that stores all the coverages in a Cover Money Market. It manages the rollover of the coverages and claims of the Cover Pool. It abstracts the details of the coverages out from the end users. It is considered a user of Cover Core V2.

#### Coverage Providers

Coverage providers in a Cover Money Market deposit collateral into the Cover Reserve. 

They can then collect premiums as those coverages are purchased by coverage seekers.

### The Money Market

The cover money market provides options for coverage seekers to stream coverages without worrying about expiries or paying upfront for the whole time period.

The purchase rate in the market can follow a bonding curve or simply just a flat fee. The creator of the money market will be able to decide.

Note: contracts can be created to interact with the money market on behalf of end users. Then **middle layer contracts** will provide flexibility to their creators and providers on **its policies and rules.**

#### Coverage Seekers

Coverage Seekers will deposit a certain amount of payout to streamline purchase of a coverage on a Risk. Contracts \(vaults/pools etc.\) can be coverage seekers who may automatically transfer a certain % of all user deposits to purchase coverages. 

### Claim Management

Claims are managed through Cover Core V2. The money market will simply follow the process. When a claim is accepted, Cover Core V2 will payout to the reserve, who then payout to its recorded users. If the users are contracts, then payout will be allocated to the contracts, who can then distribute the payout to its end users following its own rules. The guidelines can be found [_here_](https://docs.coverprotocol.com/product/claims-guidelines-v2)_._

### Example - Public Cover Money Market

Consider Yearn as a Cover Pool with yDai-vault and yCrv-vault as Risks \(using only 2 Risks for simplicity\). 

Yearn creates a public money market where: 

* Dai is used as the collateral
* Dai is used as coverage premium payment currency
* Anyone can deposit to become a coverage provider
* Anyone can purchase coverages from the market

1. Yearn \(or requests Cover to\) deploys the above Cover Money Market on top of the Cover Core V2.
2. Anyone can deposit any amount of Dai as collaterals to the Cover Reserve of the market. Let’s assume there are $45mm Dai deposited for this market. The reserve will be able to mint $45mm worth of coverage. The reserve will hold the following tokens, $45mm each.

   \*  C\_FUT0\_Yearn\_0\_DAI\_12\_31\_20

   \*  C\_3Crv\_Yearn\_0\_DAI\_12\_31\_20

   \*  C\_yCRV\_Yearn\_0\_DAI\_12\_31\_20

   \*  NC\_Yearn\_0\_DAI\_12\_31\_20

3. $45mm Yearn coverage will be available for sale on the Yearn Cover Money Market. As long as coverages are not 100% purchased, depositors can withdraw deposits and accumulated premiums at any time. 
4. Yearn vaults \(like anyone\) can buy coverages from the money market directly by using a % of yields as premium payments. For example, yDai-vault and yCrv-vault will automatically transfer a % of yields to the Money Market for coverage. The vaults can be covered up to $45mm. If the vault has higher TVL \(than $45mm\), more Dai are required to be deposited into the reserve.
5. When expiry comes, the reserve will automatically convert the current coverage to the next expiry. No actions required from both depositors or coverage buyers.
6. When an exploit happens \(Cover Core will record any valid exploits\), the reserve will freeze the current deposits based on the payout ratio. It will rollover the remaining collateral \(if not a 100% payout, or not 100% coverages sold\) to the next Cover Pool nonce and expiry where users can stream coverages again. 

### Example - Semi-Private Cover Money Market

Consider Yearn as a Cover Pool with yDai-vault and yCrv-vault as Risks \(using only 2 Risks for simplicity\). 

Yearn creates a semi-private money market where: 

* Dai is used as the collateral
* Dai is used as coverage premium payment currency
* Anyone can deposit to become a coverage provider
* Yearn vaults \(or a middle layer buying contract\) are the only whitelisted coverage buyers

1. Yearn \(or requests Cover to\) deploys the above Cover Money Market on top of the Cover Core V2.
2. Anyone can deposit any amount of Dai as collaterals to the Cover Reserve of the market. Let’s assume there are $45mm Dai deposited for this market. The reserve will be able to mint $45mm worth of coverage. The reserve will hold the following tokens, $45mm each.

   \*  C\_FUT0\_Yearn\_0\_DAI\_12\_31\_20

   \*  C\_3Crv\_Yearn\_0\_DAI\_12\_31\_20

   \*  C\_yCRV\_Yearn\_0\_DAI\_12\_31\_20

   \*  NC\_Yearn\_0\_DAI\_12\_31\_20

3. $45mm Yearn coverage will be available for sale on the Yearn Cover Money Market. As long as coverages are not 100% purchased, depositors can withdraw deposits and accumulated premiums at any time. 
4. Yearn vaults can buy coverages from the money market directly by using a % of yields as premium payments. For example, yDai-vault and yCrv-vault will automatically transfer a % of yields to the Money Market for coverage. The vaults can be covered up to $45mm. If the vault has higher TVL \(than $45mm\), more Dai are required to be deposited into the reserve.
5. When expiry comes, the reserve will automatically convert the current coverage to the next expiry. No actions required from both depositors or coverage buyers.
6. When an exploit happens \(Cover Core will record any valid exploits\), the reserve will freeze the current deposits based on the payout ratio. It will rollover the remaining collateral \(if not a 100% payout, or not 100% coverages sold\) to the next Cover Pool nonce and expiry where users can stream coverages again. 

### Example - Private Cover Money Market

Consider Yearn as a Cover Pool with yDai-vault and yCrv-vault as Risks \(using only 2 Risks for simplicity\). 

Yearn creates a private money market where: 

* YFI is used as the collateral
* YFI is used as coverage premium payment currency
* Yearn treasury/trust and Yearn vaults are the only whitelisted coverage providers
* Yearn vaults \(or a middle layer buying contract\) are the only whitelisted coverage buyers

1. Yearn \(or requests Cover to\) deploys the above Cover Money Market on top of the Cover Core V2.
2. Yearn treasury deposits 500 YFI \(from treasury\) into the Yearn Cover Reserve \(the reserve\) as collateral. Some of the Yearn vaults choose the money market as one of the yield strategies and deposit 500 YFI into the reserve. The reserve will be able to mint $80mm  \(YFI @ $40k\) worth of coverage \($40mm each for the two Risks\). The reserve will hold the following tokens, $40mm each

   \*  C\_FUT0\_Yearn\_0\_DAI\_12\_31\_20

   \*  C\_3Crv\_Yearn\_0\_DAI\_12\_31\_20

   \*  C\_yCRV\_Yearn\_0\_DAI\_12\_31\_20

   \*  NC\_Yearn\_0\_DAI\_12\_31\_20

3. $45mm Yearn coverage will be available for sale on the Yearn Cover Money Market. As long as coverages are not 100% purchased, the Yearn treasury can withdraw deposits and accumulated premiums at any time. 
4. Yearn creates a buying contract that buys coverages from the money market for its vaults. For example, yDai-vault and yCrv-vault will automatically transfer a % of yields to the buying contract. The buying contract then converts them into YFI, and uses it as premium in the Money Market for coverages. The vaults can be covered up to $45mm. If the vault has higher TVL \(than $45mm\), more YFI are required to be deposited into the reserve. 
5. When expiry comes, the reserve will automatically convert the current coverage to the next expiry. No actions required from both depositors or coverage buyers.
6. When an exploit happens \(Cover Core will record any valid exploits\), the reserve will freeze the current deposits based on the payout ratio. It will rollover the remaining collateral \(if not a 100% payout, or not 100% coverages sold\) to the next Cover Pool nonce and expiry where users can stream coverages again. 

