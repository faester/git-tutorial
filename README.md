= Formål: at kunne benytte git til versionsstyring og deling af filer 


= Forudsætninger
Installer chocolatey

== Installer *chocolatey* og *git* 
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

*Du kan nu arbejde med git lokalt*

Vi antager i det følgende, at repositories ligger under `C:\workdirs`. Det er ingen forudsætning, men enkelt ift diverse eksempler. 

== Forbind til git.rootdom.dk
Skal man deles om et git-repository - og samarbejde er jo en væsentlig del af formålet med git - skal man have autentificeret sig over for git-serveren. I vores tilfælde er det `git.rootdom.dk`. 

Git bruger normalt ikke brugernavne og passwords, men public/private keys. Dvs at det er dine forskellige laptops, der for lov til at lokke ind *som dig* mod git-serveren. 

Derfor skal du starte med at lave en nøgle. 

putty-gen er en mulighed, og det er ret simpelt på Windows. 

Hvis du ikke allerede har installeret putty, så kan chocolatey hjælpe: 

```
putty install -y putty.install
```
Puttygen burde nu kunne startes fra menuen. Hvis det driller ligger den her: 
```"C:\Program Files\PuTTY\puttygen.exe" ```

For at lave en nøgle skal man bevæge musen lidt rundt. Når filen er lavet skal man sætte et password for nøglen. Brug "Conversion" -> "Export OpenSSH key". 





== Hvad indeholder et git repository

- ingenting
- men der ligger een folder `.git`, som man absolut aldrig skal røre.
- og det bør indeholde
-- .gitignore
-- README.md
