# Arbejde med remotes
## Forbind til git.rootdom.dk
Skal man deles om et git-repository - og samarbejde er jo en væsentlig del af formålet med git - skal man have autentificeret sig over for git-serveren. I vores tilfælde er det `git.rootdom.dk`. 

Git bruger normalt ikke brugernavne og passwords, men public/private keys. Dvs at det er dine forskellige laptops, der for lov til at lokke ind *som dig* mod git-serveren. 

Derfor skal du starte med at lave en nøgle. 

putty-gen er en mulighed, og det er ret simpelt på Windows. 

Hvis du ikke allerede har installeret putty, så kan chocolatey hjælpe: 

```
choco install -y putty.install
```
Puttygen burde nu kunne startes fra menuen. Hvis det driller ligger den her: 
```"C:\Program Files\PuTTY\puttygen.exe" ```

For at lave en nøgle skal man bevæge musen lidt rundt. Når filen er lavet skal man sætte et password for nøglen. Brug "Conversion" -> "Export OpenSSH key". 

Kopier nu den eksporterede fil til din lokale .ssh-folder
```
cp <eksporteret-fil> ~\.ssh\id_rsa
```

Endelig skal man gennemføre nedenstående for at slippe for at tampe sin key-passphrase ind konstant

```
Import-Module 'C:\tools\poshgit\dahlbyk-posh-git-9bda399\src\posh-git.psd1'
Set-Alias ssh-agent "$env:ProgramFiles\git\usr\bin\ssh-agent.exe"
Set-Alias ssh-add "$env:ProgramFiles\git\usr\bin\ssh-add.exe"
Start-SshAgent -Quiet
```
(Kan kopieres til $profile) 

For at det fungerer skal den offentlige nøgle kopieres til git.rootdom.dk



1. Kopier *hele* indholdet af "Public key for pasting into OpenSSH authorized_keys file"
2. Gå til https://git.rootdom.dk/settings/keys
2. Log ind
3. "New SSH key"
4. Angiv dit maskinnavn i "Title"
5. Paste fra putty-gen til feltet "Key"
6. Gem.



## Hvis du ikke vil overskrive din nøgle fil. 
Generer en nøgle som beskrevet ovenfor
Kopier den offentlige nøgle som beskrevet oven for
Kopier den *private* nøgle til ~/.ssh/git.rootdom.dk 
Ret/opret filen `~/.ssh/config` så den indeholder 

```
Host git-rootdom git.rootdom.dk
	HostName git.rootdom.dk
	IdentityFile ~/.ssh/git.rootdom.dk
	User git 
```
Skal tilføjes ssh-agent med `ssh-add ~/.ssh/git.rootdom.dk`

# Hvad indeholder et git repository

- ingenting
- men der ligger een folder `.git`, som man absolut aldrig skal røre.
- og det bør indeholde
-- .gitignore
-- README.md

