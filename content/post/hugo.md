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


## Images

I first put things in a folder called "images" that was under `./resources/_gen/images` -- but that wasn't right.  I then moved it up to `./resources/images` and tried doing some things I saw under [Image Processing](https://gohugo.io/content-management/image-processing/) in the docs, like this:

```
{{- $image := resources.Get "images/logo.jpg" -}}
```

But this just rendered the text itself to the page, not even the path or an error or anything.  I then realized the issue was that I was just setting a variable (and maybe not in the right place?)

In any event, I ended up using a "page bundle", so my directory looked like:

```
e-notes/
├── images
│   ├── electronic_notes_photo.jpg
│   ├── lamy_from_pen.png
│   ├── neo_paper_005.jpg
│   └── scan_image.pdf
└── index.md
```

and then I just used image tags like `![alt text here](/images/lamy_from_pen.png)`.