# PI-NodeRED
Project to use Node-RED to connect Raspberry PI and other IOT data sources to OSIsoft PI using the PI Web API

## Overview
This project and tutorial show the steps using Node-RED (a node.js / JavaScript based graphical progamming language) to collect and transform data from a Raspberry PI and PI Sense HAT (json) and send it to the OSIsoft PI System.  This also explores gathering data from other web sources to send to the PI System, including weather station data (xml) from the National Weather Service (weather.com), and power grid data (html) from ERCOT (ercot.com).  This project also demonstrates displaying of OSIsoft PI Data on a Raspberry PI - PI Sense HAT display.  Finally, it also offers a simple tutorial on using the PI Sense HAT in Node-RED.   

## Tutorial
Please refer to this project's [Wiki](https://github.com/langanjp/PI-NodeRED/wiki) for a tutorial and instructions

## Pre-Reqs
*  Raspberry PI 3 (https://www.raspberrypi.org/products/raspberry-pi-3-model-b/)
   *  running Raspian Jessie  
   *  running Node-red v0.14.6 (not the default) or higher already installed: https://github.com/langanjp/PI-NodeRed/wiki/Node-RED-Installation#upgrading-node-red-and-nodejs
   *  Other version of Raspberry PI and the default version of Node-RED may work, but have not been tested
*  Connected to network, with a known IP address (may need keyboard, mouse and monitor for initial setup)
*  PI Sense Hat (https://www.raspberrypi.org/products/sense-hat/)
   * If you don't have a PI Sense Hat, there is a node-red sense hat simulator that you can install: https://www.npmjs.com/package/node-red-node-pi-sense-hat-simulator.  It does not fully support the exercises as it does not support displaying text.
*  Access to OSIsoft PI Web API 2016 server or higher 
   *  Connected to your own (not shared) PI Asset Framework (AF) DB and your own (not shared) PI Data Archive (DA) 
   *  If you need to share a DA, some AF templates will need to be modified before using to create a user specific AF template to modify the hierarchy and tagnames that will be created by the templates.
*  PI Web API will need "Anonymous" and "Basic" authentication: 
   *  Anonymous will break PI Coresight searching, so it would ideally be a dedicated PI Web API server
   *  Also, it is not advised to leave a PI Web API server in Anonymous if write enabled. Anonymous access is needed for one example of the PI Web API's websocket (or Channels) due to limitations of the Node-RED websocket implementation.  Either create a PI Web API server just for Anonymous (and read-only access to certain tags or elements) or plan to remove Anonymous after doing the example exercise. 
*  PI Tag pointsource
   *  This will automatically create one called IOTED as part of the automated PI tag creation, or modify the AF imports xmls to your own desired pointsource   
