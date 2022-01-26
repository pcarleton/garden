---
title: "Render"
date: 2022-01-25T20:51:41Z
draft: false
---

TODO: get this badboy on Render.com

1. Render.com
2. Register (with Github)
   a. (Act on your behalf): looks like it will only be able to do that on resources I grant the app access to
3. New Static Site
4. Push this thing to Github
  a. looks like it needs to be public, but I guess that's the point anyway
    i. This got me thinking about how my github might actually get more traffic from people I know versus my blog which is exclusively strangers afaict.
  b. Seems like it _should_ be able to be private, says "It looks like we don't have access to your repo" in the logs, so I could grant it access.
5. Go back and actually add the public assets
6. Follow the [namecheap instructions](https://render.com/docs/configure-namecheap-dns)
7. Voila! It worked.

Overall it took about 20 minutes.

Some things I might do to make it smoother:
- a pre-push hook that does `rm -rf ./public && hugo`