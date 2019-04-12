# reset

Kommandoen reset handler mest om, at man kan fortryde at man har `add`et en konkret ændring til sit igangværende commit. 

Når man arbejder mange sammen på et repository kan det være en god ide at sikre, at der er en logisk sammenhæng i commits. Så hvis man er ved at rette en feature i en webapplikation, og på samme tid laver rettelser i backend-koden og de forskellige webviews, så kan man måske ønske at `add`e backendfilerne til et commit, og efterfølgende committe sine webviews. 

Hvis man så ved en fejl `add`er en fil man ikke ønsker skal være en del af committed, kan man lave en `git revert -- <filnavn>` og ordne det. 

## Den farlige `reset`-kommando. 

Hvis man synes alt man har lavet er noget rod, kan man køre kommandoen 

``` 
git reset head --hard
```

Det er Dirty Harry for git! **Alle ændringer i kataloget forsvinder og nulstilles til sidste commit (head).** Men nogen gange er det jo hvad man ønsker. Pas på!



[Tilbage](lab3.md)
