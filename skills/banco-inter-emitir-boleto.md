---
name: banco-inter-emitir-boleto
description: Emit a boleto (payment slip) and retrieve its details and PDF.
api: openapi/banco-inter-cobranca-openapi.yml
operations:
- incluirBoleto
- consultarBoleto
- descarregarPdfBoleto
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/banco-inter-cobranca-openapi.yml ; every operationId checked against the contract
---

# banco-inter-emitir-boleto

Emit a boleto (payment slip) and retrieve its details and PDF.

## Steps

1. 1. Create a boleto using `incluirBoleto` with the required fields for the payment slip
2. 2. Retrieve the detailed boleto information using `consultarBoleto` with the `nossoNumero` field from the creation response
3. 3. Download the boleto PDF using `descarregarPdfBoleto` with the `nossoNumero` field

## Rules

- Use microservice_auth (oauth2) or token (apiKey, header x-api-token) authentication
- Use the https://cdpj.partners.bancointer.com.br/cobranca/v3 server for production or https://cdpj-sandbox.partners.uatinter.co for sandbox
- The `nossoNumero` field is required for retrieving and downloading boleto details
