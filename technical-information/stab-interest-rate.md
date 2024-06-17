# 💹 STAB interest rate

STAB interest rate calculation is done through a PID-controller in the Scrypto blueprint. Every time the protocol is updated the following computation is done:

```rust
interest_rate -= (kp * (price_error / internal_price)
                    + ki
                        * (average_of_last_50_prices
                            / internal_price)))
                    * passed_minutes;
```

With:

```rust
kp: dec!("0.00000000076517857"),
ki: dec!("0.00000000076517857"),
price_error: open_market_price - internal_price,
```

The internal price is then altered accordingly:

```rust
new_internal_price = internal_price * interest_rate.pow(passed_minutes)
```

Minimum yearly interest rate: -33.33%

Maximum yearly interest rate: +50%

If these values are exceeded by the interest rate calculation, interest rate is automatically set to the exceeded value.\
