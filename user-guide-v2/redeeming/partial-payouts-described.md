# Partial Payouts Described

If a claim is accepted with a 100% payout ratio, then the NOCLAIM token will be worth $0 while the CLAIM will be redeemable for 1 collateral. 

However, our protocol also allows for partial payouts. Partial payouts are utilized when a protocol is exploited for less than their total TVL and the loss is proportionally distributed amongst depositors. In that case, the payout ratio, x, would be less than 100%. CLAIM tokens will be redeemable for x collateral while NOCLAIM will be redeemable for \(1-x\) collateral.

For example: If _**MYPROTOCOL**_ gets exploited for $1 million while the total value locked is $5 million, a payout percentage of 20% would be reasonable. In that case, CLAIM is redeemable for 0.2 collateral and NOCLAIM is redeemable for 0.8 collateral

