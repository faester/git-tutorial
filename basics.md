# Basisviden
Vi starter med en bunke definitioner. Og lige om lidt prøver vi at illustrere med noget praksis. 

## Distribuerede repositories
Git er distribueret. Det vil sige, at man arbejder med en fuld kopi af et repository. I princippet er den lokale kopi man har liggende på sin laptop ikke forskellige fra det der ligger på en server.

Når man skal dele sit arbejde synkroniserer man sine egne ændringer, med en anden udgave af repositoriet. Ligeledes kan man tilføje ændringer fra andres repositories til sin egen kopi. 

Git er smart nok til kun at sende ændringerne frem og tilbage. 

Normalt synkroniserer man med en kopi hos [github](https://github.dom) eller vores lokale betalte udgave på [https://git.rootdom.dk](https://git.rootdom.dk). Men man kan også dele filer via et netværksshare. Repositories er ikke bundet til  en specifik server, så man kan godt dele sine ændringer med både github og vores lokale repository.

## Changes - perlekæder
Som omtalt ovenfor er et git repository en række ændringer, der er kædet sammen. Man kan næsten forestille sig en perlekæde, hvor hver perle er en samlet beskrivelse af hvilke filer der er ændret "siden sidst". 

Hver perle (delta, eller changesæt) repræsenterer et `commit`. 

                              [head]
                                |
                             [ændring2]
                                |
                             [ændring1]
                                |
                              [tom]


Man kan også have flere perlekæder, der er bundet sammen i specifikke knuder. Det kan være smart, fordi man på den måde har en genvej til en specifik tilstand. 

## Branches - pegepinde
I git kan man som omtalt lave en såkaldt `branch`. Det er i praksis blot et navngivet "bogmærke", der peger på en bestemt ændring -- et specifikt `commit`. 

                             [head]-master    [parallelunivers]-dev
                                |                    |
                             [ændring2]        [eksperiment2]
                                |                    |
                             [ændring1]--------[eksperiment1]
                                |
                            [ændring0] 
                                |
                              [tom]

Branching er enormt smart, hvis flere skal arbejde sammen, fordi den enes ændringer (og fejltagelser) ikke berører den andens arbejde. 

Men branches er også den primære kilde til frustrationer og `merge konflikter`. I ovenstående tænkte eksempel kunne man forstille sig, at den person der arbejder i stien `[head]` retter i en fil, der også modificeres i `[parallelunivers]`. Det vil gå fint, men på et tidspunkt skal ændringerne i de to branches samles til en fælles virkelighed igen, og på det tidspunkt kan man få en del problemer. 

Generelt er kortlevede branches en god ide. Branches der lever mere end et par dage er i reglen altid en kilde til problemer. 

Det er normal praksis at man har een branch, der afspejler sin seneste release, og løbende arbejder i en anden branch. Man committer *aldrig* direkte til master. Men lige nu skal vi ikke dvæle ved den slags detaljer. 

[Lad os se nogle eksempler](lab1.md)

Der er [en oversigt over basiskommandoer her](basic-commands.md)
