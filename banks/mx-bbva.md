# BBVA México estado de cuenta to Excel: layout notes

Account statements in Spanish, amounts in MXN.

- **Two-line header.** The first line has `FECHA` spanning two date columns and `SALDO` spanning
  two balance columns; the second line names them:

  ```
  FECHA                                                      SALDO
  OPER   LIQ   COD. DESCRIPCIÓN   REFERENCIA   CARGOS   ABONOS   OPERACIÓN   LIQUIDACIÓN
  ```

  `OPER` is the transaction date and `LIQ` the settlement date. `CARGOS` are withdrawals and
  `ABONOS` deposits. Of the two balances, `OPERACIÓN` is the running balance; `LIQUIDACIÓN` is a
  settled balance and is best ignored for checks.
- Dates print as `DD/MON` with Spanish month abbreviations: `ENE`, `FEB`, `MAR`, `ABR`, `MAY`,
  `JUN`, `JUL`, `AGO`, `SEP`, `OCT`, `NOV`, `DIC`. Day first.
- The settlement date can also appear at the start of the description (`01/SEP SPEI RECIBIDO...`).
- The balance is not printed on every row.
- Summary labels: `Saldo Anterior` (opening), `Depósitos / Abonos`, `Retiros / Cargos`,
  `Saldo Final` (closing).
- The transaction table ends at `Total de Movimientos`. The pages after it hold other tables
  (fees, interest, fiscal data) that must not be read as transactions.
- The period prints as `DEL 01/09/2026 AL 30/09/2026`; the account number follows
  `No. de Cuenta`.
- Common description terms: `SPEI ENVIADO` / `SPEI RECIBIDO` (bank transfers), `TRASPASO`
  (transfer between accounts), `PAGO CUENTA DE TERCERO` (payment to a third party), `COMISIÓN`
  (fee), `IVA` (VAT on a fee).

See also: [Common gotchas](../gotchas.md), [Checking a conversion](../checking.md).
