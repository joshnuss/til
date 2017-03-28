---
layout: default
title: Create a TIL website
tags: TIL, Jekyll, Static website
---

# Create a "Today I Learned" Website

It's super **easy** to setup using Jekyll.

Plus, you can host it on GitHub for **free**.

## Setup the repository

```bash
# Create folder
mkdir til

# Navigate to folder
cd til

# Initialize repository
git init

# Create a README
echo "# TIL of $(whoami)" > README.md

# Create Gemfile
echo -e "source 'https://rubygems.org'\ngem 'github-pages', group: :jekyll_plugins" > Gemfile

# Install dependencies
bundle

# Stage files for commit
git add .

# Save changes to repository
git commit -m 'Initial commit'

# Create repository on GitHub
hub create

# Push to GitHub
git push

# Open in browser
hub browse
```

## Configure GitHub

1) Open the repository in GitHub (shortcut: `hub browse`)

2) Click **Settings/GitHub Pages**

3) Change the source to `Master Branch`, and then click `Choose a Theme`

4) GitHub will update the `_config.yml`, so pull the latest `git pull origin master`

# Setup your Homepage

Create an `index.html`, with:

```markdown
---
layout: default
title: Welcome!
---
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
```

## Create a your first post

Create a `_posts/2017-1-1-title-of-post.md`, with:

```markdown
---
layout: default
title: Hello World!
tags: til, github
---

# Hello World

it works!!!
```

## Preview your site

To run in development mode:

```bash
bundle exec jekyll serve --baseurl /til
```

Navigate to [http://127.0.0.1:4000/til/](http://127.0.0.1:4000/til/)

## Deploy

```bash
git add _posts
git add index.md
git push
```

You can view your website at: [https://YOURUSERNAME.github.io/til](https://YOURUSERNAME.github.io/til)
