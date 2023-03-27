# How to create multi ssh keys:
## On ubuntu
go to .ssh folder from terminal 
- ```cd``` #to go to root
- ```cd .ssh```
## On windows
- create **.ssh** folder on **"C:\Users\your_username\"**

## Config in your PC
### run this command
```
ssh-keygen -t ed25519 -C "your_email@example.com"
```
### then
- enter **rsa** file name
- enter **pass** if you wanted or press enter
## Config in github
### click 
__your profile image__ **>** __sittings__ **>** __SSH and GPG keys__ **>** __new SSH key__
## copy 
your __public ssh key__ for this github account thin past it in github in new SSH key 

## If we have multi keys
### we need add config file on .ssh folder and put this on it
```
Host me github.com
    HostName github.com
    PreferredAuthentications publickey
    IdentityFile ~/.ssh/id_ed25519_me

Host work github.com
    HostName github.com
    PreferredAuthentications publickey
    IdentityFile ~/.ssh/id_ed25519_work
```
## clone repo
### from me account
```
git clone git@me:OWNER/REPOSITORY.git
```
### from work account
```
git clone git@work:OWNER/REPOSITORY.git
```
## Change git remote
```
git remote set-url origin git@github.com:OWNER/REPOSITORY.git
```


