# Venmo-Transaction-Analysis

The following analyis was done for eductional purposes and uses Venmo transactions gathered of the course of a month in November 2020.

In order to obtain the Venmo transactions used in this analysis one can use the following url venmo.com/username, where username is the unique username for each user. Given a valid username you are given an html file including the most recent 5 public transaction; from each transaction we can get the time sent, the usernames of the people involved in the transaction, and the message accompanying the transaction. This seems to be the only way at the moment of viewing public Venmo transactions without signing in to Venmo. If one wants to request a multitude of user transaction the hardest step will be finding valid usernames. In this analyis the folllowing method is used.

1. Get the most recent Venmo transactions from any user and record the usernames of the users involved in the transactions(at best we will get 5 at worst 1). Add these usernames to a list of unchecked usernames, and add the original user to a list of checked usernames.
2. Get the most recent Venmo transactions from someone in the unchecked users, if there are any new unchecked usernames add these to the uncheck username list, and then add the searched username to the checked username list.
3. Repeat step 2 until one runs out of usernames to check. 

There are two problems that arise in this method, we tend to get almost no older transactions as  we are only being shown the most recent transactions coupled with the fact that users who are involved in a recent transaction tend to be frequently using Venmo and so their 5 recent transactions will all be very new. Another problem is we quickly run out of new users to seach, as many users either Venmo very few people or groups of friends tend to only Venmo other friends which creates cycles, this can be thought of as a cycle in graph theory.

To reduce these cycling and recency problems. We observe that most Venmo usernames have a common theme, as most users go with the default username. Which is of the form:
**first_name-last_name-number** Example: John-Doe-10

This number tends to be an increment based on how many people with the same first name and last name signed up before any user.
Therefore if this number is low we can assume that be searching with same first name and last name with small number increments we can obtain more users.
This turns out to help solve both the cycling and recency problems.

The code to do this wont be provided however is fairly straightforward.
