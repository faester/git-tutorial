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

Lad os gøre livet surt for os selv og tilføje nogle rettelser, som vi ved kommer til at skabe konflikter senere. Ligeledes tilføjer vi nogle, der ikke gør. 

> Lav filen 'mor.txt' og skriv din mors og dit eget fornavn i filen. 

> Tilføj dit telefonnummer i 'din egen' fil. 

> Tilføj de to filer med `add` og commit dem. 

Du skulle nu have to filer. 

> Sammenlign din aktuelle branch med vores tidligere branch 'lab2'
```
git diff lab2
```
<details><summary>Hvad viser dit output?</summary>

    diff --git a/29641657.txt b/29641657.txt
    deleted file mode 100644
    index c7ad9f4..0000000
    --- a/29641657.txt
    +++ /dev/null
    @@ -1 +0,0 @@
    -<EF><BB><BF>Morten F<C3><A6>ster
    diff --git a/mhf.txt b/mhf.txt
    index 50edb7c..7123acf 100644
    --- a/mhf.txt
    +++ b/mhf.txt
    @@ -1,5 +1,2 @@
     <EF><BB><BF>Morten Hjorth F<C3><A6>ster
     29641657
    -Struenseegade 53, 3
    -2200 Kbh N
    -Oppossum
    diff --git a/mor.txt b/mor.txt
    new file mode 100644
    index 0000000..f73705c
    --- /dev/null
    +++ b/mor.txt
    @@ -0,0 +1 @@
    +Morten - Marie
    
</details>

Lige nu ser grafen omtrent sådan her ud: 


             [mor.txt og mhf.txt]-*master       [mhf.txt med adresse]-*lab2
                    |                                     |
                    -----------------------------[mhf.txt med tlf]
                    |
            [mhf.txt med navn]
                    | 
                 [init]



[Næste øvelse handler om at løse konflikter mellem branches i git](lab5.md)
[Tilbage til oversigten](basics.md)
