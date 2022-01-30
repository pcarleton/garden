---
title: "Hugo"
date: 2022-01-30T20:13:27Z
draft: false
---


- Switching ports fixed a connection problem for some reason... 
- the default one through `sudo apt-get install hugo` was from 2020, so intalled from source instead.


- Render: doesn't seem to be picking up my commits as pulls.
    - Just kidding it worked this time.


- All my links are to "example.com" -- uhoh. Maybe I need to re-install the theme?
  - Problem was the "baseUrl" in the config.toml
  - New issue: clicking name in the top right doesn't change the URL (i.e. doesn't take you "home")