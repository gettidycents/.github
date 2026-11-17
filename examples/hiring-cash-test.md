# Can you afford a hire? Model the months before it pays off, in integer cents

**Link:** https://gettidycents.com/tools/hiring-cost-calculator (FREE, no sign-up)

Most "employee cost" calculators answer *what does the person cost?* The owner's question is different: **can the cash carry that cost in the months before the new person brings money in?** That is a month-by-month simulation, not one multiplication.

```js
// all money in integer cents
const reserve = 1_000_000;          // $10,000 minimum cash
let cash      = 5_000_000;          // $50,000 today
const profitToday = 150_000;        // $1,500 a month before the hire
const salary  = 480_000;            // $4,800 a month
const onCost  = Math.round(salary * 0.20);   // 20% employer on-costs
const startCost = 300_000;          // one-off: equipment, recruiting
const fullSales = 1_200_000;        // extra sales once fully up to speed
const margin = 0.60;                // gross margin on those sales
const ramp = 4;                     // months to full speed

let low = Infinity, payback = null, cumulative = -startCost;
cash -= startCost;
for (let m = 1; m <= 12; m++) {
  const share = Math.min(m / ramp, 1);
  const gross = Math.round(fullSales * share * margin);
  const effect = gross - salary - onCost;      // what the hire adds this month
  cash += profitToday + effect;
  cumulative += effect;
  low = Math.min(low, cash);
  if (payback === null && cumulative >= 0) payback = m;
}
console.log({ low, belowReserve: low < reserve, payback });
```

Two numbers matter more than "the hire costs $5,760 a month":

- **the cash low point**, and whether it stays above your reserve;
- **the payback month**, when the cumulative effect turns positive.

A third is useful when you negotiate: the **largest salary the extra sales pay for** at full speed, `salary * 1.2 <= fullSales * margin`.

The free calculator runs exactly this with your own numbers (its sample hire bottoms out at $43,700 in month 1 and pays for itself in month 6) and shows every step. Fixed formulas, no AI guesses.

*Tidy Cents makes tools for running your business.*
