# SYNTEX Slovakia for Claude

Connect Claude to the customer storefront at **syntex.sk**. The plugin searches professional video and audio equipment, compares specifications and prices, reads your own orders, and prepares a separate cart draft for checkout on the store website.

## Setup

After adding the `syntex-storefront` marketplace, run this in Claude Code:

```text
/plugin install syntex-sk@syntex-storefront
```

Restart Claude Code or run `/reload-plugins`, then open `/mcp` and select `plugin:syntex-sk:syntex`. Authenticate in your browser using your store account and review the requested permissions. Credentials belong on the store's sign-in page, never in chat.

MCP endpoint: https://mcp.syntex.sk

Connect your customer account for this store using OAuth. The separate anonymous /catalog endpoint is not configured by this plugin.

The plugin uses OAuth discovery and dynamic client registration. It contains no client secret, fixed bearer token, local server or dependency installation step. The connection cannot be used to switch to another market's account.

## Workflows

- `/syntex-sk:connect`: explain sign-in, reconnecting and the selected store.
- `/syntex-sk:catalog`: find products, use real catalog filters, and compare specifications.
- `/syntex-sk:orders`: read your own order history and order details.
- `/syntex-sk:cart`: prepare a draft and a link for confirmed transfer to the store website.

You can also ask in natural language. Example: "Find Blackmagic cameras for 4K video and compare two suitable options." Prices and availability are returned at query time; final totals and purchase conditions are confirmed on the website.

Only simple products with integer quantities are supported in cart drafts. Configure sets, variants and other configurable products on the website. Creating a checkout link does not place an order or charge a payment. The customer confirms draft import and completes checkout on the website.

## Privacy Policy

The hosted store service processes the arguments needed for tool calls, OAuth authorization, account-specific pricing, own order data and draft cart data. MCP operational usage is recorded by the service according to the store's privacy policy. The plugin does not request full conversation history, passwords, API keys or card data. No standalone local telemetry or executable is included. Disconnecting or revoking the authorization is managed through the MCP client's controls and the store's connection page.

- Privacy policy: https://www.syntex.sk/i/privacy
- Terms: https://www.syntex.sk/i/vseobecne-obchodne-podmienky
- Support: https://www.syntex.sk/i/kontakt

Review the linked policy and the requested account permissions before connecting. Historical order statuses do not independently prove payment or delivery.

## License

MIT for the bundled manifests and workflow instructions only. Hosted services, store software, catalog data and customer data are outside this license. Brand assets remain subject to trademark rights. This integration is not made or endorsed by Anthropic.

## Review materials

`review/test-cases.json` contains five positive and three negative test scenarios. `review/submission.json` contains draft connector details and unresolved publication steps. These files contain no reviewer account credentials and do not assert that live testing or directory approval has occurred.
