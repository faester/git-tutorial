# clean 

Clean bruges til at fjerne filer, der ikke er versionsstyrede fra et katalog. 

Igen er det en lidt "farlig" kommando, men den er meget nyttig, hvis man bygger kode og vil fjerne alle genererede og downloadede filer. 

> Prøv at tilføj filen `sletmig.txt` uden at `add`e eller lignende. 

Kør nu kommandoen 
```
git clean -xdf
```

Ovenstående fjerner alle ikke-versionsstyrede filer fra kataloget!
