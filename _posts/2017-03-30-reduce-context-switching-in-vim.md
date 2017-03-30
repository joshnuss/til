---
layout: default
title: Reduce Context Switching in VIM
tags: rails, vim
---

# Reduce Context Switching in VIM

When editing code, switching between files causes context switching. Anything that reduces this will increase focus.

For example, you might be in some file and want to go to the related test, or you may be looking at a Pull Request and want to open all it's related files. You have to start thinking about what the file is called or where it might be. This *should* be easy.

Well now it is..

Lately, I've been experimenting with different ways of accomplishing this, and starting building up shortcuts.

Let me share them with you.

## Open related test

For alternating between code and tests, I use [rails.vim](https://github.com/tpope/vim-rails). It provides a helpful command `:A` to open alternate file. I map it to `,.`.

You can map it in your `.vimrc` with `noremap <Leader>. :A<CR>`

## Chaining VIM

Cool things happen when you chain `vim` together with other commands like `git`.

A common pattern I use is `vim -O $(....)`, let me explain:

  - `vim` is the command, could be anything, i.e. `emacs`
  - `-O` opens a list of files in vertical split mode, i.e. `vim -O file1.txt file2.txt`
  - `$(...)` can be any command that returns a list of files. i.e. `vim -O $(find .)` opens all files in current dir

## Chaining VIM with GIT

You can find the files you have uncommitted with `git ls-files -m`, so if you do `vim -O $(git ls-files -m)`, it will open all changed files in a split view.

You can do the same for opening the last commit, or opening all files modified in this branch. See my aliases below.

## Aliases

Here are some aliases:

```bash
# ~/.bash_aliases
#
# open all dirty files
alias mods='vim -O $(git ls-files -m)'

# open all files modified in last commit in split view
alias amend='vim -O $(git diff-tree --no-commit-id --name-only -r HEAD)'

# open all files modified in current branch in split view
alias amend-branch='vim -O $(git diff --name-only $(git merge-base --fork-point origin/master)..)'
```
