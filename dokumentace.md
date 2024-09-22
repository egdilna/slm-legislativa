> 🏗️ Tohle je stále dost rozpracována pracovní verze, zatím nelze použít jako funkční dokument

## Sémantický model legislativy

### Popis prvků modelu

![Diagram sémantiky legislativy](https://www.mermaidchart.com/raw/986b09ec-d02e-4a00-bcf4-1e47223e43c2?theme=light&version=v0.1&format=png)



Skupina Zdroje:  ()

- Objekt Předpis: Jeden právní předpis jako celý dokument. Jde právě a pouze o jeden předpis. ()
- Objekt Rodina předpisu: Sada dokumentů a fragementů tvořících celou rodinu předpisu. Ta obsahuje samotný právní předpis, jeho prováděcí právní předpisy (jako jsou vyhlášky) a také všechna ustanovení právního předpisu, která se v daném předpisu zmiňují (třeba odkazem, poznámkou pod čarou apod.) ()

Skupina Datové entity:  ()

- Objekt Dokument (document): dokument jednoho předpisu skládající se z metadat a všech jeho fragmentů ()
- Objekt Fragment (document fragment): Konkrétní ustanovení či jeho část jež je fragementovanou dekompozicí znění předpisu Fragmentem je paragraf, ale i jednotlivý odstavec, či jednotlivý pododstavec, písmeno, bod, apod. ()
- Objekt Reference: Vazba z jednoho fragmentu na jeden či více, reference se může jako vazba interpretovat oběma směry. Jako referenci můžeme mít i vazbu mezi ustanoveními a to i napříč předpisy. ()

Skupina Sémantické typy:  ()

- Třída Metadata předpisu: Informace o předpisu, včetně jeho identifikace, názvu, stromu platnosti, vazbených předpisů, účinností a stromu časových znění ()
- Třída Ustanovení: Jedno ustanovení právního předpisu. Jde o významovou a jazykovou skladbu z jednotlivých fragmentů, kdy se kupříkladu jazykově sestavuje věta z textu odstavce a textu jednoho písmene. (⋈A,B)
- Třída Fragment ustanovení: Každý fragment jež je součástí ustanovení jako celku. Fragmentem je třeba konkrétní písmeno v odstavci v paragrafu. ()
- Třída Pojem: Přesně uvedený pojem, ktewrý má pro daný zákon určenou definici a je v zákoně nějak konzistentně používán. V určitćh případech jde i o pojem bez definice, pokud je jeho váznym obecně známý. ()
- Třída Definice: Definice pojmu nebo soustavy pojmů, může se využít pro lepší pochopení pojmu, pro náhradu s legislativní zkratkou či označením a pro jazykové a sémantické vyavětlení pojmu používaného v ustanoveních. ()
- Třída Činnost či událost: Popis nějaké činnosti či procesu, třeba co dělá daný úřad nebo jedna strana smluvního vztahu. Většinou má logickou sémantickou vazbu na někoho nebo něco, což je obvykle pojem. ()
- Třída Úkon:  ()
- Třída Souborná konstatace: Soubor ustanovení tvořících věcně jednu skupinu, kdy platí všechny ustanovení (AND) (výsledek∀A≡B)
- Třída Rozdílová konstatace: Soubor ustanovení tvořících množinu pro výběr pro věcně jednu skupinu, kdy platí jedno z ustanovení (OR) (výsledek∋B≢A)
- Třída Podmínka: Logická podmínka, která může být splněná nebo nemusí být splnéna a podle toho se řídí další vazby na ustanovení ()
- Třída Souborná podmínka: Podmínka skládající se ze dvou či více podpodmínek, kdy všechny musí být splněny. (výsledek∪A∧B)
- Třída Rozdílová podmínka: Podmínka skládající se ze dvou či více podpodmínek, kdy některé musí být splněny. (výsledek∩∵A∨B)