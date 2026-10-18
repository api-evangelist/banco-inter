---
name: manage-webhooks
description: Register, inspect, delete and replay Banking webhooks for Inter Empresas events.
api: openapi/banco-inter-banking-openapi.yml
operations: [Token, putWebhookBanking, getWebhookBanking, getBoletosWebhookCallbacks, postWebhookCallbacksRetry, deleteWebhookBanking]
---
# Manage Banking webhooks

1. `Token` with `webhook-banking.write webhook-banking.read`.
2. `putWebhookBanking` — PUT `/banking/v2/webhooks/{tipoWebhook}` with an HTTPS `webhookUrl` (Inter calls it with mTLS).
3. `getWebhookBanking` confirms the registration; `deleteWebhookBanking` removes it.
4. `callbacksFilter` lists callbacks sent in a period (with delivery status); `retryCallback` resends failed ones.
5. Make handlers idempotent: retries and replays deliver the same event more than once.
Pix and Cobrança have their own webhook operations in their contracts (`webhookPut`, `webhookGet`, `webhookDelete`).
