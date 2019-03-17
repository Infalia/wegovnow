---
layout: post
title:  "WeGovNow OnToMap Logger - Joomla plugin"
date:   2019-03-13 20:00:00
categories: [joomla, plugin, IMC]
tags: plugin
---
This is the Joomla plugin which is implemented to allow any Joomla application to communicate with the WeGovNow OnToMap Logger.

It follows the "Dispatcher / Observer" design pattern in order to be able to "listen" specific events that are triggered by core application components (e.g. ImproveMyCity) and proceed with certain actions such as sending to the mapped concepts in the WeGovNow Ontology the corresponding metadata.

Prerequisites
----------------
*WeGovNow OnToMap Logger* requires a Joomla CMS instance to be up and running. You can download Joomla CMS from its official website.

For security reasons, it is suggested to always install *WeGovNow OnToMap Logger* in the latest Joomla version.

Installation
----------------
The *WeGovNow OnToMap Logger* follows the installation guidelines of Joomla CMS.

1) Download the [zip package](https://github.com/Infalia/otm_logger/archive/master.zip) and drag and drop to the Extensions: "Upload and Install Joomla Extensions"

Setting up
----------------
This plugin is *observing* events which are being dispatched by the ImproveMyCity for the WeGovNow core component. In order to make the WeGovNow OnToMap Logger plugin to *listen* to your third party Joomla application you have two options. Either you dispatch events with the same name as below, or you (most probably) slightly change the source code (just the function names of the observing events) of this plugin according to your needs.

Available events (as used by the ImproveMyCity for WeGovNow core component);

- onAfterNewIssueAdded
- onAfterCategoryModified
- onAfterModerationModified
- onAfterStepModified
- onAfterNewCommentAdded

An example schema function that you could use for your Joomla application follows:

    public function onYourActionIsTriggered($model, $validData, $id = null) {
        ...
        // $model is your plain data model
        // $validData contains your validated sanitised data
        // $id you can pass explicity your data id
    }

> WeGovNow OnToMap Logger - Joomla plugin supports out-of-the-box the advanced OnToMap request BELONGS_TO that allows to connect your data to the WeGovNow FirstLife application.

Customisation
----------------
Before enabling the *WeGovNow OnToMap Logger* plugin, you need to set some required options. An indicative example with values for each required field is the following:

    //Set the OnToMap App ID
    OnToMap App ID: torino-imc.infalia.com

    //
    OnToMap events endpoint: https://torino.api.ontomap.eu/api/v1/logger/events 
    
    //
    OnToMap mappings endpoint: https://torino.api.ontomap.eu/api/v1/logger/mappings 

    //OnToMap .pem file
    OnToMap .pem file: /opt/my/path/to/pem/torino-imc.infalia.com-uwum.pem

    //
    Application path of FirstLife: wegovnow.firstlife.org

GitHub link
----------------
Download the source code at [https://github.com/Infalia/otm_logger](https://github.com/Infalia/otm_logger)

Download the [zip package](https://github.com/Infalia/otm_logger/archive/master.zip) ready to be installed as Joomla extension via the Joomla Installer GUI.
