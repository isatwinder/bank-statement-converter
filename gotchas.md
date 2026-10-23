# Common gotchas

The problems below show up across many banks. Most of them don't cause an error. They produce a
spreadsheet that looks right and isn't.

## Descriptions that wrap over several lines

Long descriptions continue on a second or third line with no date and no amount. Some banks put
the continuation **below** the line with the date and amount, others put the first part of the
description **above** it. Guess the wrong direction and every description is shifted by one row.

At a page break, the tail of the last transaction can land at the top of the next page, above the
repeated column headers.

## Amounts without a leading zero

Some statements print small amounts as `.15` rather than `0.15`. A parser that expects a digit
before the decimal point skips the row, and its description often merges into the row above.
The total is off by a few cents, which is easy to miss.

## Number formats

| Printed | Meaning |
| --- | --- |
| `1,234.56` | US, UK, Canada, Mexico |
| `1.234,56` | Much of Europe and Latin America |
| `1,23,456.78` | India (lakh grouping) |
| `(12.00)` | Negative, accounting style |
| `45.00 DR` / `45.00 CR` | Debit / credit suffix |
| `45.00-` | Trailing minus |

## Signs

There are three common ways a statement says whether money went in or out:

1. **Separate columns:** Withdrawals / Deposits, Debits / Credits, Paid out / Paid in, Cargos / Abonos.
2. **One amount column with signs or DR/CR markers.**
3. **Sections:** amounts are all positive, and the section heading ("Deposits and other additions",
   "Withdrawals and other subtractions") gives the sign.

Credit card statements reverse the meaning: purchases are usually printed **positive** (they
increase what you owe) and payments negative. Converted naively, every purchase looks like income.

## Dates without a year

Most statements print `09/14` or `14 Sep` with no year. The year comes from the statement period.
A December-to-January statement needs care, or January's transactions land in the wrong year.

Date order is another trap: `03/04` is 4 March in the US and 3 April in the UK, Canada (often),
Mexico and India. The country of the bank decides it, not the file.

## Two dates per row

Many banks print a transaction date and a posting (or value) date. Some put the second date at
the start of the description instead of in its own column.

## Repeated headers and page furniture

Column headers repeat on every page, sometimes with an extra column in a later section.
Page numbers, "continued on next page", marketing boxes and rewards summaries sit on the same
lines as transactions. On card statements a rewards box is often printed to the **right** of the
transaction table, on the same y positions.

## Balance carried forward

"Balance brought forward" / "carried forward" lines repeat at page breaks. They are not
transactions, but they are useful: each one confirms the running balance at that point.

## Balance printed once per day

Some banks print the running balance only on the last transaction of each day. Rows without a
balance are normal there, and a check has to work day by day.

## Missing pages

Statements are often downloaded or scanned with a page missing. "Page 2 of 5" labels show it,
when they're printed. Without them, a gap in the running balance is the only sign.

## Several accounts in one statement

Combined statements (checking + savings, or several cards) contain a separate table and separate
balances per account. Merging them into one list breaks every balance check.
