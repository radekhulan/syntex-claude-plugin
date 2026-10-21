# SYNTEX storefront plugins for Claude

This marketplace currently connects Claude to the Syntex.cz customer storefront. Each plugin connects to the selected store's existing remote MCP service over HTTPS using OAuth.

Available plugins: `syntex-cz`.

## Installation in Claude Code

Run these commands inside Claude Code:

```text
/plugin marketplace add radekhulan/syntex-claude-plugin
/plugin install syntex-cz@syntex-storefront
/reload-plugins
/mcp
```

In `/mcp`, select the plugin's server and complete its OAuth sign-in in your browser. Use `/syntex-cz:connect` for connection instructions. Use `/syntex-cz:catalog`, `/syntex-cz:orders`, or `/syntex-cz:cart` for the corresponding workflows.

For a local archive, extract it to a permanent directory and add that directory's absolute path as the marketplace source instead. This repository contains only distribution files. Additional markets can be added later as separate plugins. A GitHub repository containing several plugins uses a separate directory submission for each plugin folder.

## Features

- Search the connected store's catalog using its categories, brands and technical filters.
- Compare product specifications, current prices and availability.
- Read orders belonging to your connected account in the selected market.
- Prepare a separate MCP cart draft and a short-lived link for confirmed transfer to the website.

Orders and payments are completed on the store website. The plugin does not collect card details or place orders. AVYX requires an approved business account; it has no anonymous catalog.

## Privacy Policy

OAuth sign-in occurs on the selected store's website. The remote MCP receives the tool arguments needed for a task, and the service processes authorization, customer-specific prices, own order history and separate cart drafts. The service records operational MCP usage according to the store's policy. The plugin does not request full conversation history and includes no local executable, lifecycle hook or telemetry client. Each plugin's README links to that market's privacy policy, terms and support. Review those policies before connecting.

## License and ownership

MIT applies to this distribution's plugin manifests and workflow instructions. It does not license the separately hosted MCP server, store application, catalog data or customer data. SYNTEX and AVYX names and brand assets remain subject to their owners' trademark rights. This is a third-party integration, not a plugin made or endorsed by Anthropic.

## Directory submission

See each plugin's `review/submission.json` and `review/test-cases.json` for draft submission materials. Test cases have not been run in Claude as part of packaging. No reviewer credentials or tokens are included. A package that passes local validation still needs live testing and the developer portal's review.
