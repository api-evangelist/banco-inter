---
name: setup-pix-automatico
description: Create a Pix Automático recurrence, ask the payer to confirm it, and issue recurring charges.
api: openapi/banco-inter-pix-automatico-openapi.yml
operations: [Token, recPost, postSolicRec, getSolicRec, recIdRecGet, cobrTxidPut, cobrTxidGet, cobrTxidRetentativaDataPost, addWebhookrec, addWebhookCobr]
---
# Set up Pix Automático

1. `Token` with `rec.write rec.read solicrec.write solicrec.read cobr.write cobr.read` (plus `webhookrec.write webhookcobr.write`).
2. `recPost` — POST `/pix/v2/rec` creates the recurrence (idRec).
3. `postSolicRec` — sends the confirmation request to the payer; poll `getSolicRec` or receive `addWebhookrec` callbacks until accepted. `recIdRecGet` shows recurrence status.
4. `cobrTxidPut` — PUT `/cobr/{txid}` issues each recurring charge for the approved recurrence; `cobrTxidGet` reads it; register `addWebhookCobr` for charge events.
5. `cobrTxidRetentativaDataPost` requests a retry on a given date after a failed debit.
Sandbox: `changeStatusRec`, `changeStatusSolicRec` and `makePaymentCobr` simulate payer actions.
