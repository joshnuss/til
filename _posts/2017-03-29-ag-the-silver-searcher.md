---
layout: default
title: AG - The Silver Searcher
tags: ag, shell, utilities
---

# AG is pretty rad

One of the most indispensible tools in my toolbox is `ag`. It is really efficient at splunking through tons of files super fast.

It can anwser questions like:

- Where is this function used
- Which files do something similar
- Which files are named like this
- Does anything match this regular expression

# Tips

## Before/After

By default `ag` shows just the matches line, often you want to see lines before and after. `ag` has the options `-B`/`--before` or `-A`/`--after` for that.

```bash
# show 5 lines before and 5 lines after
ag all-the-things -A 5 -B 5
```

# Find filename by pattern

If you want to find all files where the name matches a pattern, you can use the `-g` option.

```bash
# find all files that have the word "reservation"
$ ag -g reservation
app/models/reservation.rb
spec/models/reservation_spec.rb
```

# Match based on filename

If you wanted to find something in only certain types of files, you can use `-G`. It's similar to the lowercase `-g`, except it match inside the file and match the file name.

```bash
# find instances of "city" where the filename contains the word "model"
$ ag city -G model
app/models/hotel.rb
22: city: "New York"
35: destination.city != source.city
test/models/reservation.rb
13: city = "Montreal"
```
