### Open Source Link Compilation
This is a directory of some of the open source projects I worked on during my summer 2014 internship with Progress Software.

### [Roll Call App](https://github.com/progress/roll-call) 
A simple app for keeping track of who is in the office at any given time. Each member of the office is represented by a Hue smart lightbulb in a bulb array, with each bulb shining green or red to represent in or out. When a user enters or exits, the bulb flashes a few times before updating to the new color.

Technology Breakdown: The user movements are tracked through an iOS app that detects the iBeacon network within the office. The iOS app communicates to a Node.js server through REST calls. Another Node instance runs locally within the company firewall and pings out to the cloud node server periodically. Any updates it detects are relayed to the Hue network through more REST calls. 

Relevant Blog Posts:

[My First Beacon App](http://dcinglis.wordpress.com/2014/06/27/my-first-beacon-app/)

[The Roll Call App](http://dcinglis.wordpress.com/2014/07/15/the-roll-call-app-integrating-beacons-with-node-js-and-mongodb/)

[Provisioning an iOS App](http://dcinglis.wordpress.com/2014/08/21/provisioning-an-ios-app-for-ad-hoc-testing/)

### [JSDO Proof-Of-Concept](https://github.com/progress/angular-jsdo-demo)
Progress uses their Javascript Data Object protocol for much of their backend data storage and transfer. This was a proof-of-concept to show that a Node.js server could access data exposed with this protocol and convert it into JSON form to be consumed by front end services. In this demo, a simple AngularJS site uses REST calls to access the data from Node and display it to the client in table form. 

Relevant Blog Posts:

[Displaying OpenEdge Data in an AngularJS Web App](http://dcinglis.wordpress.com/2014/08/19/display-openedge-data-in-an-angularjs-web-app/) 

### [Implementing JSDO in a Node Server](https://github.com/progress/jsdo-node)
With Node successfully able to read JSDO data, the logical next step was to expose data over the JSDO protocol in Node. Since Node is such a widely used platform and has such great flexibility through its modules, feeding a data source into Node is relatively easy. Then Node can expose data through the JSDO protocol to Progress backend services, since this is a data format they can easily process. Thus, Node acts as a go-between, connecting the front-end data collection to back-end data processing. 

Technology Breakdown:
Data is fed into Node by reading from a Mongo Database. Node reformats this data into the format specified by JSDO, then generates a catalog that describes the properties of each data field. The catalog, data, and an authentication service are all exposed to the end user through a REST API.


    