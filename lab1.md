# Første øvelse
Lige en bemærkning: *Git er svært!* - Man kan alt mulig smart, og 99% af tiden er det let og intuitivt. Men den sidste procent er nogen gange frustrerende. Vi prøver at være grundige med forklaringerne fra starten; det hjælper forhåbentlig senere :)

**Lad være med at bruge andet en kommandoprompten til disse øvelser** - og brug gerne så primitive værktøjer som muligt. Der er mange tools til at styre git, men de fleste af dem gør det svært at forstå hvad der sker i repositoriet. 
 
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

Det helt korte svar er, at nu har vi et git repository som vi kan tilføje filer til. 

## Tilføj den første fil

<details><summary>Vi arbejder primært med tekstfiler</summary>

 Enhver fil gemmes *enten* som en tekstfil eller som en binær fil. Man kan gemme alle slags filer i et git-repository, men git er ikke særlig smart når det gælder binære filer. Retter man i en tekstfil, så gemmes der ikke ret mange flere data, end en eksakt beskrivelse hvilke linier og tegn der er rettet.

 Hvis man gemmer et billede og retter i det, så ligger billedet to gange inde i `.git`-folderen. Det virker fint, og man kan også spole frem og tilbage i sine versioner, men man kan ikke se hvilke ændringer, der er sket i filen. 

</details>

> Opret en fil i det nye katalog. Filen skal navngives som dine initialer med endelsen `.txt`. Inde i filen skal du skrive dit fulde navn. 
Brug notepad, 


