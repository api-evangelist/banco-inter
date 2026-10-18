---
name: pay-with-pix
description: Send a Pix payment from an Inter Empresas account and confirm its status.
api: openapi/banco-inter-banking-openapi.yml
operations: [Token, realizarPagamentoPix, consultarPagamentoPix, putWebhookBanking]
---
# Pay with Pix (Banking)

1. `Token` with `pagamento-pix.write pagamento-pix.read`.
2. `realizarPagamentoPix` — POST `/banking/v2/pix` with the value and destination (key, copy-paste code or bank data). Send the `x-id-idempotente` header (a UUID you store) so a retry never pays twice.
3. `consultarPagamentoPix` — GET `/pix/{codigoSolicitacao}` to read the final status; or register `putWebhookBanking` for the Pix payment webhook type and wait for the callback.
4. Payments may require approval in the Inter app depending on account settings; treat a pending status as non-final.
