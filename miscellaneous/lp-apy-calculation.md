# ➕ LP APY calculation

The 7d Real APY shows how profitable providing liquidity has been the last 7 days, compared to just holding both tokens.

<pre class="language-javascript"><code class="lang-javascript"><strong>7_day_real_apy = ((lp_valuation_now / lp_valuation_7_days_ago)^(365 / 7) - 1) * 100;
</strong></code></pre>

With `lp_valuation_now` being the value of 1 LPSTAB token currently.

And `lp_valuation_7_days_ago` being the value of 1 LPSTAB token 7 days ago <mark style="color:red;">**WITH CURRENT STAB and XRD PRICES!**</mark>

Because for both valuations the current asset prices are used, it makes for a fair comparison between holding and providing liquidity.
