# How to check a converted bank statement

A converted statement can be checked against figures the bank printed. If every check passes,
no row is missing, duplicated or misread. If one fails, the first failing row shows where.

## 1. The running balance

Where the statement prints a balance after each row:

```
previous balance + amount = this row's balance
```

Run it on every row. The first row where it fails is either misread itself, or a row just above
it is missing. Two common, fixable mistakes show up here: an amount read with the wrong sign, and
the balance column copied into the amount.

When the balance is printed once per day, run the same check on the last row of each day.

## 2. The summary totals

Almost every statement prints a summary:

| Bank account | Credit card |
| --- | --- |
| Opening balance | Previous balance |
| Total deposits / credits | Payments and credits |
| Total withdrawals / debits | Purchases, fees, interest |
| Closing balance | New balance |

Check:

```
bank:  opening + money in − money out = closing
card:  previous + purchases − payments = new balance
```

and compare the converted totals of money in and money out with the printed ones. Card
statements usually have no running balance at all, so this is the main check for them.

## 3. Page numbering

If pages are labelled "Page X of Y", every page from 1 to Y should be present.

## 4. Across statements

For a year of statements, each closing balance should equal the next statement's opening
balance, and periods should follow on without gaps. A mismatch usually means a statement is
missing from the batch.

## 5. Duplicates

The same date, amount and description appearing twice is often real (two coffees), but when it
appears in two overlapping statements it's a duplicate. Check overlaps between periods before
importing into accounting software.
