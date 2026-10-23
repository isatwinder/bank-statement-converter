# Capital One credit card statement to Excel: layout notes

Credit card statements.

- As with Discover, the description column can be titled by the section name (for example
  "Transactions" or "Payments, Credits and Adjustments") rather than "Description".
- Two dates per row: transaction date and posting date, printed as `Mon DD`.
- Separate tables per cardholder on accounts with authorised users; each has its own total.
- Purchases positive, payments negative, no running balance. Check against Previous Balance,
  Payments, Other Credits, Transactions, Fees, Interest and New Balance.

See also: [Common gotchas](../gotchas.md), [Checking a conversion](../checking.md).
