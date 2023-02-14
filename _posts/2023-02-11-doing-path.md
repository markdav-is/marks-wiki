---
title: The Doing Path
date: 2023-02-11
---

# The Doing Path
I've been reading _Strategic Doing_ and it's a great read. SD is oriented to larger groups and I've been reflecting on the smaller 5 person teams I encounter daily. These teams build art and software projects for work and civic orgs. On this blog I'm collecting my thoughts around three main practices: _Minimal Agile_ that's is just enough process to keep focused on the work, _Behavior Driven Design_ that keeps products rooted in conversations, and _Defaulting to Do_ as a way to keep things flowing forward. These combined practices I'm collectively calling "The Doing Path" as an homage to Taoist use of the words _way_ or _path_.  Not in a pretentious or religious aspect, but as a simple set of aspects to keep in mind when addressing hard problems with small teams.

## Minimal Agile
The most effective team size is one. A single person working on a product is an artist and they have all the skills required to build the product and take it to market. Most artists have process and often keep lists to help remember things. Adding folks to this scenario requires communication that takes efforts away from building the product. A team is a community of folks with a common goal. One trap teams fall into is spending too much time focused on the process and not enough time focused on the product.  To avoid this trap I'm recommending to use the lease amount of process possible and I'm referring to this as Minimal Agile.  As a starting place, use the agile ceremonies (ask the internet) and pick a simple tracking tools that supports checklists in tickets.  Have everyone on your team read _the checklist manifesto_ and _agile manifesto_ as backgrounders. The ceremonies I've picked are concentric loops with a Release being in the outer loop made up of multiple cycles and daily stand-ups.   

- Release Scoping
- - Cycle Planning
- - - Daily Stand-up
- - Cycle Demo
- Release Demo & Retro

### Release Scoping
Following software terminology, a Release is something that gets delivered to the customer.  You can think of it in more general terms as something your team will release into the wild. It's can be an end-goal for a small projects, or an iteration for larger ones.  Scoping ceremonies try to fit effort into a milestone.  For example, for a large art project, you might have an event a few months away.  For the event, you will need to have a number of things in place.  Each thing you want to fit into this event needs to be completed by the event date.  Making a list of these things is critical so everyone knows what is being built.  In software terms these are called features and/or capabilities.  A feature can be something you see like "play a video" and a capability can be something that happens like "accept credit cards". This is the first time we'll use the _three questions_ from _strategic doing_ What could we do?  What should we do? What will we do.   

#### What could we do?
Based on the folks in the room, take a look at the work ahead of you and ask free-wheeling questions like "How might we accomplish the goals of the release?" bounded only by the imaginations and capabilities of the attending team members. Establish psychological safety in the room and make space for all voices. Time-box this to 15 minutes.  Use a whiteboard or sticky-notes to capture everything that was talked about.

#### What should we do?
Looking at everything that comes out of the _what could we do?_ session, take a look at these suggestions from a practical perspective. How well to they fit the budget? How well do they fit the timeline? Do we truly have these capabilities on the team?  If there's a customer involved, how does this align with their expectations?  You might not have the customer in in the room for this conversation, but you definitely need their voice heard thru a representative like the product owner.  This conversation should add basic time and budget scope to these ideas and should take another 15 minutes.

#### What will we do?
The conversation so far should have generated a fine set of possible things to build.  Based on everything you now know, it's time to pick that you will put into to the release in time for the milestone.  Be honest and make sure you are not experiencing magical thinking about what the team can accomplish.  Do members have multiple project pulling at their time?  Have you accounted enough time for customer feedback in the iterative cycles that will come next?  Se yourself up for success buy shooting to be ahead of schedule and under budget.  


### Cycle Planning
Find a cycle cadence that works for your team.  Start with weekly cycles that follow the standard work week.  Try and move all your meetings to Mondays and Fridays to preserve the bulk of the week for product building efforts. Ask the internet about _maker vs manager schedules_ for more info on preserving building time by managing meetings.  In cycle planning dedicate an hour to properly breaking down the list of goals that are in scope for the release. If you estimate a goal will take longer than a cycle, break it down into smaller pieces.  I'll use a shopping-cart in an app for an example.  A completely functioning shopping cart needs User Interface elements, validation that that the data is correctly formatted, it will post dat to an API that will in turn talk to a credit-card processing system and an inventory system. If this is too much work for your cycle, start breaking it down.  Maybe move credit card processing into a later release for example. The outcome of cycle planning is to get the team that is doing the work to agree that the amount of work in the cycle is reasonable.   

### Daily Stand-ups, Demos and Retros
There's a zillion example of doing these common agile ceremonies on the internet.  I'm not going to belabor explaining them here except to share some pro-tips: Always pre-record your demos just in case something goes wrong when you are giving a live demo and you can fall back to playing the video.  Canned demos also allow you to re-wind and talk about specific parts.  Also record any feedback when you demo to be shared with the whole eam later.  My favorite retro format is the pirate ship because it's fun.  Retros should be fun, and mix-up the format to get fresh insights.

## Behavior Driven Design
BDD is a whole methodology to itself and I have yet to find the definitive book on the subject. I use Specflow in my software projects and it's a good set of tools.  I think BDD applies to any project, not just software because it uses clear and concise language to describe things using templates for Features, Scenarios and Behaviors

### Features (and Capabilities)
The largest scoped task we like to track is a feature (or capability) and can be described in a few works like "check for tickets at the door" or "shopping cart".  The purpose of tracking this high level item is ask as a dashboard of large items for your release timelines.

### Scenarios
Scenarios is where the templated language kicks in.  "As a [person] I need to [perform action] so I can [accomplish goal]." The advantage to this explicit language is that it's really clear who is doing what and why. "As a patron of the event I need to exchange my ticket at the door for drink tokens so i can get drinks at the bar.  The beauty of sceneries is that they are in regular language that anyone can understand.

### Behaviors aka Gherkin
I've always had a hard time with "Gherkin" (ask the internet) as a term and prefer to call this template _behavior language_ or _given-when-then_.  If follows the template "[given] a state of things, [when] action performed, [then] new state exists" and you can liberally pepper this with _and_ as needed to describe more complicated situations.  For example "Given a shopping cart that is full of items and a credit card on file, when the buy button is pressed and an address is selected, and a confirmation popup is accepted, then the items are removed from available inventory, and the credit card on file is processed, and the pick ticket is ent to the warehouse".  That's a pretty stacked behavior, and can should likely be broken down into smaller behaviors, but it's easy to understand and more importantly testable.  A shorter example of a behavior is "Given at least one item in the shopping cart, when visiting the _my cart_ screen then the buy button is available to tap/click". Again the most valuable part of this language is that it's testable.

## Defaulting to Do
The most valuable part of this path to getting things done is a _doing_ mindset.  At every stage of the construction effort the way forward is always taking action. Let's say you've been given a task that is poorly defined.  One reaction to this would be to add a comment to the task to the effect of "needs more information". Adding that comment implies that someone, somewhere will be on the lookout for your comment and fill in the gaps. I call this _magical thinking_ and the preferred approach would be to take action.  What action to take?  If we have enabled everyone on the team to understand the work, they should be able to see the way forward.  A correct action is always a combination of doing and communicating.  Start working on a new feature/scenario/behavior in the working folder for the project and at the same time sends coms to the product owner "I started on the missing docs here [link] and made a ticket for you to verify the contents".

## Just enough process
Be careful not to spend all your time in the tickets or chat or email.  Focus on doing and getting things done.  If you need to skip forward and build stuff without clear direction, be ready to re-do that work.  Retrospectives are the time talk about process, what's working and what's not.  When selecting a tool for tracking your tickets, be sure to select on that allows for checklists.  Most tools that support markdown will support checklists in the description just by including [ ] before a list item.  

For example:
- [ ] This is
- [ ] an example
- [ ] checklist

Many teams fall into the trap of spending more time updating tickets than they do building the product.  This reminds me of the adage "measure 100 times and cut once" that like to set things up for success completely before starting.  This is _waterfall thinking_ and not cyclical or iterative.  

My plan is to post here on this wiki exploring more of these concepts.  As I encounter blockage to the flow of my personal a work projects I'll dig into more details.




