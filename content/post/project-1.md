---
date: 2020-06-10T00:00:00-00:00
description: "Tennis Prediction"
featured_image: "/images/tennis.jpg"
tags: ["Tennis", "Logistic Regression"]
title: "2020-06 : Tennis Prediction"
---

This is my first project in Data Science. I'm a fan of tennis, after practicing during 7 years. I missed the court.
What could be more interesting than studying Data Science with a little bit of nostalgia.
We tried to answer : Can tennis outcomes be predicted thanks to data available on the internet ?

I did this project with a friend of mine : [Florian DECONINCK](https://github.com/foukette), we had 3 weeks to do the analysis and create a dashboard on a website to see latest tweets regarding tennis, see different results of tennis matches and link our predictions to it.

We reached an accuracy of 65% by using elo rating of player in a Logistic Regression. That is a good score already but we then tried to do a more deeper analysis.

We tried to compute more features to see if we can beat this accuracy :

We performed different steps to reach our goal :
- **Data collection** : we got our data from a website that freely gives a pre-populated database with tennis results and a lot of information on players. This website is [Ultimate tennis statistics](https://ultimatetennisstatistics.com/)
- **Data cleaning** : we checked all features to see if some important data was missing. We saw that we had matches duplicates, we decided to drop those duplicates and reverse half of the matches to get a balanced sample.
We also dropped features that we weren't interested in like match_id, player_rank (we preferred elo_rating which is more accurate) and surface.
We handled NA values by dropping records where missing values were essential for future steps. We also saw that missing values were mostly coming from atypical tournaments like Davis Cup or ATP Finals.
- **Feature scaling** : we then scaled our features for the Logistic Regression
- **Feature Engineering** : We computed new statistics as first serve success percentage, winning on first serve percentage, aces, percentage of matches won, and also head to head statistics between players. We then performed feature difference to have one feature for each statistics representing the difference of levels between the 2 players on this statistics.
- **Feature selection** : We performed recursive feature elimination to keep only the most important features.

{{< figure src="/images/rfe.png" title="Recursive feature elimination" >}}

- **Modeling** : We got a 64% accuracy, this model didn't outperform our previous model, our features don't seem to bring more information than elo rating.

![Confusion matrix](/images/confusion_matrix.JPG)

In conclusion, with more time to research really important features, with more time to do exploratory analysis and statistics tests to evaluate our features, we could expect to improve our model.

[Link to the github repository](https://github.com/Thrynk/Tennis-prediction)

