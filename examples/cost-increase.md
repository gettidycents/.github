# Passing on a cost increase: why 8% up is not 8% on your prices

**Link:** https://gettidycents.com/tools/cost-increase-calculator (FREE, no sign-up)

A cost increase hits only the part of your costs it applies to. Treat it that way and the price rise you need is smaller than the headline number, but bigger than the lazy estimate.

## The example

- Sales: $60,000 a month, gross margin 40% → cost of goods $36,000
- Other monthly outflows (rent, wages, etc.): $19,000
- Profit: $5,000

Supplier +8%, rent and wages +5%:

```js
// integer cents, no floats for money totals
const cogs = 3_600_000, other = 1_900_000, sales = 6_000_000;
const extra = Math.round(cogs * 0.08) + Math.round(other * 0.05); // 288_000 + 95_000
const profitAfter = sales - cogs - other - extra;                 // 117_000 = $1,170
const priceRise = extra / sales;                                   // 0.0638 → 6.4%
```

- Extra cost: **$3,830 a month**
- Profit: **$5,000 → $1,170** (77% less)
- Price rise to win it back at the same volume: **6.4%**

Not 8% (only part of your costs went up 8%), and not 4.8% (8% × the 60% cost share forgets the rent and wages).

The free Cost Increase Calculator does this with your own numbers and also shows how long the cash above your reserve lasts. Fixed formulas that show their working, no AI guesses.

*Tidy Cents makes tools for running your business.*
