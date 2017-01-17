# PI-NodeRED
Project to use Node-RED to connect raspberryPI and other IOT datasources to OSIsoft PI using the PI Web API

Pre-Reqs
*  Raspberry PI 3
   *  Node-red v0.14.6 (not the default) or higher already installed: https://github.com/langanjp/PI-NodeRed/wiki/Node-RED-Installation#upgrading-node-red-and-nodejs
   *  Other version of Raspberry PI and the default version of Node-RED should work, but have not been fully tested
*  Connected to network, with a known IP address (may need keyboard, mouse and monitor for initial setup)
*  PI Sense Hat
*  Access to PI Web API 2016 server or higher 
   *  Connected to your own (not shared) PI AF DB and your own (not shared) DA
   *  If you need to share a DA, some AF templates will need to be modified before using to create a user specific AF teamplate to modify the hierarchy and tagnames that will be created by the templates.  This will need to be done before hand
*  PI Web API will need "Anonymous" and "Basic" authentication: 
   *  Anonymous will break PI Coresight searching, so it would ideally be a dedicated PI Web API server
*  PI Tag pointsource
   *  Create one called IOTED, or modify the AF imports xmls to your own desired pointsource   
