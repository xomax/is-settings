Vlastní validace
===

Do formulářů lze vkládat validace závislé na políčcích, která se nacházejí na stejné stránce.

Vlastní validace lze kombinovat se základní validací (např. na celé číslo atd.)

Validace se závislostí se zapisují do políčka *"Nastavení validace"*, chybová hlášky při nesplnění se používá z políčka *Chybový popisek*.


Podporované validace:
---

**ereg**

Libovolný regulární výraz zpracovávaný PHP funkcí `preg_match`. Zapisuje se bez ohraničujících znaků.

Zápis: `ereg::regularni-vyraz`

Příklad: `ereg::([a,b,n]){3}`

**preg**

Stejná funkce jako **ereg**, zápis je nutné uvést i včetně ohraničujících znaků a případných modifikátorů.

Zápis: `preg::regularni-vyraz`

Příklad: `preg::|([a,b,n]){3}|ig`

**fnc**

Zavolání interní funkce systému. Pro toto využití je nutné znát PHP část, která je připravena na validaci.

Zápis: `fnc::nazev-funkce`

Přiklad: `fnc::is_numeric`

**value**

Kontrola stejné hodnoty vůči jinému políčku.

Zápis: `value::hodnota`

Přiklad 1: `value::jaro` pro kontrolu, že je vyplněná hodnota text "jaro"

Přiklad 2: `value::@field3` pro kontrolu, že je vyplněná hodnota stejná jako v políčku s ID 3 na té samé stránce, nebo je hodnota políčka s ID 3 mezi vybranými hodnotami pole, které je validováno (v případě, že se jedná o checkboxy)

**value<**

Kontrola, zda je hodnota menší než zadaná hodnota v jiném políčku.

Zápis: `value<::hodnota`

Přiklad 1: `value<::1000` pro kontrolu, že je vyplněná hodnota menší než 1000

Přiklad 2: `value<::@field3` pro kontrolu, že je vyplněná hodnota nižší než hodnota v políčku s ID 3 na té samé stránce

**value>**

Kontrola, zda je hodnota vyšší než zadaná hodnota v jiném políčku.

Operuje se stejnou logikou jako **value<**

**value<=**

Kontrola, zda je hodnota nižší nebo rovna zadané hodnotě v jiném políčku.

Operuje se stejnou logikou jako **value<**

**value>=**

Kontrola, zda je hodnota vyšší nebo rovna zadané hodnotě v jiném políčku.

Operuje se stejnou logikou jako **value<**

**percent<=**

Kontrola, zda je hodnota nižší nebo rovna procentu hodnoty jiného pole.

Zápis: `percent<=::procento%@id-pole`

Přiklad: `percent<=::70%@field3` pro kontrolu, že je vyplněná hodnota menší nebo rovna 70 % hodnoty políčka s ID 3 na té samé stránce

**percent>=**

Kontrola, zda je hodnota vyšší nebo rovna procentu hodnoty jiného pole.

Operuje se stejnou logikou jako **percent<=**


Platné pro systémy:
---

- IS Sport (2018)
