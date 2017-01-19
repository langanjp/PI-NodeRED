# PI-NodeRED
Project to use Node-RED to connect Raspberry PI and other IOT data sources to OSIsoft PI using the PI Web API

##Pre-Reqs
*  Raspberry PI 3
   *  Node-red v0.14.6 (not the default) or higher already installed: https://github.com/langanjp/PI-NodeRed/wiki/Node-RED-Installation#upgrading-node-red-and-nodejs
   *  Other version of Raspberry PI and the default version of Node-RED should work, but have not been fully tested
*  Connected to network, with a known IP address (may need keyboard, mouse and monitor for initial setup)
*  PI Sense Hat
*  Access to PI Web API 2016 server or higher 
   *  Connected to your own (not shared) PI AF DB and your own (not shared) DA
   *  If you need to share a DA, some AF templates will need to be modified before using to create a user specific AF template to modify the hierarchy and tagnames that will be created by the templates.
*  PI Web API will need "Anonymous" and "Basic" authentication: 
   *  Anonymous will break PI Coresight searching, so it would ideally be a dedicated PI Web API server
   *  Also, it is not advised to leave a PI Web API server in Anonymous if write enabled. Anonymous access is needed for one example of the PI Web API's websocket (or Channels) due to limitations of the Node-RED websocket implementation.  Either create a PI Web API server just for Anonymous (and read-only access to certain tags or elements) or plan to remove Anonymous after doing the example exercise. 
*  PI Tag pointsource
   *  Create one called IOTED, or modify the AF imports xmls to your own desired pointsource   

##Tutorial
Please refer to this project's [Wiki](https://github.com/langanjp/PI-NodeRED/wiki) for a tutorial
