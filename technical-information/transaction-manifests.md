---
description: >-
  Some protocol functionality isn't available through the front-end, but
  requires the use of the transaction manifest.
---

# 🧾 Transaction manifests

The three interactions currently impossible through the front-end are using flash loans, forced liquidations and forced minting. These are all handled by the Stabilis Proxy Component.

**Flash loan manifest**

Flash loan receipt resource address: `resource_tdx_2_1ng9qmw3dsv3hfu7fem359llx8049af5thn9gehdrefr4xp7ckggxza`

Proxy component address: `component_tdx_2_1cpv6ach7wxjp79g09c0dcc9c8qy7hw9wxsfpmnr56tgd6a0pk0zk9d`

STAB resource address: `resource_tdx_2_1t57r3zezvsx0gud4p2ed3seteqaahnyzg5ahavamqyxqltkmjqpdxf`

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
