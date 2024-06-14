---
description: 'The Borrow page consists of a single feature: opening loans of STAB.'
---

# 💰 Borrow

<mark style="color:red;">**Be careful, when borrowing STAB, you risk being liquidated when your collateral value falls below the MCR (150% of your debt's value)!**</mark> This comes with [<mark style="color:blue;">**liquidation penalties**</mark>](../technical-information/system-parameters.md)<mark style="color:blue;">**.**</mark>

**Borrow STAB**\
Borrowing STAB is done by providing collateral. The value of collateral provided needs to be > 150% (MCR) of the borrowed STAB.\
\
The accepted collaterals are currently:

1. XRD
2. LSUs
   1. Hermes Protocol LSU
   2. Radst0kes LSU

**LSUs are only selectable in the dApp when you own them!**

**Get some here:** [**https://stokenet-dashboard.radixdlt.com/network-staking**](https://stokenet-dashboard.radixdlt.com/network-staking)

Mainnet Stabilis will try to accommadate as many LSUs as possible, but for testing this is unnecessary and too convoluted, so only these two are accepted.

Choosing the amount of collateral to use, desired collateralization ratio and clicking "Borrow", starts a loan.

**Protocol overview**\
The state of the protocol is displayed on the right side of the page, to give the user as much insight as possible.
