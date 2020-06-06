+++
categories = ["Transforming embedded"]
date = 2020-06-05T22:00:00Z
description = "Robust is good but not good enough. Learn what antifragile products are and how to build them."
image = "/images/anti_fragile.png"
tags = []
title = "How to build antifragile products"
type = ""

+++
A few years back Nassim Nicholas Taleb came out with a book called [Antifragile](https://www.amazon.com/Antifragile-Things-that-Gain-Disorder-ebook/dp/B009K6DKTS). And recently, I listened to a [great podcast](https://open.spotify.com/episode/5JslzRu8oM12HOTBAosxjX?si=38PSh2--TJemgAAqTsEOkA) where Barry O’Reilly took Talebs ideas and applied them on software architecture. Both inspired me to write this blogpost. Here I will expand on their ideas and explore how we can build antifragile product development systems. I have actually touched upon this subject before I knew about the term antifragility when I wrote about [How Agile Is Your Product](https://www.tomasgiden.com/blog/how-agile-is-your-product/ "How agile is your product") and [Product Agility Check](https://transformingembedded.sigmatechnology.se/insight-post/product-agility-check/). This one takes it even further by discussing how to figure out what you need to do in your system.

### What is antifragility

We first need to define fragility and antifragility. How about if you drop your phone on the ground? Will the phone be better or worse? Most likely it will be worse off (mine has a broken screen right now). It will never be better. This what we call a fragile system.

But how about when you go out running and really push yourself? Directly after the run you will be worse off, but a few days later your body will have adapted to the stress of the run so next time you are out running it will be easier. Your body has become better. We call this an antifragile system.

### Do antifragile products really exist?

So how about antifragile products? Will your software and hardware become better if you put it under the stressors of a lot of users, strange customer environments or changing business requirements? If your product does not include advanced unsupervised machine learning, most likely it will be worse off. So if you just look at your product, it is clearly fragile. In the best of worlds, it is robust and resilient, but it is not antifragile.

To move into the antifragile domain you need to consider the development organisation as a part of the system, and not just the product. With humans in the loop we have an adaptive system; you put the product under stress by early testing or deployment, you discover bugs and fix them or you add features to adapt to changing customer needs. Every time your product becomes better.

To be able to do this there are some preconditions.

1. You work in iterations, always testing and potentially deploying every iteration.
2. You must have built observability into your product and your customer relationship processes to see what stresses your product.
3. You must have tight feedback loops back to the developers.
4. You must have the business agility and development agility to be able to respond to stressors.
5. Your product must be easily upgradable.
6. Your customers must be able to accept upgrades.

These are all necessary, but they are not enough.

### Limits of antifragility

There is a limit to the changes we can do to our product. As everyone in the product development business knows, eventually our product cannot respond to the changes we need to make to it and we need to start from scratch. Why is that?

The reason is that we have not made the product flexible in the right dimensions and thus the change needed would be just too expensive to handle. When we built the system back in the days, we probably did it based on known requirements. But the problem with requirements is that they are based on the flawed assumption that we can predict the future. In a complex world, we just cannot.

In fact, asking someone to set up requirements for a system is close to bullying. We are forcing them to accept the responsibility for unknown future events by creating a static set of requirements. And when unpredicted things start happening, as they will, we have our back free by just pointing towards the requirement that someone else defined. Good for us personally, but not for our business.

Instead of requirements we need to start talking about what stresses the system. I call these stressors.

### Stressors

A stressor is something that pushes our product / development system outside its comfort zone. For example, if a competitor decreases their price that is a great stressor for any development organisation. Or looking deeper, what happens if we discover that a control algorithm needs to run at a much higher frequency because of new components? Or what about if we get many more users than expected? And so on.

These stressors are not detailed requirements and are a lot more fuzzy and general. We definitely don’t need to know all the details.

### How to make our product systems more antifragile

What we start with it to list all different kinds of stressors that can affect our system no matter the probability. Then we figure out how our system needs to be adapted to handle them.

We cannot predict all stressors that are going to affect our system in the future nor their probability because of the complex environment but that is okay because that is not the point.

What we will notice is that the same adaptations will be the solution to multiple unrelated stressors. So for 50 different stressors we might come up with 10-20 different ways our system needs to be adapted. And this we will continue until the number of adaptations do not increase anymore, even if we add new stressors.

Now we can divide the adaptations into a number of different categories.

The **first** category are those that are close free to implement. It can be to divide a component into two or moving a function between two components. These we just do.

The **second** category are those that do actually cost a lot of money from the start. For example, should we set up factories in multiple countries, use cloud infrastructure at multiple providers or build in massive redundancy into the software and hardware. For these adaptations we need to fall back to risk management and balance the cost versus the risk before deciding what to do.

Implementing these two first categories of adaptations will increase the robustness of our product. This is great in a complex world. But by definition it is not antifragility. To become antifragile we need to look at category three and four.

The **third** category are those that are costly to implement but where we can do cheap preparations in the product to not paint ourselves into a corner. In embedded systems, adding a software update system is one such preparation. Or divide your monolith into multiple components where you only need to replace one component when the system comes under a stress instead of replacing everything.

The **fourth** category are adaptations to the organisation to be able to react to stressors. For example top down control and strict processes for people to follow are very fragile to unknown events. Bottom up, mission driven organisations are much more antifragile since they rely on the adaptability of individuals. Different agile practices and DevOps are other very relevant adaptions.

With the third category we build up the adaptability of our product, and with the four we build up the organisational support to be able to do the adaptations. Now we can become truly antifragile.

We can also talk about a **fifth** category of product strategy adaptations though it is slightly out of scope of this article. If we only have one product and one customer, we become very fragile. If we for example had one stable main product in a large stable market and then several small high risk products experiments in emerging markets with large possible upsides (a so called barbell strategy) we can also become antifragile in this domain.

### Wrapping up

Now we have built in a number of adaptations to both our product and our organisation to a number of future possible stressors. If the stressors that lay behind these adaptations show up, then our system are already robust and antifragile enough to handle them. That is great, but it gets even better.

Not only are we protected against these stressors, we are also protected against unknown stressors we didn’t even consider. The reason for this is, as we talked about before, is that multiple stressors share the same adaptations in the system. So by adapting for a known stressor, we have actually adapted for a number of other unknown stressors as well.

So by these simple measures we have actually become much more robust and antifragile than it shows. And isn’t that awesome!

If you want to know some of the most general adaptations you can perform in an embedded system go checkout my [Product Agility Check](https://transformingembedded.sigmatechnology.se/insight-post/product-agility-check/). It is a free workshop format with printable cards you can use to see what capabilities you have to adapt your embedded system in the face of changes.

_This article was also published on Transforming Embedded_ [_here_](https://transformingembedded.sigmatechnology.se/insight-post/how-to-build-antifragile-products/ "How to build antifragile products")_._