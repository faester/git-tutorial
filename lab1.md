# Første øvelse
## Lav et git-repository
Alle kommandoer i git udføres ved at skrive `git` efterfulgt af mellemrum og den kommando man ønsker at udføre. 

*Start med at stille dig i et nyt blankt katalog.* Eksempelvis `C:\work\git-tutorial`. 

Vores aller første kommando er 
```
git init 
```

<details>
<summary>Hvad har vi opnået her?</summary>
  
I sig selv giver kommandoen `git init` ikke ret mange synlige resultater. Hvis du er i posh git (powershell) eller en anden terminal, der forstår git, vil du se at prompten ændrer sig 
```
C:\temp\foo> git init
Initialized empty Git repository in C:/temp/foo/.git/
C:\temp\foo [master]>
```
Det er fordi powershell nu kan se at vi står i et git repository. Ligesom responsen fra `git init` i øvrigt også fortæller os. 

Hvis man viser skjulte filer kan man også se, at der er kommet en ny underfolder - `.git`. Der ligger en mængde filer i denne folder, som hjælper git med at holde styr på resten af repositoriet. *Rør aldrig indholdet af `.git`*
</details>
