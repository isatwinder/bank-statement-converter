# HSBC UK bank statement to Excel: layout notes

- Columns: Date, Payment type and details, Paid out, Paid in, Balance.
- The date prints only on the **first** transaction of each day; later rows that day have none.
- The balance prints only on the **last** transaction of each day. Check the running balance day
  by day.
- Payment type codes start the description: `DD` (direct debit), `SO` (standing order), `BP` (bill
  payment), `CR` (credit), `VIS` (card), `)))` (contactless), `ATM`.
- "BALANCE BROUGHT FORWARD" and "BALANCE CARRIED FORWARD" lines at page breaks are not
  transactions, but they confirm the balance at that point.
- Dates print as `DD Mon YY`, day first.

See also: [Common gotchas](../gotchas.md), [Checking a conversion](../checking.md).
