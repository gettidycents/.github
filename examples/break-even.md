# Break-even in integer cents (FREE tool)

Try it free, no sign-up: https://gettidycents.com/tools/break-even-calculator

- Break-even sales = fixed costs ÷ gross margin
- Break-even units = fixed costs ÷ contribution per unit, rounded UP
- Margin of safety = (sales − break-even) ÷ sales

```js
const beSales = (fixedCents, marginBp) => marginBp > 0 ? Math.ceil(fixedCents * 10000 / marginBp) : null;
const beUnits = (fixedCents, priceCents, varCents) => priceCents > varCents ? Math.ceil(fixedCents / (priceCents - varCents)) : null;
```

Example: fixed $12,400.00, margin 38% → break-even $32,631.58/month; at $36,000 sales the margin of safety is 9.35%.

Tidy Cents — tools for running your business. 170+ tools, 30+ free. No AI guesses: every result shows its working.
