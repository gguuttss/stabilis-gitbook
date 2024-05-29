---
description: >-
  On the Liquidations page, the user can mark loans for liquidation and
  eventually liquidate them.
---

# 🤹 Liquidations

For a loan to be liquidated, it first needs to be marked. Then, after a delay of 5 minutes, it can be liquidated by the marker. If the marker decides not to liquidate it, 10 minutes after the initial marking, anyone can liquidate it.\
\
See the [System parameters](../miscellaneous/system-parameters.md) for liquidation penalties.

**Marked liquidations**\
To start the process of a marked liquidation, pressing the "mark" button checks whether the STAB loan with the lowest collateralization ratio is eligible for liquidation. If it is, the user is rewarded with a **Marker Receipt**, which they can use to liquidate the loan with.\
\
By selecting a Marker Receipt, the state of the corresponding marked loan can be checked. If the the user so desires and it is possible, they can then liquidate the corresponding loan by clicking "Liquidate". If the selected marker has expired, the user can burn it, as it has no further use.

**Unmarked liquidations**\
Sometimes the marker of a loan does not have sufficient funds to liquidate a loan. So, after a 10 minute delay, marked loans are liquidatable by everyone. Pressing the button under **"Liquidate next"**, liquidates the loan that has been marked for the longest amount of time.\
\
If there are multiple loans available for public liquidation, but the first one's debt is relatively large, users sometimes do not have sufficient funds to liquidate it. Might this occur, the user can use the **"Liquidate, but skip"** section. The user inputs how many loans they want to skip when liquidating. In the case of one relatively large loan blocking the queue, one would fill in "1" and click the "Liquidate" button. When skipping more liquidations then are available, the last available liquidation is selected.
