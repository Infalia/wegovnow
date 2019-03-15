---
layout: post
title: "Scenarios"
---
> ## I want to include my Joomla! extension in the WeGovNow platform.

Joomla! has thousands of free and paid extensions that could be included in the WeGovNow platform.

At the first stages of the WeGovNow project, ImproveMyCity for WeGovNow was a monolithic Joomla application that included all WeGovNow dependencies inside the main component. Although this led to a quick prototype, this king of design wouldn't allowed the expandability of the system and most importantly, it was very difficult for third parties to reuse any of the features.

Later on, ImproveMyCity broke into small modules and plugins that could be used independently and standalone, either with little or no parameterisation. Moreover, each module and plugin has its own UI for easier setup (no configuration files are used anymore).

Due to the heavy decoupling that took place, **anyone who wishes to include their Joomla based application in the WeGovNow platform is able to do it** by using these modules and plugins and by following the steps below:

1) xxx  
2) xxxx  
3) xxxxx  

> ## I want to install the fully functional ImproveMyCity application in the WeGovNow platform.

For those cities who already using the WeGovNow platform and wish to include in their setup the ImproveMyCity application, the following steps are necessary:

1) xxx  
2) xxxx  
3) xxxxx  

> ## I want to install the fully functional Offers & Requests application in the WeGovNow platform.

For those cities who already using the WeGovNow platform and wish to include in their setup the Offers & Requests application, the following steps are necessary:

1) xxx  
2) xxxx  
3) xxxxx  

> ## Is it possible to use WeGovNow Trusted Marketplace or any of its features?

"Trusted Marketplace" (TMP) was replaced by "Offers & Requests" but still, TMP [source code is available in GitHub](https://github.com/Infalia/tmp) for anyone who is willing to use it.

It should be noted though that TMP is deprecated now but nevertheless **we are happy to support you in case you wish to reuse it and facing technical issues**.

You can check its functionalies either by following the detailed installation instuctions in the [README](https://github.com/Infalia/tmp) file and set it up to your own premises, or you can have a look of its features and functionalities in [WeGovNow Prototype 3](https://pt3-tmp.infalia.com/profile/basic-info). See some indicative screenshots below.


##### PUT A SCREENSHOT HERE

Trusted Marketplace is composed of the following sub-systems: 

1) The "Social Accounts Linker" for collecting personal posts

2) The "Reputation Mechanism" to analyse the collected data from the Social Accounts Linker and set a user score

3) The "Enhanced User Profile" to be used for better match-making

4) The "Accessibility Preferences" (part of the Enhanced User Profile)

5) The "Offers and Demands" (the ancestor of future Offers & Requests)

6) The "Personalised Timeline" (which is moved in the WeGovNow Landing Page)

For convenience, we have managed to decouple the reputation mechanism from the Trusted Marketplace. It has a command line interface that allows to input tweets and outputs a set of metrics that could help define the reputation score of a person. The training dataset it was supposed to be populated during the pilot phase of WeGovNow through the "Social Accounts Linker" but the initial collected data during Prototype 3 are erased due to GDPR adjustment. 

So, in order to use the Reputation Mechanism you need to collect new data and more specifically new tweets. Note that the "Social Accounts Linker" supports Twitter, Facebook, LinkedIn and Google social accounts, the Reputation Mechanism works only with Twitter data.

For technical information and source code please visit the [Reputation Mechanism GitHub repository](#)

##### PUT THE LINK