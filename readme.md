# Zápočet 2

## Simulátor play-off MS v ledním hokeji 2023

## https://github.com/hridel/fei23_zap2

Napište program v jazyce C, který ze souboru [data/input.csv](data%2Finput.csv) načtěte do vhodně zvolené datové struktury
účastníky MS v ledním hokeji.

Datový soubor CSV (comma separated values) má tuto strukturu:

* id (krátké označení týmu)
* team (název týmu)
* group (označení skupiny _A_ nebo _B_)
* standings (konečné pořadí týmu v základní skupině)

**Ukázka souboru:**

| id | team | group | standings |
| :--- | :--- | :--- | :--- |
| GER | Germany | A | 4 |
| CAN | Canada | B | 1 |

Hlavním cílem programu je simulovat play-off turnaje a rozhodnout
o umístění na medailových pozicích.

Během simulace play-off bude program simulovat jednotlivé zápasy.
Každý zápas má jednoho vítěze a jednoho poraženého. Výsledek každého zápasu vypište
na obrazovku a do textového souboru pomocí formátovacího řetězce ve tvaru:

```text
Fáze turnaje:   Název týmu 1 skóre Název týmu 2  
```

* Fáze turnaje je vypsána vždy na velikost 3 znaků včetně dvojtečky a může být:
    * **QF:** (čtvrtfinále)
    * **SF:** (semifinále)
    * **L:** (souboj o třetí místo)
    * **W:** (finále)
* **Název týmu 1** odpovídá plnému názvu týmu (sloupeček _team_ zdrojového souboru) a bude zarovnán na velikost 15 znaků vpravo.
* skóre bude vypsáno ve formátu **_počet_branek_týmu_1_:_počet_branek_týmu_2_** bude vypsáno celkem na velikost 5 znaků (pozic).
* **Název týmu 2** odpovídá plnému názvu týmu (sloupeček _team_ zdrojového souboru) a bude zarovnán na velikost 15 znaků vlevo.

Příklad výpisu čtvrtfinálového zápasu mezi Kanadou a Německem s výsledkem 3:1 je tedy:

```text
QF:          Canada  3:1  Germany       
```

Do čtvrtfinálových zápasů nastoupí tyto týmy (podle umístění v základních skupinách):
* _A1 x B4_
* _A2 x B3_
* _A3 x B2_
* _A4 x B1_

Kde _A1_ je označení týmu, který ve skupině _A_ skončil na _prvním_ místě, _B3_ je označení týmu, který skončil ve skupině _B_ na _třetím_ místě, atp.

Do semifinálových zápasů pak týmy:
* Vítěz duelu _A1 x B4_ proti vítězi duelu _A2 x B3_
* Vítěz duelu _A3 x B2_ proti vítězi duelu _A4 x B1_

Do bojů o 3. místo:
* poražení ze semifinálových zápasů

Do finále postoupí:
* vítězové ze semifinálových zápasů

Na konec výstupního souboru a na obrazovku vypište umístění týmů na medailových pozicích.

```text
...

1. Název týmu
2. Název týmu
3. Název týmu
```

Konečné zdrojové soubory (*.c, případně *.h) a výstupní textový soubor nahrajte v archivu typu ZIP na STAG.