# Auditing a card-processing statement: expected vs billed, without guessing

**Link:** https://gettidycents.com/product/merchant-fee-audit-switch-lab (paid tool, $29 one-time; the free demo uses fictional data)

A statement total is not something you can check against a headline rate. You check it **rule by rule, charge by charge**, and you keep anything you cannot explain apart instead of averaging it away.

```js
// contract: 1.6% + $0.10 per payment (cents)
const rule = { pct: 0.016, fixed: 10 };
const payments = Array(2000).fill(4000);          // 2,000 payments of $40

const expected = payments.reduce(
  (sum, amount) => sum + Math.round(amount * rule.pct) + rule.fixed, 0);
const billed = 163000;                            // what the statement says

console.log(expected, billed - expected);
// 148000 15000  -> $1,480 expected, $150 to explain
```

That $150 is **not** an overcharge yet. Refunds, disputes, a monthly fee or a different card group can explain it. The honest output has three buckets:

1. differences supported by a complete rule and record;
2. items that cannot be checked (missing rule, card group or channel), shown as unresolved;
3. credits you actually received, allocated once.

Comparing a new provider works the same way: run the **same transactions** through the other offer, add setup, equipment and exit fees, and find the month the switch pays back.

*Tidy Cents makes tools for running your business. No AI guesses: every result shows its working.*
