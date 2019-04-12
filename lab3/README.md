# Lab 3 - Fortryd rettelser
Versionskontrol er ikke ret meget værd, hvis man ikke kan fortryde ændringer eller sammenligne med tidligere versioner. 

De funktioner der handler om at fortryde rettelser i git, er følgende: 

| Kommando | beskrivelse |
| -------- | -------------------------- |
| [*revert*](revert.md) | Fortryder et helt commit. |
| [*checkout*](checkout.md) | kan bruges til at tjekke en enkelt fil ud. (Men bruges normalt til at skifte branch.) |
| [*reset*](reset.md) | Kan bruges når man har ´add´'et en fil, men ikke ønsker den skal være en del af ens commit. Man kan også bruge *reset* til at fjerne rettelser i sit katalog.  |
| [*clean*](clean.md) | Er mere en oprydningskommando end en fortrydkommando. Fjerner *alle* filer, der ikke er versionskontrolleret af git. Farlig, men smart når man bygger fra kildekode og lignende.  |

[Næste øvelse](../lab4/README.md)

[Forregående](../lab2/README.md)

[Indeks](../basics.md)
