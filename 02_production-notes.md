# Production Notes

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
