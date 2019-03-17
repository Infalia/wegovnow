---
layout: post
title:  "Trusted Marketplace for WeGovNow - Reputation Aggregator Mechanism"
date:   2019-03-13 17:00:00
categories: [module, trusted marketplace]
tags: trusted marketplace
---
The Reputation Aggregator Mechanism, part of the [WeGovNow Trusted Marketplace](https://infalia.github.io/wegovnow/wgn-tmp) receives input from three different sources in order to define users' reputation score;

1) Indirectly from any other WeGovNow core component through the OnToMap Logger. All user events (actions and activities) are requested and being pulled by the Logger into the “Event Decomposer” that decomposes the raw consolidated information into data about i) activities, ii) location, iii) timestamp and iv) description as free text. The spatial data are forwarded to the “Geo Relevance Scorer”, the temporal data are forwarded to the “Temporal Relevance Scorer”, the interest/activity data are forwarded to the “Activity Scorer”, and data about user reputation are forwarded to the “Trust Ranker”.

2) Directly from the users through the “Dashboard” and their personal profile, preferences and interests that are explicitly declared by them.

3) By social networks, on user’s consent, through the “Social Media Linker & Collector”.

The high level architecture of Trusted Marketplace is depicted in the following diagram;

![High level architecture of TMP)](https://infalia.github.io/wegovnow/assets/images/TMP_architecture.png)

The “Relevance Fusion” merges the various scores that are calculated by applying several rules such as (but not limited to): i) certain radius containing actions of all the places that the specified user has recorded activity (geolocated), ii) actions within available time-slots (e.g. every weekend), iii) reputation threshold, iv) relevance matching threshold, v) notification frequency threshold (e.g. up to 3 notifications per day) and others. Lastly, the “Ranking & Notification” feeds the “Notification” mechanism that informs users with personalised suggestions in the Landing Page, and also helps to enhance the personalised timeline in the user interface (UI) of the Trusted Marketplace. It also helps to prioritise (rank) the most relative offers/demands according to user interests. Trusted Marketplace UI also includes i) the “Reputation Aggregator” which is actually part of the “Offers & Demands Organiser”, ii) the “Accessibility User Preferences Guide” and iii) the Dashboard. The latter three modules are composing the “Enhanced User Profile” that interacts with the UWUM to get and set global variables (e.g. user preferences) as key- value pairs. 

Installation
----------------
This is a CLI tool. You run directly from either the command line or create a wrapper around it (e.g. bash script).

GitHub link
----------------
Get the source code and find more details at [https://github.com/Infalia/tmp-reputation-mechanism](https://github.com/Infalia/tmp-reputation-mechanism)