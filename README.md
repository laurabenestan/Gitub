# Gitub
Set-up ssh connection for gitlab and gitub

This page is for first time user of git. 

## What's git and ssh?

```git``` is the software that manages the versioning of files, it forces users to version their files systematically. 
Therefore git is different than gitlab, github, or bitbucket, which are forges. 
A forge is a web-based collaborative software platform for both developing and sharing computer applications. 
Gitub and GitLab uses the SSH protocol to securely communicate with Git. 
SSH stands for Secure Shell and is a cryptographic protocol based on the concept of public-private keys.
```git``` is a distributed version control system, which means you can work locally, then share or push your changes to a server. In this case, the server you push to is GitLab
When you use SSH keys to authenticate to the GitLab remote server, you don’t need to supply your username and password each time.

## What I need to do ?

1. First get a [github account](https://github.com).
2. Download and install [git](https://git-scm.com/downloads) - note that it is already available in datarmor
3. Set up ```git``` with your user name and email.
4. Generate a SSH key
5. Generate a token to use as password for ```git``` 

### How to check if ```git``` is installed?

Open any terminal and check if you already have Git installed by typing:

```bash 
git --version
```
If you are getting back an error message, you need to install Git.

### How to configure ```git```?

Open a terminal/shell and type:
``` bash 
git config --global user.name "Your name here"
git config --global user.email "your_email@example.com"
```
This command allows git to make the link with your email address.
To enable colored output in the terminal, you can (optionnally) type:
``` bash 
git config --global color.ui true
``` 

### How to generate ssh on your computer or on datarmor?

SSH uses two keys, a public key and a private key:
- The public key can be distributed
- The private key should be protected

To communicate with Gitub and GitLab, you can use the several SSH key types (see https://docs.gitlab.com/ee/user/ssh.html).
Here, we will generate a ed25519 keytype:
``` bash 
ssh-keygen -t ed25519
``` 
A message will appear below 
``` bash 
Generating public/private ed25519 key pair.
Enter file in which to save the key (/home/user/.ssh/id_ed25519):
``` 
Accept the suggested filename and directory by pressing ``Enter`` and specify a passphrase
``` bash 
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
``` 

Then, copy the SSH key generated to include it into your github/Gitlab account
``` bash 
cat ~/.ssh/id_rsa.pub
``` 

Go to you github account, in the Settings (access from the top-right corner on your image profile).
Then, in the SSH 

## How to generate a token for your github account?


cat ~/.ssh/id_rsa.pub
