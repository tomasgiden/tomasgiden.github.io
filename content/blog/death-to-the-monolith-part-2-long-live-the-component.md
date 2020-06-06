+++
categories = ["Transforming Embedded"]
date = 2020-06-05T22:00:00Z
description = "Learn how to go from a monolith to a component based architecture."
image = "/images/slicing_and_dicing.jpg"
tags = []
title = "Death to the monolith part 2: Long live the component"
type = "post"

+++
In [part 1](https://www.tomasgiden.com/blog/death-to-the-monolith/ "Death to the Monolith") of this article I talked about the value you get if break up a monolith into individually deliverable components which makes up one value stream individually. In summary, firstly, by delivering the components independently, you will be able to be that much more responsive towards your customers. Secondly, by organizing teams by components, you will get a high amount of accountability in terms of the code base. And thirdly, by having each team being responsible for one value stream, your developers can rise up and take accountability for their own goals.

In this part 2 I am going to talk more about the technical details about these components. First I will cover how to slice the components. Then I will go into how to reduce shared dependencies. And finally I will talk some on how to design the interfaces between the components.

## Slicing and dicing

The first step, as I wrote about in part 1, was to get the business and product folk together to identify the natural components. How do you do that then? There are multiple ways of course but here are some ideas that can make it easier.

1. Look at the features you are delivering. The goal is that a feature only affects an individual component. Try splitting the monolith based on the different features.
2. Look at the different domains for the product. A domain is an area that has its own nomenclature, set of concepts and skills needed. Maybe also different programming languages. For example, predictive maintenance machine learning coded in Python might be a domain. Another one might be motor control coded in C or Simulink.
3. Look at the different business metrics. A product usually tries to solve multiple customer problems which all can be characterized by different metrics. See if you can split the monolith so different components are responsible for the different metrics. Because teams are tied to components you are then giving extremely clear goals for the teams to focus on improving.
4. Look at the hardware architecture. Maybe different microcontrollers in the system have their specific purpose which can translate into different components. Or look at the different sensors and actuators in the system and see if you can divide the responsibility for them into different components. For example, the radar in a car might belong to an Autonomous Drive component.

The above are good examples of how to split a monolith into components. To contrast with this, a bad way would be to split up the monolith based on layers. For example, if you would put the GUI into its own layer, all new features which can be configured and controlled by the user via the GUI would need to update the GUI component. Thus, you cannot deliver the different features independently from each other.

The exception to the rule of not dividing based on layers is the platform. All components need to be built on a common platform serving them with an execution environment, observability, upgradability and so on. This platform can be seen as its own domain (even though it does not give individual value to the customer) and thus a component.

## Component dependencies

When building components, you need to do everything you can to make them as independent and decoupled as possible.

1. Use different database engines for each component or if that is not possible, at least use different tables so as to not create a coupling through a shared database schema.
2. Let different components use different versions of shared libraries to not need to update all components at the same time when one component needs a new version of the library.
3. Don’t put highly functional system specific sensor and actuator drivers into a platform component even if they are shared between multiple components. Rather break them into two parts. Put the low-level configuration and user arbitration in a shared component in the platform. And put the functional parts into a high-level driver which each component can include their own version of.

If you take it upon yourself to figure out all the dependencies you have in your legacy system, you have a big job ahead of you. My recommendation is instead to handle each issue as they pop up. Each time a coupling between two components affects you, take the cost of decoupling them then and there. That way you are not spending your time on removing coupling which in practice never changes and doesn’t pose a problem.

## Interfaces

There is nothing more important than creating good stable interfaces between components. Even though we want all components to be completely independent, this will never happen as long as we are building one product. But by creating components along value streams, what we have done is minimize the need for interfaces. The interfaces that are left though need to be designed meticulously to be stable and minimize the coupling between different components and their changes over time.

1. To create the ability to update components independently you need to make sure that all interfaces support both backwards and forward compatibility.
2. To compensate for decoupling the components, the interfaces must be made really fast with low overhead.
3. If data is needed to pass through multiple components, it needs to be transparent so you don’t need to update the intermediary components when updating the endpoints.

Hard? Yes! Doable? Definitely!

Creating these stable interfaces doesn’t sound very agile but by doing that, you are opening up for massive agility in the components behind the interfaces.

## Freedom!

If you get the components, their common dependencies and their interfaces right you have everything to gain. Within their component each team will have full autonomy and accountability. They can choose themselves the best way they see fit to solve their business goals and achieve purpose. In that they can choose their own tools, abstractions, programming languages, design patterns and so on. And they can release whenever they have new value and the right quality.

If there is anything that is known about autonomy it is that it is the basis for creating engagement in teams. And engagement together with accountability are the cornerstones of being able to realize goals and purpose. And what else than that can we ask of our teams?

This article was also published on Transforming Embedded [here](https://transformingembedded.sigmatechnology.se/insight-post/adaptability-is-eating-agiles-lunch/ "Adaptability is eating Agile's lunch").