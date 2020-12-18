---
layout: blogpost
categories: [development, git]
---
# My git aliases

As a (former?) [mercurial](https://www.mercurial-scm.org/) fan I find the default git commands too long. Just compare `git status` to `hg st`. You could argue that this is a small thing, but I'm a slow typer and it just annoys me to type out `status` when I use it a bazillion times a day. 

Luckily git has [alias](http://githowto.com/aliases)es which makes it easy for you to make new shorthands (or new) commands. I used some aliases from [Brendan Forster's blog on this very topic](http://www.brendanforster.com/notes/git-alias.html). Here they are (ready to paste into your git config file):

    [alias]
    st = status
    co = checkout
    ci = commit
    lg = log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr)%Creset' --abbrev-commit --date=relative

Or if you want the commands to make git put them in the global git config file:

    git config --global alias.st "status"
    git config --global alias.co "checkout"
    git config --global alias.ci "commit"
    git config --global alias.lg "log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr)%Creset' --abbrev-commit --date=relative"

At least git usability is now better than the default.
