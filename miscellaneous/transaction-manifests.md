---
description: >-
  Some protocol functionality isn't available through the front-end, but
  requires the use of the transaction manifest.
---

# 🧾 Transaction manifests

The three interactions currently impossible through the front-end are using flash loans, forced liquidations and forced minting. These are all handled by the Stabilis Proxy Component.

**Flash loan manifest**

Current flash loan receipt address: address here

```
CALL_METHOD
  Address("<proxy_component_address>")
  "flash_borrow"
  Decimal("1000")
;

////////////////////////////////////////////////////////////////////////////
/////////////////////// USE YOUR BORROWED STAB HERE ////////////////////////
////////////////////////////////////////////////////////////////////////////

////////////////////////////////////////////////////////////////////////////
//// PUT THE STAB YOU'RE USING TO PAY BACK THE LOAN ON THE WORK TOP ////////
////////////////////////////////////////////////////////////////////////////

TAKE_ALL_FROM_WORKTOP
  Address("<stab_address>")
  Bucket("stab_bucket")
;

TAKE_ALL_FROM_WORKTOP
  Address("<loan_receipt_address>")
  Bucket("receipt_bucket")
;

CALL_METHOD
  Address("<proxy_component_address>")
  "flash_pay_back"
  Bucket("receipt_bucket")
  Bucket("stab_bucket")
;
```



**Forced minting / borrowing**

Will become available after the open beta
