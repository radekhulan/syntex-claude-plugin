---
name: orders
description: Zobrazení vlastních objednávek připojeného zákazníka a jejich podrobností z SYNTEX na syntex.cz, když uživatel požádá o historii objednávek.
---

Použijte list_my_orders v připojení plugin:syntex-cz:syntex a následně get_my_order s přesným orderId z výsledku. Identifikátory maloobchodních objednávek jsou řetězce, AVYX může vracet ERP GUID. Nezaměňujte identifikátor za zobrazené číslo a nevymýšlejte jej. Vyžadujte jen údaje potřebné k zodpovězení dotazu.

Zůstaňte v rozsahu připojeného účtu a trhu. Nehádejte identifikátory objednávek jiných zákazníků, neměňte identitu a nepoužívejte administrátorský konektor. Při požadavku na cizí soukromou objednávku vysvětlete, že připojení zpřístupňuje pouze oprávněná data připojeného účtu.

Uložené stavy popisujte přesně. Vyřízená ERP objednávka sama o sobě nepotvrzuje zaplacení ani doručení. Nástroje čtou uložená data objednávek a nedotazují platební bránu. Chybějící důkaz výslovně uveďte. Neúspěšné vyhledání nedokazuje, že objednávka nikdy neexistovala. Popište vrácenou chybu nebo omezení oprávnění.

Nerušte ani neměňte objednávky, nevyřizujte vrácení peněz, neprovádějte platby a neupravujte katalog. Tyto operace zákaznický postup objednávek neposkytuje. Nikdy nežádejte hesla, údaje platební karty ani přihlašovací tokeny do chatu.
