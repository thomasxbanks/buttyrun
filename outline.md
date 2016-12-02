# Production Notes

## The Purpose
The idea behind this software is to make the regular ordering of the Friday Butty Run easier to manage.

### The current process
1. One person emails, texts, and/or Slacks everyone in the office, depending on which communication method they use, asking if they want a butty picking up.
1. One person then purchases sandwiches for all the people who have replied by the time they get to the shop.
1. One person then collects money from the purchasers in exchange for their butty.

### Issues with the current process
1. No centralised communication method.
1. Relies on either the organiser remembering what each person wants from the last order or asking everyone what they want each time.
1. Relies on either getting an itemised receipt from the shop (and really, how many bacon butty shops do receipts?!) or remembering what each sandwich cost and getting the right money from each purchaser.
1. Leads to mistakes in sandwich make up.
1. Leads to people not replying in time (if the orderer doesn't have their mobile number, etc.) and not getting a butty if they want one.

### Current solutions to these Issues
1. Using a note-taking app, such as Google Keep to make notes or just checking email/slack/texts whilst ordering in the shop

### How can we make this better?
The idea behind this is to create a centralised communication method that also stores a purchaser's preferred butty and allows a simple one-tap 'geg in on this run' response method. How I envisage it working is that, for the purchaser, they get a push notification at, say, 8.30 on a Friday asking if they want in on the run. Select _yes_ to order the same thing as last time, select _no_ to opt out, select _change_ to order a different butty. The person in the shop then has a list of the people who have opted in with their selection in one place.

### How does this solve the problem?
1. Storing your preferred option against your details greatly reduces the chance of making a mistake in ordering.
1. The one-tap opt-in greatly improves a person's chances of being included
1. The push notification greatly improves a person's chances of being included

### Does this introduce any new problems?
1. It does not completely solve the issue of centralised communication.
  - Everyone needs to have the software and have notifications set up to be included. This may lead to some people still being excluded because they do not want to install an app. Potentially merely _adding_ to the breadth of communication methods!
1. There could still be issues around payments and pricing. The orderer will still be charged, say, £15.75 by the shop and have to work out that Carol needs to reimburse him £3.20. This could be addressed in a variety of ways and, as such, is worth investigating further as it seems to be a key issue in the original process.

### Extensions
By replacing __butty__ with __brew__ would allow this to work for regular brew runs. Whoever is going to make the drinks/buy the drinks from Starbucks sends a timely push notification, everyone else opts-in or opts-out and the brew-maker gets a list of who wants what - no more forgetting if Janet takes sugar or accidentally putting milk in Thom's coffee!

______

## Hierarchy of data

1. Primary level
  - Company
2. Secondary level
  - Individual
3. Tertiary level
  - Product

This is simply explained as;
A company consists of one or more individuals
Individuals own one or more sandwiches

__Mike__ works for __BBC__ and his sandwich is __bacon-sausage-brown_sauce__

__Carol__ works for __BBC__ and her sandwich is __egg-ketchup__

__Robert__ works for __ITV__ and his sandwich is __bacon-egg-brown_sauce__

Mike and Carol are grouped under __BBC__.  
Robert is grouped under __ITV__ along with anyone else who joins in from ITV in future. Robert is _Patient Zero_ for ITV.

### Is this a many-to-many relationship?
This is a valuable question that speaks to the nature of sandwiches.

__Egg__ is a _thing_ that exists in many sandwiches attributable to many people in many companies. Does __egg__ exist as a _thing_ in the software?

The simplest form of the software would be to keep _sandwiches_ as an abstract concept (probably by virtue of a free-text field) leaving a simpler relational hierarchy - A __company__ consists of one or many __individuals__ who each have one or many _unique_ __products__.

This decoupling of the idea of 'shared ingredients' will allow for this software to be used for more than bacon sandwiches - the free-text field could describe anything; how you like your brew, stationery ordering for offices, food orders from any kind of takeaway, etc. (With this in mind, I may have to change the name of the software!)

## What do I need to define?

1. What is a company?
  - A company is a group of individuals sharing a commonality (place of employment)
1. What is an individual?
  - An individual is a member of a company with a product associated to them (default sammich)

## What do I need to know about these?
1. Company
 - Address to deliver to
 - Individuals attached to this company
1. Individual
 - Company they are attached to
 - Sandwich they want
 - Whether they are the 'orderer' or the 'purchaser'

______

## First Steps
I need to...
1. create a company
1. create several individuals
1. add a product to each individual
1. generate a push notification at a specified time to all 'purchaser'
1. allow a response from each 'purchaser'
1. generate a list of individuals that responded 'yes' and display it to the 'orderer'

## Brand Identity
Things to consider in regards to design
- __Fonts__
  - Must be readable on a variety of screen sizes and resolutions
- __Colours__
  -  No thoughts on colours at the moment. Ideally, neutral as we will have little to no control of imagery (see below)
- __Design__
  - As the product is very light on content, we can be a bit more adventurous.
  - Simplistic data representation leaves room for "wow factor" to be introduced by design.
- __Imagery__
  - The intention is that users will import their own avatars (if we even have avatars!)
  - If we eventually tie this in to catering companies, their imagery will be used. Again we'll have zero control.
  - Very little, if any, other imagery to exist in the app.
