# Gitub
Set-up ssh connection for gitlab and gitub

This page is for the first-time user of ```git```. 

## What's ```git``` and ```ssh```?

```git``` is the **software** that manages the versioning of files. 
```git``` is a distributed version control system, which means you can work locally, then share or push your changes to a server.
In this case, the server you push to is GitLab.
Therefore ```git``` is different than gitlab, github, or bitbucket, which are **forges**.

A forge is a web-based collaborative software platform for both developing and sharing computer applications. 
Gitub and GitLab uses the ```ssh``` protocol to securely communicate with ```git```. 

```ssh``` stands for Secure Shell and is a **cryptographic protocol** based on the concept of public-private keys.
When you use ```ssh``` keys to authenticate to the GitLab remote server, it recognize automatically your username and password.

## 1 - What I need to do ?

1. First get a [github account](https://github.com).
2. Download and install [git](https://git-scm.com/downloads) - note that it is already available in datarmor
3. Set up ```git``` with your user name and email.
4. Generate a ```ssh``` key
5. Generate a token to use as password for ```git``` 

### 2 - How to check if ```git``` is installed?

Open any terminal and check if you already have Git installed by typing:

```bash 
git --version
```
If you are getting back an error message, you need to install Git.

### 3- How to configure ```git```?

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

### 4- How to generate private ssh for your computer or for your datarmor account?

SSH uses two keys, a public key and a private key:
- The public key can be distributed
- The private key should be protected

To communicate with Gitub and GitLab, you can use the several ```ssh``` key types (see https://docs.gitlab.com/ee/user/ssh.html).
Here, we will generate a ed25519 keytype:
``` bash 
ssh-keygen -t ed25519
``` 
This message will appear:
``` bash 
Generating public/private ed25519 key pair.
Enter file in which to save the key (/home/user/.ssh/id_ed25519):
``` 
Accept the suggested filename and directory by pressing ``Enter`` and specify a passphrase (easy password)
``` bash 
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
``` 
This command will produce two files:
- id_rsa — this is your PRIVATE key. Don’t share this with anyone else. 
- id_rsa.pub — this is your PUBLIC key. You can share it with others.

Then, access to the ```ssh``` key generated to include it into your github/Gitlab account
``` bash 
cat ~/.ssh/id_rsa.pub
``` 
You will see a bunch of code starting by ```ssh-rsa```. Copy all this code.


Go to you github account, in the Settings (access from the top-right corner on your image profile).
Then, in the SSH and GPG keys section, click on ***New SSH key***
Paste the code copied in the previous step. 
Validate the  ***New SSH key***.

## How to generate a token for your github account?

Follow this link: https://docs.github.com/en/enterprise-server@3.4/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token.
You will always use your token as the password after performing ```git push``` command.
