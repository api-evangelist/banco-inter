---
name: banco-inter-pagar-boleto
description: Make a barcode payment using the Banco Inter API.
api: openapi/banco-inter-banking-openapi.yml
operations:
- pagarBoleto
- buscarInformacoesPagamentos
- cancelarAgendamentoBoleto
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/banco-inter-banking-openapi.yml ; every operationId checked against the contract
---

# banco-inter-pagar-boleto

Make a barcode payment using the Banco Inter API.

## Steps

1. 1. Call `pagarBoleto` POST /pagamento with payment details including barcode, amount, and due date
2. 2. Call `buscarInformacoesPagamentos` GET /pagamento to verify the payment status
3. 3. If needed, call `cancelarAgendamentoBoleto` DELETE /pagamento/{codigoTransacao} to cancel a scheduled payment

## Rules

- Use OAuth2 microservice_auth or API token in x-api-token header for authentication
- Check for idempotency requirements in payment operations
- Handle pagination when searching for payment information
