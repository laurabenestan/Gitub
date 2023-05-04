# Gitub
Set-up ssh connection for gitlab and gitub

This page is for first time user of git. 

# What's git?

```git``` is the software that manages the versioning of files, it forces users to version their files systematically. 
Therefore git is different than gitlab, github, or bitbucket, which are forges. 
A forge is a web-based collaborative software platform for both developing and sharing computer applications. 

# What I need to do ?

1. First get a [github account](https://github.com).
2. Download and install [git](https://git-scm.com/downloads) - note that it is already available in datarmor
3. Set up ```git``` with your user name and email.
4. Generate a SSH key
5. Generate a token to use as password for ```git``` 

# How to check if ```git``` is installed

Open any terminal and check if you already have Git installed by typing:

```bash 
git --version
```
If you are getting back an error message, you need to install Git.

# How to configure ```git```?

Open a terminal/shell and type

``` bash 
git config --global user.name "Your name here"
git config --global user.email "your_email@example.com"
```
This command allows git to make the link with your email address.

Then optionnally you can type:

``` bash 
git config --global color.ui true
git config --global core.editor emacs
``` 

# How to generate ssh on your computer or on datarmor?

SSH stands for Secure Shell and is a cryptographic protocol based on the concept of public-private keys.


``` bash 
ssh-keygen -t rsa -C "your_email@example.com"
``` 

You can generate a RSA key as recoomended. https://docs.gitlab.com/ee/user/ssh.html

# How to generate a token for your github account?


cat ~/.ssh/id_rsa.pub
