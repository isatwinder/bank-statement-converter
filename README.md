# Bank statement converter

A bank statement converter turns a PDF bank or credit card statement into a spreadsheet: one row
per transaction, with the date, description, amount and balance in their own columns, ready for
Excel, Google Sheets or accounting software.

This page explains how bank statement conversion works, why it so often goes wrong, and how to
tell whether a converted statement can be trusted. The notes below cover the layouts of real
statements from banks in the United States, Canada, the United Kingdom and Mexico.

[BankStatementHub](https://bankstatementhub.com) is a free bank statement converter built on these
notes. No signup needed.

## How to convert a bank statement PDF to Excel

1. **Download the statement as a PDF** from online banking. A downloaded PDF converts far more
   accurately than a scan or a photo, because the text is already in the file.
2. **Upload it to a converter.** Password-protected statements need the password first.
3. **Review the rows.** Compare the result with the original, especially the first and last
   transactions and the totals.
4. **Export** to Excel (XLSX) or CSV, or to a format your accounting software imports:
   QuickBooks, Xero, Quicken, OFX or QIF.

## Why converting a bank statement is harder than it looks

A PDF has no table inside it. It holds words placed at x/y positions on a page, and a converter
has to rebuild rows and columns from those positions. Every bank lays its statement out
differently, and small details break the result:

- descriptions that run over two or three lines
- amounts printed as `.15` instead of `0.15`
- credit card statements where purchases are printed as positive amounts
- dates without a year, and day-first or month-first date order
- balances printed only once per day
- column headers, page numbers and side panels mixed in with transactions

The dangerous part is that most of these failures are silent. A dropped row still gives you a
spreadsheet that looks fine. More in [Common gotchas](gotchas.md).

## What to look for in a bank statement converter

- **Balance checks.** The converter should check every row against the running balance printed
  on the statement, and the totals against the opening balance, closing balance and summary.
  This is the only way to know nothing was dropped or misread. See
  [Checking a conversion](checking.md).
- **Credit card support.** Card statements reverse the signs and usually have no running balance,
  so they need checking against the printed summary instead.
- **Multi-page and multi-statement support.** A year of statements should convert in one go, with
  missing pages, gaps between months and duplicates flagged.
- **Export formats.** Excel and CSV for spreadsheets; QBO, OFX, QIF or a CSV in the right column
  order for QuickBooks, Xero and Quicken.
- **Local date and number formats.** `03/04/2026` means different days in the US and the UK, and
  `1.234,56` is a normal amount in much of Europe and Latin America.

## Bank statement layouts by bank

How each bank prints its statement, and what to watch for when converting it:

| Country | Bank |
| --- | --- |
| United States | [Chase](banks/us-chase.md) · [Bank of America](banks/us-bank-of-america.md) · [Discover](banks/us-discover.md) · [Capital One](banks/us-capital-one.md) |
| Canada | [RBC Royal Bank](banks/ca-rbc.md) · [TD Canada Trust](banks/ca-td.md) |
| United Kingdom | [HSBC](banks/uk-hsbc.md) |
| Mexico | [BBVA México](banks/mx-bbva.md) |

## Frequently asked questions

**Can Excel convert a bank statement PDF by itself?**
Excel's "Get Data from PDF" (Microsoft 365 on Windows) can read simple tables, but it struggles
with descriptions that wrap over several lines, section-based layouts and repeated page headers.
The result usually needs a lot of cleanup.

**Is copy and paste good enough?**
For a few rows, maybe. For a whole statement, columns rarely line up and multi-line descriptions
split into separate rows. Check the totals afterwards either way.

**Can scanned statements be converted?**
Yes, but scans need text recognition first and are less accurate than downloaded PDFs. Check them
against the printed balances with extra care.

**How do I convert a credit card statement to Excel?**
The same way as a bank statement, but check the signs: card statements print purchases as
positive amounts. Compare the converted totals with the previous balance, payments, purchases and
new balance printed in the summary.

**How do I convert several months of statements at once?**
Use a converter that takes multiple files and combines them into one spreadsheet, tagging each row
with its source statement. Then check that each closing balance matches the next statement's
opening balance. BankStatementHub does this on its
[bulk converter](https://bankstatementhub.com/bulk) page.

## Contributing

Layouts change. If a bank's statement looks different from what's described here, or you know a
layout that isn't covered, open an issue or a pull request. Please never attach a real statement:
describe the layout, or recreate it with made-up data.

Text content is licensed under [CC BY 4.0](LICENSE).
