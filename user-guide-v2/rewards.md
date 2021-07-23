# Rewards

### **Order Book Rewards Info**

Rewards are distributed to people utilizing the order book system. In order to receive rewards, you can place sell orders in the participating pairs. 

The difference between the price of your order and the market price, as well as the amount of your order, determines the number of rewards you get. 

To get the most rewards you need to place your larger sell orders closest to the market price. We will be doing snapshots of the order books once an hour and distribute rewards once a week as well.

As you move further away from the market price the rewards diminish.



**Rewards Formula:** 

![](../.gitbook/assets/codecogseqn.png)

The multiplier is used to multiply it by the order size and that will then become the weight for your position.  


{% hint style="info" %}
CoverRules / 0x notices:

* **Orders smaller than 250 tokens are not eligible to receive rewards**
* Users placing multiple orders that are larger than their token balance will only be rewarded for either their token balance or the total value of an order placed for a given token, whichever is smaller
* Users placing orders directly through the API and avoiding Coverrules' order matching do not gain any advantage over regular orders, and increase the risk of their orders being filled
{% endhint %}

## Current Mining Program <a id="3f9c"></a>

The “Blue Pool” is the first to participate in the **Liquidity Mining** program. 

You will be able to earn rewards by providing liquidity on the order books for the trading of the following pairs on CoverRules.

* C\_CURVE/DAI — _Rewards: 5 COVER per week_
* C\_YEARN/DAI — _Rewards: 5 COVER per week_
* C\_BANCOR/DAI — _Rewards: 5 COVER per week_
* C\_AAVE/DAI — _Rewards: 5 COVER per week_
* C\_COMPOUND/DAI — _Rewards: 5 COVER per week_
* C\_BALANCER/DAI — _Rewards: 5 COVER per week_
* C\_UNISWAP/DAI — _Rewards: 5 COVER per week_

{% hint style="warning" %}
**Only the ASK side \(selling of coverage/CLAIM tokens\) will be rewarded.**
{% endhint %}

