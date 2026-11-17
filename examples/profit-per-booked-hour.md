# Profit per booked hour: why the bigger ticket can earn less

**Link:** https://gettidycents.com/product/salon-capacity-service-profit (paid tool, $9.90 one-time; the free demo uses a fictional salon)

In any business that sells time (salons, studios, clinics, workshops) the scarce resource is the slot, not the service. Rank services by **contribution per hour of slot**, not per visit.

```js
// cents and minutes
const services = [
  { name: 'Haircut', price: 6000, products: 400,  slotMin: 60 },
  { name: 'Colour',  price: 9000, products: 1500, slotMin: 120 },
];
const commission = 0.40, cardFee = 0.02;

for (const s of services) {
  const pay = Math.round(s.price * commission);
  const fee = Math.round(s.price * cardFee);
  const perVisit = s.price - s.products - pay - fee;
  const perHour = Math.round(perVisit * 60 / s.slotMin);
  console.log(s.name, perVisit, perHour);
}
// Haircut 3080 3080   -> $30.80 a visit, $30.80 per chair hour
// Colour  3720 1860   -> $37.20 a visit, $18.60 per chair hour
```

The colour leaves more per visit and much less per hour of chair time. When the book is full, every colour slot could have been two haircuts.

The full tool adds what the simple version leaves out: cancellations and no-shows under your deposit rules, package cash vs visits still owed, capacity per person and station (the tightest one sets the limit; capacities are never added), and the visits you need to break even.

*Tidy Cents makes tools for running your business. No AI guesses: every result shows its working.*
