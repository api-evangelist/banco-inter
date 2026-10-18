---
name: check-balance-and-statement
description: Read an Inter Empresas account balance and statement, optionally as an enriched list or PDF.
api: openapi/banco-inter-banking-openapi.yml
operations: [Token, Saldo, Extrato, ExtratoComplete, ExtratoExport]
---
# Check balance and statement

1. `Token` with scope `extrato.read` (mTLS).
2. `Saldo` — GET `/banking/v2/saldo` for the available balance.
3. `Extrato` — GET `/extrato` with `dataInicio`/`dataFim` for movements in a period; use `ExtratoComplete` (`/extrato/completo`) for the enriched, paginated version.
4. `ExtratoExport` — GET `/extrato/exportar` returns the statement as a base64 PDF.
5. If the integration serves several accounts, send the `x-conta-corrente` header to pick one.
