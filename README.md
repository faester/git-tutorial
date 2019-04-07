# Formål: at kunne benytte git til versionsstyring og deling af filer 


# Forberedelser 

## Installer *chocolatey* og *git* 
https://chocolatey.org/install

Installer *chocolatey* fra en _eleveret_ powershell: 

```Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))```

Installer git (stadig eleveret): 

```
choco install -y git.install 
```
Da vi skal arbejde med powershell er det også en god ide at installere posh-git, der giver en bedre integration med powershell. 

```
choco install -y poshgit
```

## Sæt et brugernavn
Der er faktisk valgfrihed på alle hylder, men det er nok mest hensigtsmæssigt du vælger noget der identificerer dig selv, og ikke din kollega. Sikkerhedsmodellen er anderledes i git end eksempelvis svn. Mere om det senere, men lad os lige nu antage vi opfører os ordentligt. 

```
 git config --global user.name "Jens Hansen"
 git config --global user.email "jens.hansen@jppol.dk"
```
Alternativt kan du bede om at rette direkte i gits configurationsfil med 
```
git config --global --edit
```

*Du kan nu arbejde med git lokalt*

Vi antager i det følgende, at repositories ligger under `C:\workdirs`. Det er ingen forudsætning, men enkelt ift diverse eksempler. 

For at [arbejde med remotes](./remotes.md) skal der en del besværgelser til, men heldigvis kun første gang. Gem det til senere. 

Vi er nu klar til at [arbejde med basale git-kommandoer](./basics.md)
