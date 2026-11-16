# Profit per bottleneck minute: a restaurant example

**Link:** https://gettidycents.com/product/menu-profit-planner (paid tool, $9.90 one-time; the free demo shows a fixed example)

When a kitchen is full, the scarce resource is not ingredients. It is minutes on the busiest station. So rank dishes by profit per bottleneck minute, not per plate.

```js
const price = 1400, food = 420, grillMin = 4; // cents, minutes

const dineIn   = price - food;                              // 980 → $9.80
const delivery = price - food - Math.round(price * 0.30) - 80; // 480 → $4.80

dineIn / grillMin;   // 245 → $2.45 per grill minute
delivery / grillMin; // 120 → $1.20 per grill minute
```

On a busy night each delivery burger takes a grill slot that could earn about twice as much in the dining room.

Menu Profit Planner works out the contribution of every dish in every channel, finds the station that limits you, builds a production plan in whole portions and shows what a new ingredient price does to every recipe. **Paid tool, $9.90 one-time.** The free demo shows a fixed example; entering your own menu needs the paid version. No AI guesses.

*Tidy Cents makes tools for running your business.*
