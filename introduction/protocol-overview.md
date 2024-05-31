---
description: >-
  Stabilis is a protocol which aims to provide the Radix ecosystem with stable
  assets. At this point in time, only the STAB (STAble Basis) token will be
  available (on Stokenet).
---

# 👋 Protocol overview

**STAB**

The ultimate goal of the Stabilis protocol is creation of STAB. This is done in a similar fashion as stablecoins such as DAI or LUSD: it is borrowed.

To borrow STAB, the user provides the protocol with a collateral. The collateral value must be higher than 150% of the borrowed STAB's value (reffered to as the MCR from here on) and ensures the borrowed STAB is always backed by assets of at least their value. In return for this collateral, the protocol provides the borrower with the freshly-minted STAB tokens and a Loan Receipt. By showing the protocol their previously acquired receipt, one can prove to be the owner of a loan and exchange their STAB for their collateral again.

There are some **dangers** to borrowing STAB though. When one's collateral value falls below the MCR, being liquidated is a possibility. This means a third party is able to pay off the STAB debt in return for part of the collateral. The collateral loss will be higher than 100% of the debt, so being liquidated is no bueno! Penalties aren't set in stone yet, but on Stokenet 110% of the debt value goes to the liquidator and 10% of the debt goes to the protocol.

Of course, to prevent liquidation, it is possible to add some collateral to a loan. Similarly, one can also remove collateral from a loan, as long as the value of their collateral stays above the MCR (or even pay off the entirety of the debt to regain possession of the collateral).

**Interest rate**

The **unique** feature of STAB however, is that it is not hard-pegged to a single USD valuation; STAB tokens are subject to an interest rate. The interest rates can vary from -33.33% to +50% per year and are set by STAB supply and demand. Negative interest is attractive for STAB borrowers, as their debt decreases over time, whereas positive interest is attractive for STAB holders, as their assets increase in value.

As previously mentioned, this interest rate is set by supply and demand. To do this, the protocol keeps track of an internal price (or peg), which it believes STAB should trade at on the open market. If the internal price is higher than the open market price, STAB is in low demand and interest rates increase. Conversely, if the open market price is higher than the internal price, STAB is in high demand and interest rates decrease! To keep track of the STAB price, an AMM is built into the protocol, where the user can swap their XRD for STAB.
