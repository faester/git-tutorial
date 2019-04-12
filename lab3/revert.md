## Revert 
Revert kan bruges hvis man ønsker at fortryde en hel commit. Rettelsen fremgår samtidig klart af revisionshistorikken (git log). 

Den bliver lidt forvirret af vores en-linies commits fra før. Så lad os lige lave en ny fil. 

> Lav en ny fil <mit-mobilnummer>.txt og tilføj dit navn til filen. 
```
"Morten Fæster"|Out-File -encoding utf8 -filepath 29641657.txt
```
> Tilføj filen 
```
git add 29641657.txt
git commit -m  "Navn fra telefonnummer."
```

> Tilføj dit yndlingsdyr til filen navngivet efter dine initialer
```
"Oppossum" | Out-File -Encoding Utf8 -filepath mhf.txt
git add mhf.txt
git commit -m "Yndlingsdyr"
```
I loggen finder vi nu det commit, hvor telefonnummerfilen blev tilføjet. Her kan vi kigge i loggen manuelt, eller `grep` i loggen: 
```
git log --grep "Navn fra"
```

    commit 2aeb1d8bf4870d0e07229f70607ad023de686f7d
    Author: Morten F<C3><A6>ster <morten.faester@jppol.dk>
    Date:   Fri Apr 12 01:42:04 2019 +0200
    
        Navn fra telefonnummer.

> Brug den fundne checksum til at fortryde det commit hvor vi tilføjede filen: 
```
git revert 2aeb1d8bf4870d0e07229f70607ad023de686f7d
```

> Konstater at filen er fjernet og kør `git log` igen. 

<details><summary>Hvad kan du se?</summary>

Det skulle gerne fremgå at filen er forsvundet. 

</details>

> Revert at du revertede filen. 

<details><summary>brug git log</summary>

Hvis du bruger git log med *grep* som før, burde du nu se to commits. 

    C:\temp\bar [lab2]> git log --grep "Navn fra"
    commit 4520d85a6e80f5d9d03bf168d8a6dd361db297e9 (HEAD -> lab2)
    Author: Morten F<C3><A6>ster <morten.faester@jppol.dk>
    Date:   Fri Apr 12 01:45:35 2019 +0200
    
        Revert "Navn fra telefonnummer."
    
        This reverts commit 2aeb1d8bf4870d0e07229f70607ad023de686f7d.
    
    commit 2aeb1d8bf4870d0e07229f70607ad023de686f7d
    Author: Morten F<C3><A6>ster <morten.faester@jppol.dk>
    Date:   Fri Apr 12 01:42:04 2019 +0200
    
        Navn fra telefonnummer.
    

Du kan reverte 'Revert "Navn fra telefonnummer.' som via hashen for commited: 

```
git revert 4520d85a6e80f5d9d03bf168d8a6dd361db297e9
```
</details>

Filen skulle nu gerne være vendt tilbage. 

[Tilbage](README.md)
