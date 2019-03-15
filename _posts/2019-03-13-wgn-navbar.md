---
layout: post
title:  "WeGovNow Nagivation Bar - Joomla Module"
date:   2019-03-13 21:00:00
categories: [joomla, module, IMC]
tags: module
---
This repository hosts the WeGovNow Navigation Bar module for Joomla. It is based on [WeGovNow barebone Navigation Bar](https://infalia.github.io/wegovnow/wgn-navbar).

The purpose of this module is to include the WeGovNow Navigation Bar which is linked to the Unified WeGovNow User Management (UWUM) system in the Joomla CMS.

Since, it is designed and implemented as pure Joomla module, it can be placed to any position according to the selected theme and template. It is suggested to set on top of the page spanning the whole width of the screen.

The *WeGovNow Navigation Bar - Joomla module* is fully responsive and supports automatic login/logout based on UWUM state.

Prerequisites
----------------
*WeGovNow Navigation Bar - Joomla module* requires a Joomla CMS instance to be up and running. You can download Joomla CMS from its official website.

For security reasons, it is suggested to always install *WeGovNow Navigation Bar - Joomla module* in the latest Joomla version.

Installation
----------------
The *WeGovNow Navigation Bar - Joomla module* follows the installation guidelines of Joomla CMS.

1) Download the [zip package](https://github.com/Infalia/mod_uwumnavigator/archive/master.zip) and drag and drop to the Extensions: "Upload and Install Joomla Extensions"

Setting up
----------------
Prior on using the module, some settings under the "Advanced" tab need to be defined. An indicative example with values for each required field is the following:

    //Set the UWUM client id
    Client ID: torino-imc.infalia 

    //Set the path to the UWUM auth Joomla plugin (see more details at [xxxxx](#))
    Login URL: https://torino-imc.infalia.com/component/slogin/provider/uwum/auth 
    
    //Set UWUM path to navigation
    Navigation URL: https://torino.liquidfeedback.net/api/1/navigation 

    //Set UWUM path to session
    Session URL: https://torino.liquidfeedback.net/api/1/session 

GitHub link
----------------
Download the source code at [https://github.com/Infalia/mod_uwumnavigator](https://github.com/Infalia/mod_uwumnavigator)

Download the [zip package](https://github.com/Infalia/mod_uwumnavigator/archive/master.zip) ready to be installed as Joomla extension via the Joomla Installer GUI.