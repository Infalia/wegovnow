---
layout: post
title: "Scenarios"
---
> ## I want to include my Joomla! extension in the WeGovNow platform.

Joomla! has thousands of free and paid extensions that could be included in the WeGovNow platform.

At the first stages of the WeGovNow project, ImproveMyCity for WeGovNow was a monolithic Joomla application that included all WeGovNow dependencies inside the main component. Although this led to a quick prototype, this kind of design wouldn't allowed the expandability of the system and most importantly, it was very difficult for third parties to reuse any of the features.

Later on, ImproveMyCity broke into small modules and plugins that could be used independently and standalone, either with little or no parameterisation. Moreover, each module and plugin has its own UI for easier setup (no configuration files are used anymore).

Due to the heavy decoupling that took place, **anyone who wishes to include their Joomla based application in the WeGovNow platform is able to do it** by using the following modules and plugins and by following the [prerequisites described in the bottom of the page about getting a signed certificate](#prerequisites).

1) [WeGovNow Nagivation Bar - Joomla Module](https://infalia.github.io/wegovnow/wgn-navbar)  
2) [WeGovNow OnToMap Logger - Joomla plugin](https://infalia.github.io/wegovnow/wgn-otm-logger)  
3) [WeGovNow UWUM - Slogin Joomla Plugin](https://infalia.github.io/wegovnow/wgn-uwum-slogin)  

> ## I want to install the fully functional ImproveMyCity application in the WeGovNow platform.

For those cities who already using the WeGovNow platform and wish to include in their setup the ImproveMyCity application, the following steps are necessary:

1) [ImproveMyCity for WeGovNow - Core Component](https://infalia.github.io/wegovnow/imc-core)  
2) [WeGovNow Nagivation Bar - Joomla Module](https://infalia.github.io/wegovnow/wgn-navbar)  
3) [WeGovNow OnToMap Logger - Joomla plugin](https://infalia.github.io/wegovnow/wgn-otm-logger)  
4) [WeGovNow UWUM - Slogin Joomla Plugin](https://infalia.github.io/wegovnow/wgn-uwum-slogin)  

You also need to follow the [prerequisites described in the bottom of the page about getting a signed certificate](#prerequisites).

> ## I want to install the fully functional Offers & Requests application in the WeGovNow platform.

For those cities who already using the WeGovNow platform and wish to include in their setup the Offers & Requests application, the following steps are necessary:

1) [Offers & Requests for WeGovNow - Core Component](https://infalia.github.io/wegovnow/wgn-offers-requests)  

You also need to follow the [prerequisites described in the bottom of the page about getting a signed certificate](#prerequisites).

> ## Is it possible to use WeGovNow Trusted Marketplace or any of its features?

"Trusted Marketplace" (TMP) was replaced by "Offers & Requests" but still, TMP [source code is available in GitHub](https://github.com/Infalia/tmp) for anyone who is willing to use it.

It should be noted though that TMP is deprecated now but nevertheless **we are happy to support you in case you wish to reuse it and facing technical issues**.

You can check its functionalies either by following the detailed installation instuctions in the [Trusted Marketplace for WeGovNow - Core Component](https://infalia.github.io/wegovnow/wgn-tmp) and set it up to your own premises, or you can have a look of its features and functionalities in [WeGovNow Prototype 3](https://pt3-tmp.infalia.com/profile/basic-info). 

Trusted Marketplace is composed of the following sub-systems: 

1) The "Social Accounts Media Linker and Collector" for collecting personal posts

2) The "Reputation Aggregation Mechanism" to analyse the collected data from the "Social Accounts Media Linker and Collector" and set a user score

3) The "Enhanced User Profile" to be used for better match-making

4) The "Accessibility Preferences" (part of the "Enhanced User Profile")

5) The "Offers and Demands" (the ancestor of the future "Offers & Requests")

6) The "Personalised Timeline" (which is moved in the "WeGovNow Landing Page")

For convenience, we have managed to decouple the reputation aggregation mechanism from the Trusted Marketplace. It has a command line interface that allows to input tweets and outputs a set of metrics that could help define the reputation score of a person. The training dataset it was supposed to be populated during the pilot phase of WeGovNow through the "Social Accounts Media Linker and Collector" but the initial collected data during Prototype 3 are erased due to GDPR adjustment and afterwards the Trusted Marketplace was deprecated. 

So, in order to use the Reputation Aggregation Mechanism you need to collect new data and more specifically new tweets. Note that, the Social Accounts Media Linker and Collector supports; Twitter, Facebook, LinkedIn and Google social accounts, but the Reputation Mechanism works only with Twitter data.

For technical information and source code please visit the [Reputation Aggregator Mechanism section](https://infalia.github.io/wegovnow/wgn-tmp-reputation)

<hr>

<a name="prerequisites"></a>
## Prerequisites

**1) Availability of application via IPv4**

The client application is available via a defined URL using IPv4.

**2) Availability of application via IPv6**

The client application is also available using IPv6.

You can validate your URL with the following service 

    https://ipv6-test.com/validate.php?url=https://<your domain>

For example:
[https://ipv6-test.com/validate.php?url=https://wegovnow.infalia.com/](https://ipv6-test.com/validate.php?url=https://wegovnow.infalia.com/)

**3) Serving via HTTPS**

The client application service is encrypted via HTTPS.  
DO NOT confuse the SSL certificate for HTTPS with the X.509 certificate needed for the communication of UWUM-Clients with UWUM (see 4)

**4) X.509 certificate for client identification**

i) Create a certificate signing request (CSR) with your details

    CN of the certificate signing request (CSR) should be like "wegovnow.infalia.com" (change accordingly)

To create a CSR (given that you are using openssl):

    openssl req -out wegovnow.infalia.com-uwum.csr -new -newkey rsa:2048 -nodes -keyout wegovnow.infalia.com-uwum.key

ii) Submit CSR to the UWUM Certificate Authority to be signed  

Please send **only** the .csr file, the .key file should stay your secret

iii) UWUM Certificate Authority will then create an application record in the UWUM testing system for your
application and verify your client_id. 

Your client_id is actually the CN declared in the CSR

iv) UWUM Certificate Authority will send over the signed CRT (.crt) file

You need to create a combined .pem file out of the certificate .key file and the certificate .crt file using the following command (as an example):

    cat wegovnow.infalia.com-uwum.crt wegovnow.infalia.com-uwum.key > wegovnow.infalia.com-uwum.pem

Please ensure to place the .pem file outside the web directory, so it is not exposed to the public

**5) Inform UWUM Certificate Authority of your callback URL**

    e.g. https://wegovnow.infalia.com/oauth2_callback.php

**Note**

Callback URL should be set by client on demand