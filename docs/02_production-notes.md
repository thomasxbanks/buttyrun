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
1. Relies on either getting a receipt from the shop (and really, how many bacon butty shops do receipts?!) or remembering what each sandwich cost and getting the right money from each purchaser.
1. Leads to mistakes in sandwich make up.
1. Leads to people not replying in time (if the orderer doesn't have their mobile number, etc.) and not getting a butty if they want one.

### Current solutions to these Issues
1. Using a note-taking app, such as Google Keep to make notes or just checking email/slack/texts whilst ordering in the shop

### How can we make this better?
The idea behind this is to create a centralised communication method that also stores a purchaser's preferred butty and allows a simple one-tap 'geg in on this run' response method. How I envisage it working is that, for the purchaser, they get a push notification at 8.30 on a Friday asking if they want in on the run. Select _yes_ to order the same thing as last time, select _no_ to opt out, select _change_ to order a different butty. The person in the shop then has a list of the people who have opted in with their selection in one place.

### Extensions
By replacing __butty__ with __brew__ would allow this to work for regular brew runs. Whoever is going to make the drinks sends a push notification, everyone else opts-in or opts-out and the brew-maker gets a list of who wants what - no more forgetting if Janet takes sugar or accidentally putting milk in Thom's coffee!


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
1. What is an individual?

## What do I need to know about these?
1. Company
 - Address to deliver to
 - Individuals attached to this company
1. Individual
 - Company they are attached to
 - Sandwich they want
