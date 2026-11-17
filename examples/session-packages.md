# Prepaid session packages: money received vs sessions owed

Session & Package Control — PAID $19 one-time, FREE demo: https://gettidycents.com/product/session-package-control

```js
const COUNTS = { attended: 1, late_cancel: 1, no_show: 1, cancelled_ok: 0 };
const used = p => p.events.reduce((n, e) => n + COUNTS[e.type], 0);
const left = p => p.sessions - used(p);
const owedCents = p => Math.floor(p.priceCents / p.sessions) * left(p);
```

10 sessions for $900.00, 2 used → 8 left → $720.00 of service still owed although $900.00 is in the bank. A freeze extends expiry at read time: expiresOn + frozenDays.

Tidy Cents — tools for running your business. 170+ tools, 30+ free.
