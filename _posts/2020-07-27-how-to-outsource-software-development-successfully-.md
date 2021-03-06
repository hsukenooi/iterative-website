---
layout: post
title:  "How to Outsource Software Development Successfully"
date:   2020-07-27
author: "Hsu Han Ooi"
categories: blog 
excerpt: "Working with outsourced engineers can either be a cost-effective, time-saving solution or a nightmare of communications and an expensive source of bugs/technical debt. To increase the probability of having a successful engagement, I've compiled a three step guide below." 
---

Working with outsourced engineers can either be a cost-effective, time-saving solution or a nightmare of communications and an expensive source of bugs/technical debt. To increase the probability of having a successful engagement, I've compiled a three step guide below.

1. While it's tempting to start a new project by just reaching out to outsourcing companies, you should always start by defining a set of requirements for the project before you talk to any companies.
2. Then we'll look at different ways to source companies that fit those requirements to talk to.
3. Finally we'll go over a list of topics that will be helpful in evaluating the different outsourcing companies and take a brief look into pricing. 

## Requirements

Before talking to any development shops I highly recommend figuring out the type of engagement, the tech stack, and the timezones you're willing to work with BEFORE you approach any outsourcing companies. 

- Matching the type of engagement with your needs will speed up the process and increase the probability of success.
- The tech stack you choose is an important long term decision that will affect hiring, development speed, reliability of your product, and much more. It's a decision you should make before being influenced by an outsourced company who isn't aligned with your company goals.
- Moving fast with engineering is synonymous with communicating quickly and effectively. If you have to wait 8-12 hours to ask a question or receive a response that will slow down your company significantly which is why working in timezones which overlap with your working hours is absolutely important.

### **Types of Engagement**

Generally, I've seen 3 models of outsourcing which are described in more detail below. You can ask which model they usually work with by asking about current clients and how they currently engage with them.

**Scale an existing team**

This is generally the most successful type of engagement and if you have engineers already, you should always choose this. Have your engineers vet and coach incoming outsourced engineers. Usually this looks like in-house engineers doing interviews, code reviews, and architecture assessments with the outsourced engineers for 1-3 months (depending on the seniority) before allowing the outsourced engineers move onto their own projects. Those projects should then be well-defined, have a written spec, and should be set up so the outsourced engineer can succeed. I have a golden rule with engineering that the first project should always be successful to create momentum and show the engineer what it takes to be successful. Failure in the first project is usually due to not enough onboarding, ill-defined requirements, or poor time estimation and is the fault of the onboarding team.

- Pros
    - Higher engineering work quality (less technical debt, simpler architectures, etc.) in the long term.
    - Generally cheapest engagement type.
    - Highest probability of a successful engagement.
- Cons
    - Increased overhead for existing engineers.
    - May have to interview multiple engineers to find the right match.
    - Must have an existing engineering team preferably with a tech lead.

**Building a product**

If you don't have an engineering team, you'll generally be looking for the outsourced company to create the first version of a product. This can be successful but I generally see two issues with this engagement in almost every project. These make projects come in over time and budget. 

1. **Code Quality -** At a previous job, we had an outsourced company build the first version of a product. Almost a year later we'd take the development in-house (which is when I was hired) and the first thing we noticed was the amount of tech debt we inherited. Testing coverage extremely low or nonexistent, 3 different systems of configuration management, 2 different analytics platforms, just to name a few. This is the #1 reason if you have engineers already you should always scale an existing team. Without oversight and proper leadership it's easy to build up technical debt that can haunt you later on.
2. **Scope Creep -** When unintended features are built, that is scope creep. This generally happens due to miscommunication or lack of clarity in the product. It happens often in this type of engagement because outsourced companies engineering estimation is overly optimistic. To help with this try to create a written product spec before you meet with the company. I won't go over how to create a product spec here but make sure it includes milestones, a timeline, and what features can be left for the future.

A strong program/product manager to manage the project on your side can help mitigate these issues. Sometimes when you go with this type of engagement the outsourced company will provide a PM for you. I don't recommend relying on their PM as the goals of the project can start to drift apart. As the development team gets behind their PM will start to make decisions just to hit milestones and get paid. This may not be in the interest of the startup if quality is sacrificed. Creating an extra layer between engineers also creates another layer for miscommunication.

Below are some of the pros and cons of using the building a product engagement type.

- Pros
    - Works without having an existing engineering team.
    - Short-term will give you the biggest productivity increase.
    - Can be successful with strong program/product management skills.
- Cons
    - Often comes in over budget and over time.
    - Usually can provide everything from Design/UX to engineering. Hard to be good at everything so some divisions are much better than others.
    - Oftentimes comes with a lot of hidden technical debt to be discovered later.

**Manual Testing and Quality Assurance**

In the past I've also worked on a startup where we contracted with an outsourcing company to handle manual testing and QA. This type of engagement doesn't work and I'd never recommend anyone to use it. I learned two valuable lessons from this experience.

1. **Manual testing doesn't scale -** Manual testing is a crutch that gets more expensive over time. As you build more features, manual testing takes longer, is more expensive, and becomes more error prone. 
2. **Testing illusion -** It gives developers the illusion that testing isn't there job. 10+ years of development later and I can firmly tell you that testing is every developers job.

If you absolutely must go this route, stay away from manual testing. When you focus on automated tests, define a narrow scope that you want them to focus on. The larger the surface area of focus the more false positives. False positives lead to desensitization and ultimately getting ignored which doesn't provide any value. If you focus on the core user experience and build simple unit and integration tests it can be a successful engagement.

Below are some of the pros and cons of using the manual testing and QA engagement type.

- Pros
    - Generally more testing leads to more stable and reliable products.
    - Developers can move faster by focusing on feature creation.
- Cons
    - Releases developers from accountability of the product.
    - Manual testing isn't scalable.
    - Creates an extra layer of communication from PM to test to development.

### **Tech Stack**

Before you reach out to development shops, I recommend you choose a tech stack. You might not have engineering resources to guide you in picking a tech stack beforehand but if you're reading this, you can at least reach out to Iterative for help at hello@iterative.vc. As a last resort you can also see what are the most popular stacks today for your given use case online. You may not understand all the tradeoffs but at least you'll know what the possibilities are. 

Allowing an outsourced company to choose your tech stack for you generally doesn't work because your goals aren't aligned and causes the below issues.

1. **Use what they know -** Generally they won't choose what is best for the project but what is most familiar to them. A concrete example that happened recently is when a development shop proposed doing native mobile development vs. react-native. Although native mobile development has advantages, react-native for this use case was 30% cheaper than doing native. React-native also allows you to have one code-base for both Android and iOS which should make maintenance easier going forward. Hiring for react-native is also easier than recruiting mobile native devs. However, there are cases where native mobile development makes sense too.
2. **Overcomplicated architectures -** I don't think outsourced developers are being malicious but they have a tendency to create complex architectures to handle seemingly simple problems. Adding more complexity also adds more hours to a project which can be beneficial to them. One example I saw was dealing with search. They wanted to implement elasticsearch and I saw a database was already implemented which supported full-text searching. Instead of adding a new service which then adds testing, monitoring, deployment, and configuration management we could just implement it in the database we already had. Removing the need for an extra service.

### Timezone

If price is the most overrated quality companies look for in picking an outsourcing company, the amount of overlap with your primary timezone is the most underrated. Moving fast with an outsourced team is a function of communication and decision-making. Those happen the most when a significant amount of time overlaps between your timezone and your outsourced team. Spending hours building the wrong thing because a simple question couldn't be asked in real-time is a very common scenario and leads to engagements coming in overpriced and overtime. Always try to maximize your working hours with that of your outsourced team for the greatest efficiency and speed. 

Ideally this is at least 5 hours of overlap with your primary timezone. I've also seen 3-4 hours of overlap be successful too but it takes a well disciplined team with a strong focus on written specs. Less than that and you'll struggle to move fast. 

## Sourcing

Once you've figured out the requirements, you'll have to search for outsourced development companies. They aren't hard to find but depending on the channel you'll have to put more or less work in evaluating them.

### Channels

1. **Referrals -** The best channel to find outsourcing companies period. You'll also be able to skip a step in evaluating them. ****If you have friends or people in your network that work in technology, you likely know people that have worked with outsourcing companies before. A quick post on LinkedIn can save valuable time when looking for quality outsourcing companies.
2. **Startup Groups -** If you really can't find any referrals the next best place to ask for help is startup groups. In the Philippines there's a facebook group called [Startup PH](https://www.facebook.com/groups/startupph), there's the [Asia Tech Review](https://t.me/asiatechreview) telegram channel, and of course your favorite accelerator, Iterative. Reach out to hello@iterative.vc and we can recommend a few too. 
3. **Top X Lists -** If you search on Google for outsourcing companies you will get "Top 15 Outsourcing Companies" or something like that. Stay away from these lists. They are SEO traps and rarely give good leads in my opinion. This competition is more about spending money on SEO vs. having a quality outsourcing business.

Sourcing companies can be hard but once you've reached a few passionate tech entrepreneurs you'll soon have more than you can talk to. Don't forget to screen them using the requirements you've built above. No matter where they come from, don't sacrifice the requirements you've identified will best fit your companies needs.

## Evaluation

Once you've identified 2-4 companies you're interested in working with, I've generated a list of useful questions to ask and red flags to screen.

### Things to ask

1. **Referrals -** Ask if you can talk to a previous client. Generally they will cherry pick the client so it isn't always a representative signal but if they hesitate or the client had a bad experience that's a red flag.
2. **Availability -** Many outsourced companies won't have enough staff on hand to handle incoming projects which may delay the start date. This is problematic though because if they have to hire externally for your project, they've never worked with that developer before. The best outsourcing companies will hire opportunistically and only take projects as others wind down. 
3. **Interviews or trial period -** If you have engineering help, I'd always ask to interview the engineers you'll be working with beforehand. Technical interviews are an entirely separate topic but generally choose an easy technical challenge to just assess if they are capable. If they won't allow you to interview or don't the engineers you'll work with on-staff ask for a 2-4 week trial period before you start. Trial periods are even better than interviews.
4. **Workflow and integration -** A great way to assess how organized a team is, is to ask what their workflow is and how they plan to integrate with you. Great teams will respond with a structured plan like "we meet with clients twice a week with X,Y,Z and work internally in 2 week sprints". A red flag would be "we can do whatever you want" or not having an opinion.
5. **Tech stack -** Ask if they have a preferred tech stack and what they are comfortable working in. If they say they can work in all tech stacks, that is a red flag. Over time, outsourcing companies should build a proficiency around certain stacks and that should generally line up with what you've identified above. Conversely, if no outsourced development shops can code for your tech stack you should possibly reconsider your tech stack as it may be hard to hire for. 
6. **Milestones and acceptance periods -** If you're doing the "Building a Product" engagement, there should always be clear milestones set and a certain amount of time after to do acceptance. Only after acceptance should payments be made and I highly recommend at each milestone you ask to be able to see the code. Then have an engineer review the code during acceptance to understand what the quality is like.
7. **IP rights and ownership -** It should be non-negotiable that you own all IP. If they want to use in-house proprietary technology or build on services that you can't customize later that is a red flag. An example is if they want to build your app on their proprietary backend which hosts 5 other clients. In the future, it will be very hard to migrate from that service and it locks you into working with that outsourced development shop indefinitely. This shouldn't be confused with using widely available backends like databases on AWS which can transfer ownership easily. 
8. **NDAs and confidentiality -** You can ask for these but I wouldn't bother. Rarely enforceable and outsourcing companies aren't looking to create startups.

### Pricing

Almost all outsourcing companies price differently. Some have one-time fees, minimum engagements, different rate increments (months vs. hours), termination fees, etc. For "Building a product" engagement this is straightforward as all payments are built into the plan. For "Scaling an existing team", it's usually less clear so I like to ask "if we started today with X engineers, walk me through all the charges a 6-month engagement incurs." 

Below I've also put together what a senior developer would expect to get paid to give you context about base prices are like in each region. Outsourcing companies will charge on top of this but it shouldn't be exorbitantly more for a region. Also depending on what part of the stack they work on they'll be paid slightly more or less. Generally Frontend < Backend < Mobile < AI/Data Science.

| Location | Salary (Low) | Salary (High) | Availability |
|----------------|--------------------------|---------------------------|------------------------|
| Singapore      | 4,000                     | 8,000                      | High                   |
| Vietnam        | 1,500                     | 3,000                      | High                   |
| Philippines    | 1,000                     | 1,750                      | Low                    |
| China          | 4,200                     | 7,000                      | High                   |
| Indonesia      | 1,250                     | 2,300                      | Low                    |
| Thailand       | 2,000                     | 4,250                      | Med                    |
| San Francisco  | 15,000                    | 2,0000                     | High                   |


## Conclusion

[Software development is hard](https://hackernoon.com/why-is-software-development-so-hard-i43t32lh). It's the reason why tech workers are paid highly for doing it. Adding outsourced engineering takes that hard problem and compounds it but we can limit those negative effects by figuring out our own requirements, sourcing companies efficiently, and evaluating them effectively.

I'm also a partner here at the Iterative accelerator and if you're a startup in Southeast Asia having issues setting up your outsourced team or having problems with an existing engagement drop us a line at hello@iterative.vc. If you want to stay up to date with what's happening here at Iterative or see more content geared at startup founders you can sign up for our newsletter below.