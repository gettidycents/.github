# Comparing sales channels per order, in integer cents

**Link:** https://gettidycents.com/product/marketplace-profit-price (paid tool, $9.90 one-time; the free demo shows a fixed example)

"The marketplace takes 15%, so my own site must be better." Let's check per order.

```js
const price = 4000, make = 1200, pack = 150, ship = 600; // cents

// marketplace: 15% fee
const marketplace = price - make - pack - ship - Math.round(price * 0.15); // 1450 → $14.50

// own site: ~$1.50 card fee + $6 of ads to win the order
const ownSite = price - make - pack - ship - 150 - 600;                    // 1300 → $13.00
```

The channel with the big fee leaves **$14.50**; the "cheap" one leaves **$13.00** once you pay to bring the buyer in.

Add returns (kept, resold, written off) and your own minutes per order, and the ranking can flip again. That is the whole point: compare per order, not per fee.

Marketplace Profit & Price does this for every channel side by side, finds the minimum price and the most you can spend on ads per order, and tests a discount or free shipping before you run it. **Paid tool, $9.90 one-time.** The free demo shows a fixed example; your own figures need the paid version. No AI guesses: every result shows its working.

*Tidy Cents makes tools for running your business.*
