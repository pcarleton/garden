---
title: "Thoughts on Dall-e"
date: 2022-07-07T06:46:22+01:00
draft: false
---


# What makes it fun?

I've been playing around with the mini-dalle's on my home computer (after wrestling with CUDA and WSL and jax, and then over engineering a tailscale setup with a sqlite queue so I could submit ideas from my phone).

It can be quite fun and quite novel.  With the "non-dalle-2" models, it can feel a little like panning for gold, or digging through a trash dump, but a trash dump of fairly interesting looking garbage.

It still feels like an accomplishment when you find something good.  You "struck gold" in a sense. It's not the same level of accomplishment you feel if you had drawn the thing yourself.  You're painstakingly honing your skill, and then feeling the physical niceness of a pencil in your hand, and the paper against your palm.  The "done enough" decision is still there (you could keep submitting prompts forever), but you don't get better at it in the same way.

Things that worked really well for one thing don't work well for another. 

Maybe I'm talking myself into this is a skill, but a very different kind of skill.  And one that feels very shallow, or like it could evaporate as soon as a new model comes out.  Who knows whether the embeddings in the new model react as well to your quirky semantic tricks, or have as good of knowledge of what a minion looks like in different poses.


One comparison that I think captures the fun of it is comparing it to a google image search.  For very plain prompts, you could do a google image search, and get a stock photo back, or a painting of exactly what you said. And it would probably be way better than what a mini-dalle could come up with.

When you search something where there's only 1 search result, or no results is where things get interesting.  The "CCTV footage" is one my favorites for this.  There's something really funny about seeing a blurry image of Yoda walking around a 7-eleven.  It's a combination of being extremely novel (like it's actually Yoda sized, not a full-sized human dressed up as Yoda), it takes advantage of blurriness being okay, and it's something someone would need to put a lot of effort in to produce themselves.

{{< figure src="images/yoda.jpg" title="cctv footage of Yoda robbing a liquor store, photo credit: kuprel on github" link="https://replicate.com/kuprel/min-dalle/examples">}}


# Cherry picking

In some articles, and twitter threads, some folks have called foul on "cherry picking".  The gist is that because you might have had to generate 20 images in order to find that one amazing one, that it showcases a huge limitation of the model.

On the one hand, that's fair.  If you're only seeing the cherry-picked, you might think that these models are much more capable than they are.  But on the other hand... I don't think it hides that much of their capability.  I guess it means that it takes about 20x as long as you might expect and still requires a "human neural net" at the final stage to pick a winner.  But I guess I take that as a given after generating so much garbage with the weaker models, so I don't have any problem with cherry-picking.  I'm here for Kermit in the matrix, don't bog me down with the 19 other crappier versions of that prompt, I want to move on to see him in the Sopranos.

I guess my take-away is that, "yes" we haven't fully nailed down a generilizable understanding of human aesthetic preferences, but I guess I didn't really think we were there anyway. Needing a human in the loop to iterate doesn't seem like a huge "man behind the curtain" situation that some make it out to be. 

# Homegrown

The dalle-mini situation is very concisely summarized in this meme:


I found it interesting that most of the diaspora (10$ word) of ML tools, and hosting platforms.  dalle-flow had a whole framework it was using called Dina.  There's replicate which somehow hosts the mini-dalle at extremely impressive speeds for free.  And there's Colab, with its free and paid tier.

After wrestling with my own graphics card and going to great lengths to get it to be able to queue up a bunch of runs, and then still finding my VRAM lacking for the biggest models, I understand while all the researchers and ML community assume you're running in one of these platforms.  It's pretty impractical to get the resources to do these things without them.

However, the amount of progress that mini-dalle made calls some of that into question.  It seems like there's a wide spectrum of optimizations you could do to in order for these models to be more widely deployable, and potentially higher quality.

Whether that's desirable is an interesting question.

# Style & What is Art

One other concern I saw (citation needed), is that this will put artists out of work.  Or people  will lost interest in art created by people.  An example was about craftsmanship in clothes.  The line of thinking is that once a bunch of automation was able to create super cheap clothes, then there was a much smaller market for people making high quality clothes since you could get a similar quality for cheaper.

That's probably a valid concern! The place that's probably most at risk is illustrators on sites like fiverr.  Some times you want an image for like $50, and you hire someone to draw it.  If it's much quicker to have an AI generate one (maybe it's for a blog, or for a game or something and your budget is tight), you'll likely make do with an AI one even if it has some weird artifacts in it.

Something I didn't expect is that generating a bunch of these made me appreciate human created art more.  For instance, I did not know the word "ukiyo-e" before trying to generate a bunch of images.  I find myself more excited to go to an art museum and learn about which art work is which styles.  Will I then try to put elmo or wall-e in the style? Probably yes.  Does that somehow make my interest "less than" pre-dall-e? I had rougly zero idea what different art styles meant before, so I think it's a net positive.

Here's a bunch of different styles of darth vader and Yoda:

{{< figure src="images/darth vader and yoda as a one line drawing_1.jpeg" title="darth vader and yoda as a one line drawing">}}

{{< figure src="images/darth vader and yoda in the style of ukiyo-e_6.jpeg" title="darth vader and yoda in the style of ukiyo-e">}}

{{< figure src="images/painting of darth vader and yoda by Monet_4.jpeg" title="painting of darth vader and yoda by Monet">}}



# Different strokes

Also, I find technical drawings to be really appealing.  For instance, I have this picture from an old German textbook in my office:

TODO.

Trying to get Dall-e to generate these pictures ends up looking like this:


Some of these are very cool to look at, but they obviously aren't as precise.  In hindsight, it is pretty obvious these drawings wouldn't have accurate orbital trajectories, and they do still look cool.  It highlights the "shallow" nature of the art though.  If I show a picture of the german text book, you can explain the back story of what those ellipses mean (well, theoretically I could, I'm not actually sure!), whereas the ellipses in these pictures don't have the same precision or purpose behind them.  The best you can do is say what prompt you put in, and maybe guess at where some of the source material came from (oh that looks like Kepler's 1st law!)


# Bias / Safety

Some half formed thoughts on bias & safety

- Biggest concern for me: fake news / disinformation
- Conflicting thoughts: bias in the models
- Acknowledgement: it's biased "in my favor"
- Is it the model's job to correct "the internet" it's reflecting?
- Maybe not, but maybe if your stated goal is general AI, and you don't "correct" it, then this super powerful tool will also be biased.
- Similar to climate change, existing incentives don't work to fix the problem.  biased models are cheaper to generate since they don't account for the cost
- Need some incentive to invest heavily into new technical improvements to "fix" the bias of the models
- that incentive is _probably_ not shaming on Twitter, but bringing it up and talking about it is  better than pretending it will just go away (similar to climate change)
- AI co's would probably do well to start thinking of how they want to be regulated before they get some very ill-informed regulation that makes things worse
- 

# More funny pictures


{{< figure src="images/elmo_cctv.jpeg" title="cctv footage of elmo break dancing in a convenince storee" >}}

{{< figure src="images/queen_elizabeth_cctv.jpeg" title="cctv footage of queen elizabeth in a convenince store" >}}