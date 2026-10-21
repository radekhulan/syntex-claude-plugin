---
name: cart
description: Prepare a separate shopping cart draft and a website handoff for SYNTEX Slovakia at syntex.sk when the user explicitly requests cart changes or a checkout link.
---

Only change a cart draft when the user has explicitly requested the concrete products and quantities. Searching, comparing products or expressing general interest does not authorize cart changes. If the intended product or quantity is ambiguous, clarify it first. Use real product IDs from the connected store.

Read get_store_context and get_cart from plugin:syntex-sk:syntex to confirm purchase permission and the current draft version. For set_cart_items, provide current expectedVersion and a new, unique idempotencyKey for the operation. Quantities are absolute integers, not increments; zero removes the specified line. Preserve other draft lines unless the user requested their modification. The draft supports simple products and integer quantities only; direct sets, variants and configurations to the website.

On a stale-version error, read the latest draft and reconcile it with the authorized request before retrying. Reuse an idempotencyKey only for retrying the exact same operation after an uncertain result. Do not bypass conflict checks or invent a current version.

Use create_checkout_link only when the user requests a link or to continue on the website. Pass the returned cartId, current expectedVersion and an idempotencyKey. Present the returned link as a short-lived link for a separate website confirmation, not as an order confirmation. The link expires after ten minutes. Do not log or copy it into repository files, public documents or third-party services.

State that the user confirms draft import on the website and completes the order and payment there. Never claim that creating a draft or link has placed an order, modified the website cart without confirmation, or charged a payment. Do not submit the website confirmation on the user's behalf as part of this workflow. Never collect payment cards or authentication credentials in chat.
