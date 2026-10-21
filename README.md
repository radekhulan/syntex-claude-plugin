# Pluginy obchodů SYNTEX pro Claude

Marketplace obsahuje samostatné pluginy pro obchody SYNTEX. Nainstalujte si plugin pro obchod, který používáte. Každý plugin připojuje existující vzdálenou službu MCP příslušného obchodu přes HTTPS s přihlášením OAuth.

Dostupné pluginy: `syntex-cz`, `syntex-sk`, `syntex-en`, `syntex-hu`, `syntex-at`, `syntex-de`, `syntex-si`, `syntex-hr`, `syntex-es`.

## Instalace v Claude Code

Uvnitř Claude Code spusťte:

```text
/plugin marketplace add radekhulan/syntex-claude-plugin
/plugin install syntex-cz@syntex-storefront
/reload-plugins
/mcp
```

V `/mcp` vyberte server pluginu a dokončete přihlášení OAuth v prohlížeči. Postup připojení zobrazí `/syntex-cz:connect`. Pro katalog, objednávky a košík použijte `/syntex-cz:catalog`, `/syntex-cz:orders` a `/syntex-cz:cart`.

Jiný obchod nainstalujete nahrazením názvu pluginu, například `/plugin install syntex-sk@syntex-storefront`. Účet a přihlášení jsou pro každý obchod samostatné. Český plugin `syntex-cz` má popisy, README i instrukce česky. Ostatní pluginy mají instrukce anglicky.

Místní archiv rozbalte do trvalého adresáře a jeho absolutní cestu použijte jako zdroj marketplace. Repozitář obsahuje distribuční soubory. Pro veřejný katalog Anthropic se každá složka pluginu podává samostatně.

## Funkce

- Vyhledávání v katalogu podle kategorií, značek a technických filtrů.
- Porovnávání parametrů, aktuálních cen a dostupnosti.
- Zobrazení objednávek připojeného účtu v příslušném obchodě.
- Příprava samostatného návrhu košíku a krátkodobého odkazu pro potvrzené převzetí na webu.

Objednávku a platbu dokončujete na webu obchodu. Plugin nevybírá údaje platební karty ani neodesílá objednávky.

## Ochrana soukromí

Přihlášení OAuth probíhá na webu vybraného obchodu. Vzdálené MCP přijímá argumenty nástrojů potřebné pro úkol. Služba zpracovává autorizaci, zákaznické ceny, vlastní objednávky a samostatné návrhy košíku. Provozní záznamy MCP se řídí zásadami obchodu. Plugin nevyžaduje celou historii konverzace a neobsahuje lokální spustitelný program, automatické spouštěcí akce ani telemetrického klienta. README jednotlivých pluginů odkazují na ochranu soukromí, obchodní podmínky a podporu příslušného trhu. Před připojením si je přečtěte.

## Licence a vlastnictví

MIT platí pouze pro distribuční manifesty a instrukce pluginů. Nevztahuje se na vzdálený MCP server, aplikaci obchodu, katalogová ani zákaznická data. Názvy a grafické prvky SYNTEX podléhají právům jejich vlastníků. Tuto integraci nevytvořila ani neschválila společnost Anthropic.

## Podání do katalogu

Toto je finální instalační distribuce pro skutečné MCP adresy obchodů. Instalační ZIPy obsahují manifesty, instrukce, dokumentaci, ikony a licenci. Podklady pro podání do katalogu jsou samostatně v repozitáři u každého pluginu v `review/submission.json` a `review/test-cases.json`; do instalačních ZIPů se nebalí. Označení `draft` v těchto podkladech označuje stav podání do katalogu. Testovací scénáře nebyly při sestavení spuštěny v Claude. Veřejné schválení vyžaduje živé testy a review ve vývojářském portálu.
