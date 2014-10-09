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

``

## tl;dr

Directly edit the `gitconfig` file in the `<install path>/Git/etc/` folder (typically `C:\Program Files (x86)\Git\etc` on Windows). 