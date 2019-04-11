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

## Ret i filen og commit rettelserne 
Vi skal til at lave nogle revisioner ved at lave og committe nogen rettelser i vores fil. 

> Tilføj dit telefonnummer til filen; brug notepad eller powershell. 
```powershell
"29641657"|Out-File -append -Encoding utf8 -filepath mhf.txt
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
    +29641657


[Der findes også medfølgende GUI-baserede værktøjer. De er et fint supplement!](lab3.md)
[Tilbage til lab1](lab1.md)
