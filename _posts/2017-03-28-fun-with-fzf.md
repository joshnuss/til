---
layout: default
title: Fun with FZF
tags: fzf, vim, emacs
---

# FZF is neat

With FZF, you can add fuzzy finding to any command.

# Install

Install `fzf` with a `brew install fzf` or `git clone --depth 1 https://github.com/junegunn/fzf.git ~/.fzf && cd ~/.fzf && ./install`

# Open files with autocomplete

You can pass the results of `fzf` as the arguments to another command (eg `vim`)

```bash
# open file with autocomplete
vim $(fzf)
```

or add an alias to `~/.bash_aliases`

```bash
# ~/.bash_aliases
alias fvi="vim $(fzf)"
```

# Changing git branch with autocomplete

You can also pipe anything to `fzf`, for example you can pipe you list of git branches `git branch | fzf`. You can take those results and pass them to `git checkout` by doing `git checkout $(git branch | fzf)`

```bash
# ~/.bash_aliases
alias fco='git checkout $(git branch | fzf)'
```
