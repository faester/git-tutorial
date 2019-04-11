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

> Tilføj dit telefonnummer i filen. 
```powershell
"29641657"|Out-File -append -filepath mhf.txt
```


[Der findes også medfølgende GUI-baserede værktøjer. De er et fint supplement!](lab3.md)
[Tilbage til lab1](lab1.md)
