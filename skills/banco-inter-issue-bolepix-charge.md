---
name: issue-bolepix-charge
description: Issue, track, download and cancel a boleto with Pix (Cobrança v3 / BolePix).
api: openapi/banco-inter-cobranca-bolepix-openapi.yml
operations: [Token, emitirCobrancaAsync, recuperarCobrancaDetalhada, obterPdfCobranca, pesquisaCobranca, consultarSumario, cancelarCobranca, pagarCobranca]
---
# Issue a BolePix charge

1. `Token` with `boleto-cobranca.write boleto-cobranca.read`.
2. `emitirCobrancaAsync` — POST `/cobranca/v3/cobrancas` (seuNumero, valorNominal, dataVencimento, numDiasAgenda, pagador). Issuance is asynchronous: keep the returned `codigoSolicitacao`.
3. `recuperarCobrancaDetalhada` — GET `/cobrancas/{codigoSolicitacao}` until the boleto and Pix data are present; prefer the webhook (`webhookPut`) over polling.
4. `obterPdfCobranca` — base64 PDF to send to the payer.
5. `pesquisaCobranca` / `consultarSumario` to list and summarise by period and situação.
6. `cancelarCobranca` — POST `/cobrancas/{codigoSolicitacao}/cancelar` with `motivoCancelamento`.
7. Sandbox only: `pagarCobranca` simulates payment.
Do not use Cobrança v2 (`/boletos`) for new work: it is deprecated.
