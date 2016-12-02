# Steps to Set Up Git &amp; GitHub

## Table of Contents

* [Getting Started](https://github.com/nashvillefcc/SettingUpGit#getting-started)
  * [Create GitHub Account](https://github.com/nashvillefcc/SettingUpGit#user-content-1-create-a-github-account)
  * [Installing Git](https://github.com/nashvillefcc/SettingUpGit#user-content-2-install-homebrew-and-git)
* [Setting SSH Key](https://github.com/nashvillefcc/SettingUpGit#user-content-3-ssh-key)
  * [Generate SSH Key](https://github.com/nashvillefcc/SettingUpGit#user-content-1-generate-ssh-key)
  * [Add SSH Key to GitHub](https://github.com/nashvillefcc/SettingUpGit#user-content-2-add-ssh-key-to-github)

## Getting Started

### 1. Create a GitHub Account
Create a GitHub account [here](https://www.github.com/join)

### 2. Install HomeBrew and Git
#### MAC User
If a Mac user then you need to open your terminal. After that you should install [HomeBrew](http://brew.sh/) which you can do with the following command. HomeBrew is going to allow us to install additional things that are not included with the Mac OS. It will be our way to install Git.

_(The `$` represents the prompt.  This is not something you type and yours could look different)_
```
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
You may get a few prompts and be asked for your password.  This is the password you use to log in to your computer.  After it is installed you will need to run the command `brew doctor`.
```
$ brew doctor
```
Next perform an update to make sure that you have everything you need.
```
$ brew update
```
Now we can install Git with the following command.
```
$ brew install git
```
This will install Git on your computer globally so that you are now able to use it as a version control.  However, this does not do anything with GitHub.  At this point we are simply setting up our personal computer to use Git.

At this point you should be able to type `git --version` in your terminal and get a version number back.  If not, then the install was not successful.

#### WINDOWS User
If you are on a Windows machine then I suggest using [GitBash](https://www.git-scm.com/downloads) as your command prompt/terminal instead of [powershell](https://en.wikipedia.org/wiki/PowerShell). It will allow you to use common [bash](https://en.wikipedia.org/wiki/Bash_(Unix_shell)) commands _(although some do not work)_ and use Git commands.

## SSH Key
We now have Git installed and a GitHub account, but we do not have a bridge connecting the two.  That is what we are going to do next through an `SSH key`.

### 1. Generate SSH Key
Your first step is to [generate a new SSH key](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/).  If you follow the steps in this link then you should get everything created locally.

### 2. Add SSH Key to GitHub
Your next step is to [add the key to your GitHub account](https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/).  This link should help with the second step of this process.

_(This process can be intimidating at first but just be sure to read over the directions and follow each step.  Ask for help if you need it!)_

### Test SSH
Next we can do a quick [test in the terminal](https://help.github.com/articles/testing-your-ssh-connection/) to see if we can connect to GitHub by typing the following command.
```
$ ssh -T git@github.com
```

The first time you may get the message:
```
The authenticity of host 'github.com (192.30.252.1)' can't be established.
RSA key fingerprint is 16:27:ac:a5:76:28:2d:36:63:1b:56:4d:eb:df:a6:48.
Are you sure you want to continue connecting (yes/no)?
```
or possibly:
```
The authenticity of host 'github.com (192.30.252.1)' can't be established.
RSA key fingerprint is nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8.
Are you sure you want to continue connecting (yes/no)?
```
You need to simply type `yes` in the prompt, press return and you should receive this response:

`Hi {USER_NAME}! You've successfully authenticated, but GitHub does not provide shell access.`

