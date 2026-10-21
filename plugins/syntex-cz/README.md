# SYNTEX pro Claude

Propojte Claude se zákaznickým účtem na **syntex.cz**. Plugin vyhledává profesionální video a audio techniku, porovnává parametry a ceny, zobrazuje vaše objednávky a připravuje samostatný návrh košíku pro dokončení nákupu na webu.

## Připojení

Po přidání marketplace `syntex-storefront` spusťte v Claude Code:

```text
/plugin install syntex-cz@syntex-storefront
```

Restartujte Claude Code nebo spusťte `/reload-plugins`. Poté otevřete `/mcp`, vyberte `plugin:syntex-cz:syntex` a přihlaste se v prohlížeči svým zákaznickým účtem. Zkontrolujte požadovaná oprávnění. Přihlašovací údaje zadávejte pouze na přihlašovací stránce obchodu.

MCP endpoint: https://mcp.syntex.cz

Připojte svůj zákaznický účet tohoto obchodu pomocí OAuth. Samostatný anonymní endpoint /catalog tento plugin nepoužívá.

Plugin používá automatické zjištění konfigurace OAuth a dynamickou registraci klienta. Neobsahuje tajný klíč klienta, pevný přístupový token ani lokální server a nevyžaduje instalaci závislostí. Připojení platí pouze pro účet a trh tohoto obchodu.

## Dostupné postupy

- `/syntex-cz:connect`: přihlášení, obnovení připojení a informace o vybraném obchodě.
- `/syntex-cz:catalog`: vyhledávání produktů, filtrování a porovnání parametrů.
- `/syntex-cz:orders`: přehled a podrobnosti vašich objednávek.
- `/syntex-cz:cart`: příprava návrhu košíku a odkazu pro jeho potvrzení na webu.

Můžete se ptát i běžnou češtinou, například: „Najdi kamery Blackmagic pro 4K video a porovnej dvě vhodné možnosti.“ Ceny a dostupnost odpovídají okamžiku dotazu. Konečné částky a podmínky nákupu potvrdí web obchodu.

Návrh košíku podporuje jednoduché produkty a celočíselné množství. Sestavy, varianty a konfigurovatelné produkty vybírejte na webu. Vytvoření odkazu nezakládá objednávku ani neprovádí platbu. Převzetí návrhu košíku i dokončení nákupu potvrzujete na webu.

## Ochrana soukromí

Služba obchodu zpracovává argumenty volání nástrojů, autorizaci OAuth, zákaznické ceny, údaje o vašich objednávkách a návrhu košíku. Provozní záznamy MCP se řídí zásadami ochrany soukromí obchodu. Plugin nevyžaduje celou historii konverzace, hesla, API klíče ani údaje platební karty. Neobsahuje samostatnou lokální telemetrii ani spustitelný program. Odpojení a zrušení oprávnění spravujete v MCP klientu a na stránce připojení v obchodě.

- Ochrana soukromí: https://www.syntex.cz/i/privacy
- Obchodní podmínky: https://www.syntex.cz/i/vseobecne-obchodni-podminky
- Podpora: https://www.syntex.cz/i/kontakt

Před připojením si přečtěte odkazované zásady a požadovaná oprávnění účtu. Historický stav objednávky sám o sobě nepotvrzuje zaplacení ani doručení.

## Licence

Licence MIT platí pouze pro distribuované manifesty a instrukce postupů. Nevztahuje se na hostované služby, software obchodu, katalogová ani zákaznická data. Grafické prvky značky podléhají právům k ochranným známkám. Tuto integraci nevytvořila ani neschválila společnost Anthropic.

## Podklady ke schválení

Toto je finální instalační balíček pro skutečnou MCP adresu obchodu. Podklady ke schválení jsou samostatně v repozitáři v `review/test-cases.json` a `review/submission.json` a do instalačního ZIPu se nebalí. Obsahují pět pozitivních a tři negativní scénáře a zbývající kroky podání do katalogu. Označení `draft` se týká stavu tohoto podání. Nepotvrzuje provedení živých testů ani schválení v adresáři.
