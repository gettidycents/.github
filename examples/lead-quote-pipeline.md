# Quote pipeline: one next action per lead

Lead & Quote Recovery Desk — PAID $19 one-time, FREE demo: https://gettidycents.com/product/lead-quote-recovery-desk

Rule: every lead that is not won or lost has exactly one next action with a due date. "Overdue" is computed from the due date, never stored.

```js
function status(lead, today) {
  if (lead.outcome) return lead.outcome.result;
  if (!lead.nextAction) return 'NO NEXT STEP';
  return lead.nextAction.due < today ? 'OVERDUE' : 'ON TRACK';
}
```

Win rate per source = won ÷ (won + lost), closed leads only.

Tidy Cents — tools for running your business. 170+ tools, 30+ free.
