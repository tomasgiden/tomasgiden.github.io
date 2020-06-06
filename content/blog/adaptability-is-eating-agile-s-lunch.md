+++
categories = ["Transforming Embedded"]
date = 2020-06-05T22:00:00Z
description = "Have your development department been bogged down in making features and adaptions for single customers? Have you then adopted agile to become faster at reacting to customer’s changing needs? Great! Or is it? Maybe there is another way?"
image = "/images/elasticity.jpg"
tags = []
title = "Adaptability is eating Agile's lunch"
type = "post"

+++
Have your development department been bogged down in making features and adaptions for single customers? Have you then adopted agile to become faster at reacting to customer’s changing needs? Great! Or is it? Maybe there is another way?

We are living in a world which is becoming more and more complex. We know that we cannot anticipate our customers future needs. And through the last decades of agile thinking we have all learned that the way to respond to this is by working iteratively. In the best organisations they are learned to optimise the cycle time from customer need, through their development organisation, to delivery and finally to when the need is solved. (Though in most organisations, agile has sadly become only an optimisation of the time of a feature, useful or not, through the development department.)

Optimising your organisation for this is great and you should really, really do it. But what if I tell you there is something even better complementing it? Would you believe me? What could be better than minimising the time that it takes for us to solve our customers problems?

### Adaptability

What would be even better is if our customers could solve their own problems without even being in touch with us. I’m talking about having a product with an adaptability and extendibility to unforeseen needs. Not from the developer’s point of view as I’ve talked about in my articles on [antifragility](https://transformingembedded.sigmatechnology.se/insight-post/how-to-build-antifragile-products/) and [product agility](https://transformingembedded.sigmatechnology.se/insight-post/how-agile-is-your-product/) but from the user’s point of views.

Let me take Microsoft Excel as an example to illustrate what I’m talking about.

When you start Excel you are shown multiple sheets with endless rows and columns. You can resize these and edit any of them with text and numbers. You can use the readymade functions (SUM, MAX etc) to easily do calculations. When you as a user have learned how to use single functions, you can add multiple functions together to create much more complex functionality. If this is not enough you can go over to Visual Basic for Applications (VBA) and similar scripting solutions. Basically, even if your use case changes, it is very seldom you must call Microsoft to have them update Excel. The thought of it is almost laughable.

### **Embedded systems**

But I hear what you are thinking, Excel is one thing but we’re in the embedded business and that is something completely different. And that is true. But there is a reason we call this site Transforming Embedded. So, let me give a few examples how adaptability could look like in an embedded system.

#### **1. Adaptable GUI**

Many embedded systems of today has some kind of graphical user interface, either local or remote. It is very important here to make these interfaces simple and intuitive. We cannot afford to show all complexity up front; the threshold for a new user will become way too high. Instead what we need to do is onboard our users gradually by introducing them to complexity when they need it.

To do that, we can have different modes based on usage and we can let the user compose their own modes that fits their needs by adding and removing controls and information. Maybe even use artificial intelligence to inform the user that by tweaking some obscure parameter they can gain even more value of the system.

(This is not only important from an adaptability perspective, it is also paramount if you want to go all digital and adopt a license, pay-per-use or an outcome based business model.)

In the GUI we can even expose some of the internal logic of the device and allow editing of it. We can do that either through exposing user editable scripts or by allowing the user to ”rewire” the system through, for example, [a node based interface](https://nodered.org/).

#### **2. Open open-ended interface**

Many embedded systems can gain by interaction with many other embedded systems. Of course, you can build specific integrations for each such system but the number of such integrations that needs to be built scales quadratically with the number of systems (each system has an integrations with n other systems => O(n^2) integrations). This is not sustainable. Especially if you cannot anticipate which other systems you need to integrate with.

Instead you need to focus on making open interfaces. It could be mechanical hardware interfaces but since software is eating the world, we are more often talking about software application programming interfaces (API). These needs to be open as in available for all customers and 3rd party integrators to use. To do that they need to build with standards components from the physical interface (mechanical & electrical) to the application interface. For example, from Ethernet to TCP/IP to MQTT or HTTP to JSON to the application data model itself. Or think USB/USB-drivers. What is great about standards is that there are so many to choose from, just please let go of Modbus and similar, they are not up to most tasks of the future.

Also consider common integration plattforms such as [If This Then That](https://ifttt.com/) and similar which can act as a hub between a number different services and devices.

It is not enough that interfaces are open, they also need to be open-ended as in that they are not designed for a specific task. If an action, events or data can be accessed, let it be, no matter if you see the use for it now or not. Though always mindful of safety, security and integrity of course.

With this in place, it is simple with low effort for integrators to build modules bridging the specific systems when the need shows up.

#### **3. Apps and SDKs**

There is only so much interaction that can be done through an external API. Depending on embedded system you might get issues with latency, bandwidth and even getting physical space for cables and external devices.

To get past these issues, look at the model of today’s cell phones. When you buy one today it has several preloaded applications from Apple or Google. But they both realised early that they wouldn’t have the ability to build applications for all different users current or future needs. Therefore, they set up App Stores where 3rd party developers can publish their apps and you as a user can download them to your device.

What if you could build in the ability for a customer or 3rd party to add their own apps to your device? Then customers and integrators can start to really change your product to fit their changing use cases.

If you even code your own applications through the same internal APIs and with the same Software Development Kit (SDK) you know that you will not have any artificial limitations on what an app can do (more than you add yourself to artificially limit functionality because of safety reasons) and that integrating with your product will be painless.

If your product is popular enough you can even start your own app store and build an eco-system around your product consisting of multiple 3rd party integrators.

### **Conclusions**

No matter how you build adaptability and extendibility into your products (and I’m sure there are many more ways than those I listed above), there are a three things to consider.

1. Mind the user. An embedded system has multiple different users such as operators, integrators, analysts, IT support etc. Mind all their needs for adaptability and extendibility.
2. Adapting should not be a separate process. There should be an easy learning curve for the specific user from using your system to making small adaptions and on to bigger changes.
3. Make it fun! The user should have fun continuously improving their own life. That’s how you build a product people will love.

### **Pots of gold**

If you do all this, there are two pots of gold waiting for you. The first one is getting your customers hooked on your product. When they have adapted a product to perfectly fit their use case and have lovingly invested their time and effort to do it, they will not be inclined to change it out for something else.

The second one is letting your development department off the hook for minor adaptions needed for single customers. All adaptions for every single customer can really grind the business and product development to a halt without you even realising it. You are releasing code every day but the value for all but that single customer needing that unique adaptation is very low. With that effort outsourced, you can start focusing at the big picture, your vision and how you can bring value to all your customers.

Good luck building a product your users will love to make theirs! And good luck finding your pots of gold.

This article was also published on Transforming Embedded [here](https://transformingembedded.sigmatechnology.se/insight-post/adaptability-is-eating-agiles-lunch/ "Adaptability is eating Agile's lunch").