# Discover credit card statement to Excel: layout notes

Credit card statements.

- The transaction tables have no "Description" heading. The description column is titled by the
  section name instead: `TRANS. DATE | PAYMENTS AND CREDITS | AMOUNT`, then
  `TRANS. DATE | PURCHASES | MERCHANT CATEGORY | AMOUNT`.
- The Purchases section adds a **Merchant Category** column (Supermarkets, Restaurants,
  Gasoline...). In the PDF text it can be joined to the end of the description in a single run, so
  it has to be split off by position. The category is useful: it can stand in when the merchant
  name gives no clue.
- A side panel with rewards and account details sits to the right of the table on the same lines.
- The transaction table ends at "Interest Charge Calculation". The tables after it (interest
  rates, year-to-date totals) contain amounts and dates that must not be read as transactions.
- Purchases are positive and payments negative. There is no running balance; check against
  Previous Balance, Payments and Credits, Purchases, and New Balance.

See also: [Common gotchas](../gotchas.md), [Checking a conversion](../checking.md).
