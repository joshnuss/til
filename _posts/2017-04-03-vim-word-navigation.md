---
layout: default
title: Navigating between words in VIM
tags: vim
---

# Navigating between words in VIM

Often find myself navigating vim using word boundaries. I use `w` (**w**ord) to move from word from word, and `e` (**e**nd of word) when I want to go the end of a word. To go back a word, I use `b` (**b**ack).

So changing a word becomes `ce` (**c**hange to the **e**nd of word), deleting a word `de` (**d**elete to the **e**nd of word).

Often I dont want to remove the whole word, just some boundary. For example if you have a long variable name like `some_long_ass_variable_name`, I'd like to remove the first portion.
I can navigate to the underscore boundary with `t_` (**t**ill underscore). To delete until the underscore, I'd do `dt_`, but that would leave `_long_ass_variable_name`. To remove everything including the boundary, use `f` as in `df_`.

## Bonus

The previously closed files path is aliases to `#`, just like to can do `:!echo %` to see the current file's path, you can do `:!echo #` to see the last opened files' path. To re-open last file, simple do `:edit #` or shorten to `:e#`.
