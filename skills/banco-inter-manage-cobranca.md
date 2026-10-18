---
name: banco-inter-manage-cobranca
description: Create, retrieve, and manage a cobrança (charge/invoice) through its lifecycle.
api: openapi/banco-inter-cobranca-bolepix-openapi.yml
operations:
- emitirCobrancaAsync
- recuperarCobrancaDetalhada
- editarCobranca
- consultarAtualizacaoCobranca
- obterPdfCobranca
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/banco-inter-cobranca-bolepix-openapi.yml ; every operationId checked against the contract
---

# banco-inter-manage-cobranca

Create, retrieve, and manage a cobrança (charge/invoice) through its lifecycle.

## Steps

1. 1. Create a new cobrança using `emitirCobrancaAsync` with the required fields in the request body
2. 2. Retrieve the created cobrança details using `recuperarCobrancaDetalhada` with the `codigoSolicitacao` path parameter
3. 3. Update the cobrança using `editarCobranca` with the `codigoSolicitacao` path parameter and fields to update in the request body
4. 4. Check the update status using `consultarAtualizacaoCobranca` with the `codigoEdicao` path parameter
5. 5. Retrieve the cobrança PDF using `obterPdfCobranca` with the `codigoSolicitacao` path parameter

## Rules

- Use microservice_auth (oauth2) or token (apiKey in x-api-token header) for authentication
- Operations are idempotent where appropriate (GET, PATCH)
- Use pagination parameters when retrieving collections
- Handle errors according to the API response codes
