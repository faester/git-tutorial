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


## Kombiner ændringer med `merge`

Vi står nu på branchen `lab5` og ønsker at integrere ændringerne fra branchen `lab2`. 

> Men lad os lige se hvilke filer der er i folderen inden vi går i gang 
```
ls
```
Vi har to filer 

    Mode                LastWriteTime         Length Name
    ----                -------------         ------ ----
    -a----       12-04-2019     02:12             36 mhf.txt
    -a----       12-04-2019     01:57             16 mor.txt
    
    
For at kombinere branches er det enkleste er at bruge kommandoen `merge`, der simplet hen kombinerer de to. 

> Kør `git merge`

Men **ak!**, git giver en fejlmeddelelse: 

   Auto-merging mhf.txt
   CONFLICT (content): Merge conflict in mhf.txt
   Automatic merge failed; fix conflicts and then commit the result.


Der var altså en forskel i `mhf.txt`, der ikke kunne løses og git beder os om at løse problemet selv. 

Man er simpelt hen nød til at rette filen i hånden, men inden vi retter konflikten skal vi lige se indholdet i kataloget efter vi kørte merge: 

    Mode                LastWriteTime         Length Name
    ----                -------------         ------ ----
    -a----       12-04-2019     02:15             19 29641657.txt
    -a----       12-04-2019     02:15            116 mhf.txt
    -a----       12-04-2019     01:57             16 mor.txt
    
    
Vi kan se at telefonnummerfilen er kommet med over på den eksisterende branch og at filen `mor.txt` stadig ligger der. 

Til gengæld er vi nød til at rette `mhf.txt` i hånden.

<description><summary>Lad os se indholdet</summary>

    Morten Hjorth Fæster
    29641657
    <<<<<<< HEAD
    =======
    Struenseegade 53, 3
    2200 Kbh N
    Oppossum
    >>>>>>> lab2
    
Det er svært at læse - og et af de steder hvor man kan have god hjælp af nogle tools, men `<<<<<<< HEAD` betyder, at her starter indholdet fra vores aktuelle branch `lab5`. Alt efter linien med de mange lighedstegn og indtil `>>>>>>> lab2` viser hvad der står på branchen `lab2`. 

</summary>

> Ret filen i en editor, til du er tilfreds med indholdet. Dernæst skal filen tilføjes og vi skal comitte.  

```
 git add mhf.txt
 git commit -m "Merged branch lab2"
``` 

<details><summary>Grafen har nu ændret sig, så `lab5` er en integration med `lab2`. </summary>

             [merge lab2]- *lab5 \------
                    |                   \-----------------
                    |                                     |
             [mor.txt og mhf.txt]-*master      [mhf.txt med adresse]-*lab2
                    |                                     |
                    -----------------------------[mhf.txt med tlf]
                    |
            [mhf.txt med navn]
                    | 
                 [init]

</details>

*kigger vi i folderen har vi alle tre filer.*


## Kombiner ændringer med `rebase`

Kommandoen rebase har samme formål som `merge`, altså at man kan kombinere to forskellige branches. Men den fungerer temmelig anderledes. Hvor `merge` ser på forskellene på de to branches når man beder om at merge, så forsøger `rebase` at finde det tidspunkt hvor de begyndte at afvige fra hinande, og tilføje alle ændringer i rækkefølge. Efter en merge kan man således stadig følge de forskellige branches i commit-grafen, men efter `rebase` kommer der et enstrenget commit-spor. Det er der mange der synes er ønskværdigt, fordi det på nogen punkter er lettere at følge med i ændringerne. 

`rebase` fungerer sådan, at den finder den yngste fælles knude og bruger den som udgangspunkt. Så finder den toppen af den branch der bliver rebaset, og afspiller ændringer fra den aktuelle branch oven på denne. 


Så hvis udgangspunktet er nedenstående, og man står `lab2`, og forsøger en rebase på `master`, vil git finde `1a` som fælles ancester, rykke videre til `2a` og efterfølgende afspille `2b` og `3b`. 


             [2a: mor.txt og mhf.txt]-*master   [3b: mhf.txt med adresse]-*lab2
                    |                                     |
                    -----------------------------[2b: mhf.txt med tlf]
                    |
            [1a: mhf.txt med navn]
                    | 
                 [init]


Forsøger `rebase` at klippe commits {2b, 3b} af, og afspille dem oven på {2a}. 



        [3b1: mhf.txt med adresse]-*lab2
                    |
           [2b1: mhf.txt med tlf]
                    |
             [2a: mor.txt og mhf.txt]-*master 
                    |
            [1a: mhf.txt med navn]
                    | 
                 [init]


(Commits kan ikke flyttes, så selv om de principielt indeholder de samme ændringer, vil de få nye hashkoder.)

Selv om rebase tit ser pæn ud, så kan det være noget mere besværligt at gennemføre, fordi hver enkel commit bliver forsøgt afspillet igen. Hvis man løser en konflikt under vejs ændrer comittet sig, og det efterfølgende commit kan på den måde få konflikter med sin tidligere parent. 


[Tilbage til lab4](lab4.md)


[Tilbage til oversigten](basics.md)
