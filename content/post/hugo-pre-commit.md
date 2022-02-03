---
title: "Git pre-commit for Hugo"
date: 2022-02-01T20:12:42Z
draft: false
---


I want to build my site on commit, here's what I tried first:


``` ./git/hooks/pre-commit
set -eux

rm -rf public
hugo
git add public
echo "updated build directory"
```


This worked! But it took some fiddling because I mistakenly set the date of this post in the future.  Apparently you can do that and Hugo won't add the pages for it, so it was running the build command but not actually updating anything.

I started out googling around for a specific Hugo one, and ended up in a rabbit hole of people [setting up servers for 'post-receive' hooks]() and [an NPM package for linting called Husky](https://www.danilucaci.com/blog/how-to-lint-and-test-code-using-git-pre-commit-hooks), and a [python package for pre-commit modules](https://pre-commit.com/).  What I wanted was much simpler, so it was easier to [start from the git docs](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks) and mess with the `pre-commit.sample` and rename to remove `.sample`.