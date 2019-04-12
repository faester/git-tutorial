# Indbyggede værktøjer 

De værktøjer der nævnes her går vi ikke i dybden med. 

## git grep
Sindssygt smart hvis man skal søge i et versionsstyret katalog, fordi man *kun* søger i versionsstyrede filer. Indeholder kataloget filer fra eksempelvis en byggeproces, så vil de ikke blive inkluderet. 

På Windows er det også bare meget rart at det er en normal grep kommando...

## git log 
Den har vi set på før, men et par små tilføjelser: 

```
git log -- <filnavn>
```
Viser alle ændringer, der har berørt en given fil. Så hvis man ønsker at se hvemder har modificeret en fil hvornår, kan det være en hjælp. 

Ovenstående fungerer også, hvis man skal lede efter en forsvunden fil! -- Og dermed hvornår den forsvandt. 

## git gui

Er en grafisk brugergrænseflade til git. Man kan alle de samme ting som på kommandolinien. Og der er en diff-visning, der kan være virkelig nyttig. 


## gitk

Er en slags grafisk viewer til `git log`. Understøtter også `--` hvis man kun vil se specifikke filer. 


[Indeks](../basics.md)

