---
layout: post
featured : true
title:  "Dating Apps : Algorithms and ML"
author: [ Ainesh, Rishabh ]
categories: [ Machine Learning, Algorithms ]
image: assets/images/dating-apps.jpeg
excerpt: "The working and algorithms behind how dating apps work"
---

Over the last decade, dating apps and sites have exponentially grown in popularity owing to their ease of use and effectiveness. Today we will study about a few algorithms and techniques used by dating apps, and how these algorithms have changed through the years. Dating apps aim to connect like-minded people, which can be considered an example of the Stable Marriage Problem (SMP) in mathematics. The stable marriage problem can be stated as:

 > “Given n men and n women, where each person has ranked all members of the opposite sex in order of preference, marry the men and women together such that there are no two people of opposite sex who would both rather have each other than their current partners. When there are no such pairs of people, the set of marriages is deemed stable.”

Meaning that, given that every person has rated every person of the other set, we aim to find the most suitable matches using the rating given.

Now that we have stated our problem statements, we can theorise algorithms for the above.

## The Propose-Reject Algorithm

Every Morning: Each man goes to the first woman on his list not yet crossed off and proposes to her. 
Every Afternoon: Each woman says “maybe, come back tomorrow” to the man she likes best among the proposals (she now has him on a string) and “never” to all the rest. 
Every Evening: Each rejected suitor crosses off the woman who rejected him from his list. 

The above loop is repeated each successive day until there are no more rejected suitors. On this day, each woman marries the man she has on a string.

This is also called the Gale-Shapley Algorithm and is written in a more technical form as:

```
function stableMatching {
    Initialize all m ∈ M and w ∈ W to free.
    while ∃ free man m who still has a woman w to propose to {
        w = first woman on m’s list to whom m has not yet proposed
        if w is free{
            (m, w) become engaged.
        }
        else some pair (m', w) already exists{
            if w prefers m to m'{
                m' becomes free.
                (m, w) become engaged.
                }
            else{
                (m', w) remain engaged.
            }
        }
    }
}
```

It is pretty easy for us to notice that the above algorithm has an O(n2), where n is the cardinality of both sets.

## Elo Rating System

Traditionally, dating and matchmaking apps used primitive, more basic algorithms/methods to decide which profiles you and others get to interact with. One such method that used to be used by the popular dating app Tinder is the Elo rating system. The Elo rating system is a method used to measure the relative skill level of players/users. It is widely used in several fields to decide the rankings of its players/users, notably chess, multiple sports, video games and even popular competitive programming online judge sites such as Topcoder and Codeforces. The Elo rating system uses a point-based system where a player/user with a higher number of points would essentially be ranked higher than one with a lower number of points. When multiple users play a game/interact with each other, the outcomes of that interaction result in a change in the Elo score of the involved users. Generally speaking, it works on a few basic principles, which are:

> 1. If the higher-rated player wins, a few points are taken from the lower-rated player and given to the higher-rated player.
> 2. If the lower-rated player wins, a lot of points are taken from the higher-rated player and given to the lower-rated player.
> 3. If it is a draw, the lower-rated player gains a few points from the higher-rated player.

A similar system was used in matchmaking apps such as Tinder, however, the way it is implemented is a bit different. Your Elo score is a rating of your “attractiveness/likability”. If you have a high Elo score, it means that many people are liking (right-swiping) your profile. When a person likes your profile, your Elo score increases, with the increase being proportional to that of the person who liked your profile, and the vice-versa being true as well when people left-swipe(don’t like) your profile. The app mainly shows you profiles of users with Elo scores similar to your own, as these users are more likely to like your profile, and create a match with you, which is the goal of the app at the end of the day. Tinder employs multiple other features such as decreasing the occurrence of your profile in other peoples’ feeds if you are liking every single profile that shows up in your feed (sorry to break it to you but yeah, right-swipe spamming doesn’t work :’( ).

# Machine Learning

This implementation did work well, but as always in the field of computer science, there is room for improvement. One such method that many matchmaking apps nowadays are using is machine learning (ML). Machine learning helps the app use other measures and techniques to find users that you are more likely to right-swipe. Machine Learning algorithms can learn from how we interact with profiles of users, find similarities between accounts that I like or interact with more, and find profiles of users with similar interests. For example, if I right-swipe on every person who owns a cat, the algorithm realises that I’m interested in people that own cats and therefore suggests me more profiles of people that own cats. This increases the probability of users matching with people who are more compatible with them.

There are multiple approaches one could use, such as using a Recommender System to recommend one dating profile to another. Perhaps another method would be to classify each user profile as a specific class and have them match with other profiles under the same class. But our focus here will be using an unsupervised machine learning algorithm called K-Means Clustering. We will be using the profile content rather than the pictures themselves, as people are more likely to connect with like-minded individuals. We can use Natural Language Processing (NLP) techniques and find data related to the user from their profile, such as what their interests include, and feed it to our ML algorithm to search for profiles that share similar interests. We would, however, need a lot of profiles and data to train such a model.

K-means clustering is a signal processing technique used to cluster ‘n’ observations into ‘k’ clusters, with the nearest means. This reduces the within-cluster differences, i.e., grouping like-minded people into the same cluster.

Since publicly available dating profiles are rare or impossible to come by, which is understandable due to security and privacy risks, we will have to resort to creating fake dating profiles to test out our machine learning algorithm. Fake bios are available on quite a few websites online, which can be collected using web-scraping techniques. The other attributes can just be filled using lists and random number generators. The bios are then vectorised to remove words which lack function from a computation standpoint, and are then run through the K-means clustering algorithm and will get a clustered dataset which are our matches.

## Conclusion

Congratulations, you’ve made it to the end of this article. Now you can successfully blame a few software employees based out of West Hollywood as the reason for why you can’t get any dates online. Hopefully, you’ve right-swiped this article, and if you have, please do check out our other articles. In case you didn’t, we understand why you’re salty, and hopefully, you’ll find an article that you match with.