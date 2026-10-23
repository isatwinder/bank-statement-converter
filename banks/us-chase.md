# Chase bank statement to Excel: layout notes

## Checking statements

- The transaction list is split into sections, such as Deposits and Additions, Checks Paid, ATM &
  Debit Card Withdrawals, and Electronic Withdrawals. Amounts inside a section are all positive;
  the section heading gives the sign.
- Dates print as `MM/DD` with no year; the year comes from the statement period at the top.
- The summary prints Beginning Balance, the total for each section, and Ending Balance, which is
  the main check.
- Descriptions for card purchases and transfers often wrap onto a second line.

## Credit card statements

- Purchases print as **positive** amounts and payments as negative. Read as a bank account, every
  purchase looks like income.
- There is no running balance. Check against Previous Balance, Payments/Credits,
  Purchases, Fees, Interest and New Balance in the account summary.
- A December statement includes January dates, or the reverse; take the year from the period.

See also: [Common gotchas](../gotchas.md), [Checking a conversion](../checking.md).
