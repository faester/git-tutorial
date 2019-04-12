# Lab 5 - konflikter. 

Vi har lavet en række ændringer i en fil på en branch, og er vendt tilbage til vores master, hvor vi har tilføjet en række ændringer ovne i de rettelser, vi lavede i vores branch. 

Dette simple eksempel minder om den situation, hvor to forskellige udviklere har rettet i hver deres fil.

> Lav en ny branch 'lab5'

<details><summary>Hvordan var det nu man lavede en branch?</summary>

```
git checkout -b lab5
```
</details>


             [mor.txt og mhf.txt]-*master,*lab5  [mhf.txt med adresse]-*lab2
                    |                                     |
                    -----------------------------[mhf.txt med tlf]
                    |
            [mhf.txt med navn]
                    | 
                 [init]



[Tilbage til lab4](lab4.md)
[Tilbage til oversigten](basics.md)
