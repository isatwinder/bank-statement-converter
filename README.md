# Bank statement formats

How real bank and credit card statements lay out their transactions in PDF, and the details that
break naive PDF-to-Excel conversion. Written for developers building statement parsers, and for
bookkeepers wondering why a converted spreadsheet doesn't add up.

No code here, just notes. Every layout described was seen on real statements; account details,
names and amounts in the examples are made up.

## Contents

- [Common gotchas](gotchas.md): the problems that show up across many banks
- [Checking a conversion](checking.md): how to prove a converted statement is complete
- Bank notes:
  - United States: [Chase](banks/us-chase.md), [Bank of America](banks/us-bank-of-america.md), [Discover](banks/us-discover.md), [Capital One](banks/us-capital-one.md)
  - Canada: [RBC](banks/ca-rbc.md), [TD](banks/ca-td.md)
  - United Kingdom: [HSBC](banks/uk-hsbc.md)
  - Mexico: [BBVA México](banks/mx-bbva.md)

## The short version

A PDF statement has no table inside it, only words placed at x/y positions on a page. Every
converter rebuilds rows and columns from those positions, and the failures are rarely loud: a
dropped row or a description joined to the wrong transaction still produces a spreadsheet that
looks fine. The only reliable defence is to check the result against numbers the bank printed
itself: the running balance, and the opening balance, closing balance and totals in the summary.

## Contributing

Layouts change. If a bank's statement looks different from what's described here, or you know a
layout that isn't covered, open an issue or a pull request. Please never attach a real statement:
describe the layout, or recreate it with made-up data.

## About

These notes come out of building [BankStatementHub](https://bankstatementhub.com), a free bank
statement converter. Text content is licensed under [CC BY 4.0](LICENSE).
