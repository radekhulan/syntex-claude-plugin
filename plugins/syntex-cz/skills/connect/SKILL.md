---
name: connect
description: Vysvětlení připojení nebo obnovení připojení zákaznické služby MCP SYNTEX pro syntex.cz. Použijte při dotazu na připojení nebo přihlášení.
disable-model-invocation: true
---

Vysvětlete, že plugin připojuje https://mcp.syntex.cz pro obchod syntex.cz. V Claude Code uživatel otevře /mcp, vybere plugin:syntex-cz:syntex a použije jeho ovládání přihlášení. Přihlášení OAuth a udělení souhlasu probíhají v prohlížeči na webu obchodu. Plugin používá automatické zjištění konfigurace a dynamickou registraci klienta. Nevyžaduje ruční zadání API klíče ani tajného klíče klienta.

Nikdy nežádejte vložení hesla, autorizačního kódu, přístupového tokenu nebo soukromé návratové URL do chatu. Při chybě ověřte endpoint a vybraný trh, vyžádejte si chybovou zprávu bez citlivých údajů a doporučte obnovení přihlášení pomocí ovládání klienta. Neměňte automaticky lokální nastavení klienta.

Připojte svůj zákaznický účet tohoto obchodu pomocí OAuth. Samostatný anonymní endpoint /catalog tento plugin nepoužívá.

Po připojení může get_store_context ověřit trh, měnu a oprávnění k nákupu. Nevolejte nástroje pouze kvůli testu přihlášení bez požadavku uživatele. Objednávky, zákaznické ceny a oprávnění platí pouze pro připojený účet a trh.
