+++
categories = ["Transforming Embedded"]
date = 2020-06-05T22:00:00Z
description = "Do you want to make releases more often? Do you want to be able to bring value to your clients more often? Do you often have to iterate multiple times before your customers gets great value out of your product? If the answers to any of these questions are YES than read on. "
draft = true
image = "/images/how_agile_is_your_product2.jpg"
tags = []
title = "How agile is your product?"
type = "post"

+++
Do you want to make releases more often? Do you want to be able to bring value to your clients more often? Do you often have to iterate multiple times before your customers gets great value out of your product? If the answers to any of these questions are YES than read on.

Our basic premise on why we believe embedded needs to be transformed is that we are entering an age of higher complexity and an increased rate of change. Not only that, the higher complexity makes it less certain that what you bring to market brings value to the market. Therefore, we believe you need to iterate over and over again to learn what brings value. This in itself increases the rate of releases you need to be able to make even further. If you can’t handle this increased rate of change, your competitors will outlearn you.

So, how do you do it? Often, we, and others, talk about Agile – as in [agile teams](https://transformingembedded.sigmatechnology.se/insight-post/how-you-build-awesome-teams/) and [agile processes](https://transformingembedded.sigmatechnology.se/continuous-delivery-guide/) – as the solution. These are necessary indeed, but they are not sufficient. Your product needs to support agility too!

![](/images/agile_triangle_2.png)

To do that your product must both be easy to change and easy to release. I call this non-functional requirement product agility. If your product has high agility, then it is easy and fast for your developers to quickly make the changes needed to bring new value to your customers.

But there is a lot of factors that goes into creating product agility. Here are four examples of product properties that affect product agility.

1\. How you divide your code base will affect how quickly you can make changes to it. If you don’t divide it and you use the same low-level programming language for all development, then everyone but the low-level coders will suffer low productivity because of having to express their problem in a language with bad fit. The control algorithm developers who could have used Simulink will suffer, the machine learning developers who could have used Python will suffer and you bet the GUI developers who could have used HTML and JavaScript will suffer!

2\. If you have a common interface within the system (i.e. a CAN-bus), all changes to that interface will need to be synchronized in a change control board, CCB, for the whole organization and possibly even for clients and servers being developed by 3rd parties. Any architecture, or an interface design, which doesn’t rely on waiting for such a huge CCB to complete their assessment is a win for agility.

3\. If you cannot be sure that a one change hasn’t destroyed functionality everywhere, you will have to test the whole system manually each time you make a local change. This in turn will force you to do big bang integrations in the end of each release. These big bang integrations will take a long time and will limit how many releases you can make per year without suffering too big an overhead.

4\. If you need a new processor with more memory and processor cycles, or new sensors and actuators for each new feature you want to release, it does not matter how awesome Scrum setup your software team has. You are still stuck on a release schedule which includes purchasing, tooling and manufacturing making it impossible to be agile.

But there are many more facets to product agility. I have created a workshop format with which I help my customers assess the product agility of their software. [Download the facilitation guide](https://pages.transformingembedded.com/guide-product-agility-check "Product Agility Check") together with the statements. Though, assessing product agility is just the first step. Improving product agility for a mature product is much harder than adding daily stand-ups to your process, but the outcome is also proportionally bigger. The line and the projects need to prioritize product agility and there needs to be a significant amount of focused work to make an improvement.

Your architects need to set up and enforce best practices for developing new features in your code base which preserves agility. And all developers also need to be taught to value product agility. Otherwise, your code base will degenerate over time. Here, of course, early design reviews and early [code reviews](https://transformingembedded.sigmatechnology.se/insight-post/how-to-implement-code-reviews-in-your-team/ "How to implement code reviews in your team") are a great help to make sure the realized architecture stays true to its intent.

Get the agility in the product right, together with an agile process and the right culture, and you will have the agility needed to bring true value to your customers as fast as possible.