---
title: "Git pre-push"
date: 2022-02-02T20:12:42Z
draft: false
---

I want to build my site on commit, here's what I tried first:
``` .git/pre-commit
set -eux

rm -rf public
hugo
git add public
echo "updated build directory"
```