# Checkout 

## Nulstil ændringer der ikke er committed.
Checkout kan bruges til at flytte pegepinden rundt i commit-grafen, og den kan bruges til at nulstille specifikke filer. 

> 1. Slet indholdet i din eksempelfil. 
> 2. Check forskellen med `git diff`
> 3. Udfør kommandoen `git checkout -- <filnavn>`
> 4. Check forskellen med `git diff`

Du skulle nu gerne se, at indholdet i filen er vendt tilbage. 

`checkout` er en kommando, der henter indholdet fra en bestemt revision. Med `--` fortæller vi, at vi kun vil modificere en specifik fil. 



## Nulstil ændringer der *er* committed.
Man kan også bruge `checkout` til at fortryde rettelser.

> 1. Slet indholdet i din eksempelfil. 
> 2. `commit` filen husk at `add`e

Filen er nu tom. Prøv nu at eksekvere kommandoen 

```
git checkout head~1
```

Vi ser nu at indholdet er vendt tilbage. I praksis har vi flyttet vores pointer i revisionsgrafen - `head` - til det commit vi lavede *inden* vi fjernede indholdet af filen.

<details><summary>Hvad betyder advarslen?</summary>
Helt grundlæggende at `head` peger et sted, det vil være meget vanskeligt at finde igen!
</details>

> Vend tilbage til vores branch

```
git checkout `lab2`
``` 

Filen er nu - forhåbentlig - tom igen. 

### Men hvordan fortryder vi rettelsen i den konkrete fil?

Vi så at vi kunne flytte `head` et commit tilbage oven for. 

Men vi kan også vælge at bede om at tilbageføre en konkret fil til fordums storhed, ved at lave et checkout af filen fra et tidligere commit. I stedet for `git checkout -- <filnavn>` kombinerer vi de to kommandoer. 

```
git checkout head~1 -- <filnavn>
```

Nu skulle filen gerne indeholde det sammme, som inden vores sidste commit. 

`head~1` betyder faktisk 'forrige commit' og `--` fortæller vi kun vil lade det berøre en enkelt fil.


Bemærk at `git status` nu viser, at filen er ændret. 

Hvis vil gøre vores tilbageføring af indholdet permanent skal vi `add`e og `commit`te.

> `add` og `commit` så indholdet bliver reetableret.

[Tilbage til lab3](README.md)
