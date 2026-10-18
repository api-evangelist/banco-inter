---
name: obtain-access-token
description: Obtain an OAuth 2.0 client-credentials access token over mTLS for the Inter Empresas APIs.
api: openapi/banco-inter-token-openapi.yml
operations: [Token]
---
# Obtain an access token (Banco Inter)

1. Create an integration in Internet Banking PJ and download its certificate and key; every request (including this one) is sent over mutual TLS with them.
2. `Token` — POST `/oauth/v2/token` as `application/x-www-form-urlencoded` with `client_id`, `client_secret`, `grant_type=client_credentials` and `scope` (several scopes separated by spaces, e.g. `extrato.read boleto-cobranca.write`). Each operation's description names the scope it needs.
3. Send `Authorization: Bearer <token>` on later calls; tokens last about one hour, so cache and renew instead of requesting one per call.
4. Production host `https://cdpj.partners.bancointer.com.br`, Sandbox `https://cdpj-sandbox.partners.uatinter.co`. Never reuse production credentials in Sandbox.
