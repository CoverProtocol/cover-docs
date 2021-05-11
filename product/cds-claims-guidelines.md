# CDS Claims Guidelines V2

{% hint style="info" %}
**All CDS claims will be forced filed and be sent directly to the CVC.**
{% endhint %}

The CDS Claims guide describes which events are covered and not covered by Cover Protocol. It should also be used as a reference document by the Claims Validity Committee \(CVC\) when considering any claim. These guidelines are not hardcoded into the Cover Protocol Smart Contract\(s\).  
  
All coverage is provided on a discretionary basis, with Claims Validity Committee \(CVC\), having the final say on which claims are valid and the final payout amount to CLAIM token holders minus protocol fees \(if the claim is successful\).

* There will be a default 3 day grace period after expiry to make a claim on an incident that occurred before the expiry of specific coverage. 
* When no claim is accepted there will be a default 10-day delay for the redemption of NOCLAIM tokens. 
* When a claim is accepted there will be a default 3-day delay for CLAIM tokens \(and NOCLAIM tokens if partial payout\).

**Valid Claim Guidelines**   
During the coverage period, lenders on protocols will now have the option of hedging the default risk from the borrower side. Claims are handled per risk. If there are multiple defaults, there will be a partial payout based on the total loss of lenders of that pair.

  
A claim is valid when:

* the collectible payments are lower than the expected collectible amount due to defaults. 1 rcToken should equal $1 at collection time. 

**Example:** You lent on wBTC. You received 100 rcTokens. Those 100 rcTokens only collect $95 worth of repayment DAI and defaulted collateral at the due date. The Credit Default Swap would cover you for the $5 difference, if there is not a partial payout. 

