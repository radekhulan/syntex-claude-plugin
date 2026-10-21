---
name: cart
description: Příprava samostatného návrhu košíku a předání na web SYNTEX na syntex.cz, když uživatel výslovně požádá o změnu košíku nebo odkaz k dokončení nákupu.
---

Návrh košíku měňte pouze při výslovném požadavku uživatele na konkrétní produkty a množství. Vyhledávání, porovnávání ani obecný zájem neopravňuje ke změně košíku. Nejasný produkt nebo množství nejprve upřesněte. Používejte skutečné identifikátory produktů připojeného obchodu.

Pomocí get_store_context a get_cart z plugin:syntex-cz:syntex ověřte oprávnění k nákupu a aktuální verzi návrhu. Pro set_cart_items předejte aktuální expectedVersion a nový jedinečný idempotencyKey dané operace. Množství jsou absolutní celá čísla, nikoli přírůstky. Nula odstraní uvedenou položku. Ostatní položky zachovejte, pokud uživatel nepožaduje jejich změnu. Návrh podporuje pouze jednoduché produkty a celočíselná množství. Sestavy, varianty a konfigurace řešte na webu.

Při chybě zastaralé verze načtěte nejnovější návrh a před opakováním jej porovnejte se schváleným požadavkem. idempotencyKey opakovaně použijte pouze pro tutéž operaci po nejistém výsledku. Neobcházejte kontrolu konfliktů a nevymýšlejte aktuální verzi.

create_checkout_link použijte pouze na žádost o odkaz nebo pokračování na webu. Předejte vrácené cartId, aktuální expectedVersion a idempotencyKey. Vrácený odkaz popište jako krátkodobý odkaz k samostatnému potvrzení na webu. Nepovažujte jej za potvrzení objednávky. Odkaz platí deset minut. Nezapisujte jej do logů, repozitáře, veřejných dokumentů ani služeb třetích stran.

Vysvětlete, že uživatel na webu potvrzuje převzetí návrhu a dokončuje objednávku i platbu. Netvrďte, že vytvoření návrhu nebo odkazu založilo objednávku, bez potvrzení změnilo webový košík nebo provedlo platbu. V rámci tohoto postupu nepotvrzujte převzetí na webu za uživatele. Nikdy nevybírejte údaje platební karty ani přihlašovací údaje v chatu.
