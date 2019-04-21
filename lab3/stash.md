# stash
Stash benyttes til hurtigt at vende tilbage til tilstanden i `head`. Altså med andre ord at nulstille alle dine ikke-committede ændringer så repositoriet bliver identisk med seneste `commit`.

Stash genererer ikke et commit, men ændringerne gemmes i en slags midlertidig liste af ændringer, der er ikke er bundet på det almindelige changetræ. 

Det betyder også at man når som helst kan hente rettelser man har `stash`et og afspille dem oven på den aktuelle tilstand i ens repository. 

De væsentligste kommandoer er

```
git stash 
```
der nulstiller rettelser og 
```
git stash pop
```
der tager seneste delta fra stash-stakken og genafspiller den. 

Bemærk at der kan ligge mange stashede ændringer gemt. Dem kan man få frem med `git stash list`. 

Jeg bruger ikke selv `stash` ret ofte, da jeg hellere laver midlertidige lokale branches. Men `stash` kan være nyttig og bør nævnes her, da `git` fra tid til anden foreslår at man bruger `stash` hvis man eksempelvis vil skifte branch og har ucommittede rettelser liggende. 


[tilbage](README.md)
