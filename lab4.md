# Lab 4 - Branches 

Vi udførte [tidligere](lab2.md) kommandoen `git checkout -b lab2` uden at forklare ret meget. 

Igen skal vi udføre en kommando uden særlig meget forklaring, nemlig: 
```
git checkout master 
```
<details><summary>Hvad tror I der sker, hvis man kigger i arbejdskataloget nu? - Og hvorfor?</summary>
Vi er tilbage ved diskussionen om perlekæder, metronet og vejbaner. 

Du vi i sin tid udførte `git checkout -b lab2` lavede vi en ny branch. Nu er vi vendt tilbage til repositoriet, sådan som det så ud lige inden vi skiftede branch, og alle vores rettelser er nu forsvundet. 

Eller rettere: Vores rettelser er gemt inde i `.git`-folderen, men kigger vi direkte i kataloget er de væk. 

                                                 [mhf.txt med adresse]-*lab2
                                                         |
                    -----------------------------[mhf.txt med tlf]
                    |
            [mhf.txt med navn]-*master 
                    | 
                 [init]


De to rettelser hvor vi tilføjede telefonnummer og adresse er simpelt hen spolet tilbage. Vores `head` peger nu på en anden tilstand i versionshistorien. 
</details>

Lad os gøre livet surt for os selv og tilføje nogle rettelser, som vi ved kommer til at skabe konflikter. 

## Logning


[Næste øvelse handler nemlig om at løse konflikter i git](lab5.md)
[Tilbage til oversigten](basics.md)
