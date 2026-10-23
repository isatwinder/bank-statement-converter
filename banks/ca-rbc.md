# RBC Royal Bank (Canada)

- Columns: Date, Description, Withdrawals, Deposits, Balance.
- Small amounts can be printed **without a leading zero** (`.15`). A parser that requires a digit
  before the decimal point silently drops these rows, and the description slides into the row
  above. The running balance shows it straight away.
- The date prints once for a group of transactions on the same day.
- The balance is not printed on every row.
- Dates print as `DD Mon`, without a year.

See also: [Common gotchas](../gotchas.md), [Checking a conversion](../checking.md).
