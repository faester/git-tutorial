# Lab 2 - Ret i filer, kig på historikken
Vi har nu et git repository og en enkelt fil. 

Lad os prøve at rette i denne fil. 

> Inden vi foretager os andet skal du dog lige udføre nedenstående kommando, som vi [forklarer senere](lab4.md).

```
git checkout -b lab2
```
<details><summary>Ovenstående er en forudsætning for at vi kan gennemføre en af de senere øvelser.</summary>

 Hvis du udfører nedenstående 
```
git branch 
```
burde du få en indikation af hvad vi har gjort. Output skal være 
```
* lab2
  master
```
der fortæller at vi har to lokale branches og at `lab2` er den aktive, da den er markeret med * 
</details>

## Ret i filen
Vi skal til at lave nogle revisioner ved at lave og committe nogen rettelser i vores fil. 

> Tilføj dit telefonnummer til filen; brug notepad eller powershell. 
```powershell
"29641657"|Out-File -append -Encoding utf8 -filepath mhf.txt
```
## Se hvilke filer der er rettet 
Hvis man vil se hvilke rettelser der er sket i et katalog, kan man bruge kommandodoen `git status`. Den viser en oversigt over alle de rettelser der er sket i et givent katalog. 

> Vis ændrede filer i kataloget
```
git status 
```
Output skulle meget gerne være i stil med 

    On branch lab2
    Changes not staged for commit:
      (use "git add <file>..." to update what will be committed)
      (use "git checkout -- <file>..." to discard changes in working directory)
     
            modified:   mhf.txt
     
    no changes added to commit (use "git add" and/or "git commit -a")

Den væsentligste information er selvfølgelig, at der er rettet i en enkelt fil. I det konkrete tilfælde `mhf.txt`. Bemærk at der står "Changes not staged for commit"; rettelserne i filen vil ikke blive inkluderet i næste commit. (Som man kan se er der også lidt hjælp til hvad man kunne tænkes at have brug for at foretage sig nu.)

> Gør rettelserne klar til næste commit 
```
git add mhf.txt
```
De aktuelle rettelser i filen er nu klar til at komme med i næste commit. 

> Vi ser nu hvad `status` rapporterer 
```
git status 
```
    On branch lab2
    Changes to be committed:
      (use "git reset HEAD <file>..." to unstage)
    
            modified:   mhf.txt
    
    
## Commit 
> Lad os se at få rettelsen committed.
```
git commit -m "Mit telefonnummer"
``` 
Output bør indeholde `1 file changed, 1 insertion(s)`

Nu er vores rettelse gemt. Men vi har brug for lidt flere rettelser - og skal se lidt mere på hvad der sker med `git add` og `git commit`.

## Se rettelser i filer
Før så vi hvilke *filer* der var ændret med `git status`, men ofte er det jo mindst lige så interessant at se *hvad* der er rettet i filerne. 

> Lad os tilføje et vejnavn til vores fil. 

```
"Struenseegade 53, 3"|Out-File -Append -Encoding Utf8 -FilePath mhf.txt
``` 

> Vi beder nu git om at vise os hvilke ændringer der er i kataloget
```
git diff
```
<details><summary>Du skulle nu gerne få følgende output: </summary>
Hvis du får en besked i stil med 
```
diff --git a/mhf.txt b/mhf.txt
index b375a8a..5d29466 100644
Binary files a/mhf.txt and b/mhf.txt differ
```
hvor det mest interessante er "Binary files [..] differ", er det fordi Windows har begavet os med en BOM (byte-order-marker) i starten af vores meget korte fil, der får git til at tro det er en binær fil. 

Man kan bruge filen `.gitattributes` til at pege git i den rigtige retning. 

Konkret kan man tilføje nedenstående linie til `.gitattributes` for at sikre at diffs bliver vist i et læsbart format: 
```
\*.txt diff
```
</details>

    diff --git a/mhf.txt b/mhf.txt
    index b375a8a..7123acf 100644
    --- a/mhf.txt
    +++ b/mhf.txt
    @@ -1 +1,2 @@
    <EF><BB><BF>Morten Hjorth F<C3><A6>ster
    29641657
    +Struenseegade 53, 3

Her kan vi se at gadenavnet er tilføjet (med det initielle '+'). Derudover er der et par liniers kontekst og information om filen. 

Man kan også bede om at se ændringerne i en specifik fil med 
```
git diff -- mhf.txt
```
det giver ingen reel forskel lige nu, at vi jo kun har en fil. Men de to bindestreger bruges mange steder til at fortælle, at man kun vil arbejde med een fil. 

> Tilføj rettelsen 
```
git add mhf.txt
```
Vi committer *ikke* rettelsen. 

> I stedet filføjer vi lige vores postnummer og by til filen.
```
"2200 Kbh N"|Out-File -Append -Encoding Utf8 -FilePath mhf.txt
```

Hvis vi kører `git diff` nu, er det kun ændringen i sidste linie der vises. Som udgangspunkt viser diffen altså kun ændringer, der ikke er added. Man kan diffe med en hvilken som helst rettelse, prøv i stedet 
```
git diff head
```
der gerne skulle vise ændringer i begge de tilføjede linier. 

> Commit rettelserne 

```
git commit -m "Min adresse"
```



[Der findes også medfølgende GUI-baserede værktøjer. De er et fint supplement!](lab3.md)
[Tilbage til lab1](lab1.md)
