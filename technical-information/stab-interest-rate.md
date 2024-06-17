# 💹 STAB interest rate

**What is the STAB interest rate?**\
The STAB interest rate influences STAB's peg (or, internal price). A negative interest rate, for example, makes it cheaper over time to borrow 1 STAB, whereas a positive one does the opposite.

**Why is this useful?**\
The lower the interest rate, the higher the incentive to **borrow** STAB. And conversely, the higher the interest rate, the higher the incentive to **hold** STAB. As you can see, altering the interest rate will influence supply and demand for STAB.\
\
An asset's price is determined by where the supply and demand curve meet and by altering the interest rate in such a way that the supply and demand curves of STAB meet at the peg, we can ensure stability.

**Choosing the right interest rate**\
To measure supply and demand, we can look at STAB's price on the open market, and compare it with its peg. If STAB is trading above its peg, there is too much demand for STAB, and we need to incentivize borrowing and disincentivize holding. As we have just seen, we can accomplish this by decreasing the interest rate. The other way around works as well, if STAB is trading below its peg, we should increase the interest rate. Repeating this process over and over leads to the discovery of an optimal interest rate, where supply and demand meet: fair-priced stability is found.\
\
**Exact calculations**\
This process of STAB interest rate calculation is done through a PID-controller in the Scrypto blueprint. Every time the protocol is updated the following computation is done:

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
