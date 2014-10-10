---
layout: blogpost
categories: [development, git]
---
# How to configure git without access to `HOMEPATH`

Ok, so this is weird. I don't have access to save in my `HOMEPATH` directory. What can I say: not the most natural place not to be able to save, but nonetheless that's the case (I have access to save in all subfolder, but still). Anyway since `HOMEPATH` is the default place to save global git configuration files this is a bit awkward. 

Git comes with default settings (stored in the installation path) and since I have permission to write there that makes it possible to still solve the the global configuration problem. 

## Translating `git config --global` commands to lines in gitconfig

Typically configuring git is done with the `git config --global` (if it's a global git setting anyway.). The setting in then saved to your `HOMEPATH` 

Example: 

`git config --global user.name "Ada Lovelace"`

will write this: 

`[user]
	name = "Ada Lovelace"`

to the `gitconfig` file. 

I would normally configure the following things (on Windows):

`git config --global alias.st "status"`

`git config --global alias.co "checkout"`

`git config --global alias.ci "commit"`

`git config --global alias.lg "log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr)%Creset' --abbrev-commit --date=relative"`

`git config --global user.name "Ada Lovelace"`

`git config --global user.email "ada@lovelace.org"`

`git config --global push.default "matching"`

`git config --global credential.helper "winstore"`

which translates to:

`[alias]
	st = status
	co = checkout
	ci = commit
	lg = log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr)%Creset' --abbrev-commit --date=relative
[user]
	name = "Ada Lovelace"
	email = "ada@lovelace.org"
[push]
	default = matching
[credential]
	helper = winstore`

in the `gitconfig` file.

Please note that you should only use the last configuration if you actually install [git-credential-winstore](https://gitcredentialstore.codeplex.com/) (which I recommend if you are on windows).

## tl;dr

Directly edit the `gitconfig` file in the `<install path>/Git/etc/` folder (typically `C:\Program Files (x86)\Git\etc` on Windows). 