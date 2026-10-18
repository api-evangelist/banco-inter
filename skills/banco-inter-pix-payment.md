---
name: banco-inter-pix-payment
description: "Make a Pix payment through the Banco Inter Banking API with realizarPagamentoPix, then check that payment's status with consultarPagamentoPix using the codigoSolicitacao returned by the payment request."
api: openapi/banco-inter-banking-openapi.yml
operations:
- realizarPagamentoPix
- consultarPagamentoPix
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/banco-inter-banking-openapi.yml ; every operationId checked against the contract
---

# banco-inter-pix-payment

Make a Pix payment through the Banco Inter Banking API with realizarPagamentoPix, then check that payment's status with consultarPagamentoPix using the codigoSolicitacao returned by the payment request.

## Steps

1. Initiate a Pix payment using `realizarPagamentoPix` with payment details in the request body
2. Retrieve the payment status using `consultarPagamentoPix` with the `codigoSolicitacao` from the payment response in the path parameter

## Rules

- Use OAuth2 authentication via microservice_auth scheme
- Include the x-api-token header for API key authentication
- The GET operation is idempotent for checking payment status
