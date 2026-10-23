# TD Canada Trust statement to Excel: layout notes

- Columns: Description, Withdrawals, Deposits, Date, Balance. The date column comes **after** the
  description and amounts, so parsers that expect the date first misplace every row.
- Dates print as `MON DD` (for example `SEP14`), without a year.
- Small amounts can be printed without a leading zero (`.15`); see [RBC](ca-rbc.md).
- "Balance forward" opens each page and is not a transaction.

See also: [Common gotchas](../gotchas.md), [Checking a conversion](../checking.md).
