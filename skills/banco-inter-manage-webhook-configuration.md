---
name: banco-inter-manage-webhook-configuration
description: Create, retrieve, update, or delete webhook configurations for banking, cobrança, and boleto services.
api: openapi/banco-inter-banking-openapi.yml
operations:
- putWebhookBanking
- getWebhookBanking
- deleteWebhookBanking
- webhookPut
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/banco-inter-banking-openapi.yml ; every operationId checked against the contract
---

# banco-inter-manage-webhook-configuration

Create, retrieve, update, or delete webhook configurations for banking, cobrança, and boleto services.

## Steps

1. 1. Create or update a webhook configuration using `putWebhookBanking` with the `tipoWebhook` path parameter and webhook configuration in the request body
2. 2. Retrieve the current webhook configuration using `getWebhookBanking` with the `tipoWebhook` path parameter
3. 3. Delete a webhook configuration using `deleteWebhookBanking` with the `tipoWebhook` path parameter
4. 4. Create or update a cobrança webhook using `webhookPut` (PUT /cobrancas/webhook) with webhook configuration in the request body
5. 5. Create or update a boleto webhook using `webhookPut` (PUT /boletos/webhook) with webhook configuration in the request body

## Rules

- Authentication requires either OAuth2 microservice_auth or API token in x-api-token header
- Operations are idempotent for PUT methods when creating or updating webhooks
- Use appropriate server URLs: banking endpoints use /banking/v2, cobrança uses /cobranca/v3, and boleto uses appropriate endpoints
