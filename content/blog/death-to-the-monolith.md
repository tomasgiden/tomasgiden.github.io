+++
categories = ["Transforming Embedded"]
date = 2020-06-05T22:00:00Z
description = "A monolithic is a complex system which is hard to release. But complex system need frequent feedback to create customer value. Thus, the monolith must die."
image = "/images/pineapple_knife.jpg"
tags = []
title = "Death to the Monolith"
type = "post"

+++
More often than not, I am consulting for clients developing big embedded systems. Building big systems is hard. Building big embedded systems is harder. When these organizations try to be agile about their way of working, they often run up against limits for agility in their product. Because of this, I previously wrote an overview about this called [How agile is your product](https://transformingembedded.sigmatechnology.se/insight-post/how-agile-is-your-product/). I have also created a workshop facilitation guide called [Product Agility Check](https://transformingembedded.sigmatechnology.se/insight-post/product-agility-check/) which you can run within your organization yourself to figure out what exactly is limiting your product.

In this article, I am exploring my thoughts about one of the limiting factors in many products, which is when they are built as a monolith. That doesn’t apply to me, you might say, counting all the different parts your product is made up of. But then let me ask you a question, can you release these different parts separately? If you can’t, then from a release standpoint at least, what you have is a monolith. And this is a monolith I want to kill!

## Why the monolith must die

The reason the monolith must die is that a big system is a complex system. And in a complex system we need frequent releases to get the feedback needed to make sure we create customer value. But the problem here is that the larger system we have, the harder it is to make releases. Secondly, you get coordination overhead with lots of teams talking to each other (or even worse – not talking to each other!). And trying to get all these teams to the finish line on the same time is not trivial. Therefore, to minimize this overhead, though in a suboptimal way, projects are often very long.

> You’re damned if you do, damned if you don’t.

It is also hard to develop in a big monolith. As a developer, there are no bound to what you need to understand to get started coding, and often you need to be aware of what every other developer is doing. On top of this, shared responsibility for a big codebase is hard. Shared responsibility can work in a team but a whole organization cannot be a team. The result becomes that no one is taking responsibility for the codebase leading to technical debt creeping up on you, no matter the best intentions of each developer. Any organization trying to develop something large needs to divide responsibility in some way. Development teams can either be divided into component teams or feature teams. But here you are damned either way.

Component teams work on a specific part of the monolith, like the GUI, but to develop a feature which spans multiple components you need to involve multiple teams creating lots of handovers. And when developing complex features, handovers kills the throughput and invites misunderstands leading to rework.

Therefore, the usual solution is to set up cross functional feature teams which has the knowledge how to develop a whole feature themselves. However, put highly trained developers and engineers into feature teams working with features given to them by a business division, not truly understanding the why behind them, and just being asked to be code factory workers. Lather – Rinse – Repeat. That this does not spark joy, create engagement and enforces accountability is given. It will be quite efficient in the beginning but with a lack of component responsibility, technical debt will, over time, creep up on you and hit you and your efficiency like a ton of bricks.

## A rosier world

Let me paint you another rosier picture. What if you build vertical teams containing everyone needed to deliver value to the customer in a very specific area from business to development? And what if these teams could deliver this value totally independently from all the other teams?

Each team would be able to release more often because of the radical minimized coordination needed. The feedback cycles would be rapid and strong.

From a customer standpoint there would be a plethora of releases coming each year, but each individual customer would not need to update more often than before. They update only when new functionality giving them value show up in a release. The difference for them is rather that they don’t need to wait for ‘their’ feature to be synchronized into a release with 10 other features they couldn’t care less about.

And with clear goals and vertical team structure creating a self managed empowered team, employee engagement and accountability would be a mile higher than before. A team would be both a feature and a component team simultaneously; reaping the benefits of both and the downsides of neither.

Also, the individual developer no longer needs to understand the whole system but only her own value stream and therefore becomes productive much faster.

Can you feel it? Is this where you would like to be?

## Descaling by decoupling

The answer in how to get there is not some ‘agile’ scaling framework. The answer instead lies in descaling the system by decoupling the system.

What we need to do is to break apart the monolith into separate components where each component is so decoupled from the others that they all can be released independently. This might sound easy, but the devil is in the details.

To do this you need both product people and business people cooperating closely in defining components which both can represent customer value flows and which can be released separately in to code base. Between the components, clear, well documented and stable interfaces become incredibly important.

Since most components will be representing customer value flows, many end to end tests can be done on a component level. However, the components are still running in the same physical system and there will be interaction between them through the interfaces. Therefore, you still need to do some complete system planning and testing (and here an ‘agile’ scaling framework will give some value). But compared to a monolith, the amount of will shrink radically.

One of the few good thing with a big monolith is that creating a release package is trivial. Just take all code, compile it together and there you have it. When splitting up the monolith into individual components, some of the complexity is shifted to building a release from these components. So if you have a continuous delivery pipeline, its architecture will be more complex

## Getting started

Even if you buy the value you can get from breaking your monolith into separately deliverable components, when you stand there with your monolith in front of you, it is not easy to know how to get started. You cannot stop delivering value for half a year just to refactor the whole system into individually releasable components.

Instead, what you need to do is to create the first value stream component team and then let them slice of their components from the monolith. When that is split off and have started producing customer value, you can continue with the next team and the next component. At no point in time during the killing of the monolith are there more than the developers in one component which are not producing customer value.

## Conclusion

I hope I have inspired you to descale your system and create true agile delivery teams even when you are facing a large monolithic embedded system. The benefits of true agility are sorely needed in the digitalized world of today where complexity and speed are invariably increasing.

Now it is your turn. What business value could you realize if you had the ability to deliver different value streams just in time? And what would be the first step for you to get started?

If you want to learn more about the nitty gritty technical details on building these components, continue reading about it in [Death to the Monolith part 2: Long live the component!](https://transformingembedded.sigmatechnology.se/insight-post/death-to-the-mon%E2%80%A6ve-the-component/ "Death to the Monolith part 2: Long live the component!"). In it, I will go into how you should think when slicing the components, how to limit the dependencies between the components and how to build the interfaces between them.

If you have questions or feedback, just send me a message.

This article was also published on Transforming Embedded [here](https://transformingembedded.sigmatechnology.se/insight-post/death-to-the-monolith/ "Death to the Monolith").