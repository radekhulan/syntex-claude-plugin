---
name: connect
description: Explain how to connect or reconnect the SYNTEX Austria customer MCP service for syntexshop.at. Use when the user asks about this connection or its sign-in.
disable-model-invocation: true
---

Explain that this plugin connects to https://mcp.syntexshop.at for syntexshop.at. In Claude Code, the user opens /mcp, selects plugin:syntex-at:syntex, and uses its authentication control. OAuth sign-in and consent occur on the store website in the browser. The plugin uses discovery and dynamic client registration; it does not require a manually supplied API key or client secret.

Never ask the user to paste passwords, authorization codes, bearer tokens or private callback URLs into chat. For a connection failure, check the endpoint and selected market, ask for the non-sensitive error message, and advise reconnecting through the client's authentication controls. Do not change local client settings automatically.

Connect your customer account for this store using OAuth. The separate anonymous /catalog endpoint is not configured by this plugin.

After the user has connected, get_store_context can confirm the market, currency and purchase permissions. Do not call tools merely to test sign-in without the user's request. Existing orders, customer prices and account permissions are scoped to this account and market.
