# Scenarios

## [Scenario 1](../blob/master/scenario1.md)

You have to deploy a web application, which will be accessed by the global Internet. Data exposed in that web app will include sensitive information about powerful people, so attacks are expected. The app has a high public impact, so there will be big fluctuations in traffic. App releases with new data are frequent. The app includes a form for sending information in a completely secure way to the app owner.

Design a system and communications architecture for deploying the application in production. Describe the external architecture (how the world views the system) and the internal one (how it is implemented) with all the technical details you can.

You can make assumptions, but you have to state them with your solution. You can draw diagrams by hand, take photos and attach them to the answer.

## [Scenario 2](../blob/master/scenario2.md)

You have to extract, transform and load graph data from 200K local HTML files into a Neo4j database, by:

1. scraping data points from the files
2. analysing the data
3. transforming the data
4. importing the data into the Neo4j database
5. testing/checking every process

Please, answer the following questions:

What ratios of expected work time would you give to each phase?
What tools, frameworks and programming languages would you use to do this?
You have to repeat this chain for up to five sources with different origin data.
What and how would you try to standardize in order to have more reusable code/tools?
You have three people to work on this, what would you assign to them? How would you communicate with each other?

Note we don't expect code, but known tools that solve these situations or a description of how would you design the project code in modules for different tasks. Anything that you can provide from an architectural perspective is valid.


## [Scenario 3](../blob/master/scenario3.md)

You have to lead your team while building a document search interface. The documents index (Elasticsearch) is located on ICIJ servers, accessible through a REST API. The interface your team have to create should run both on a website and a desktop application (for advanced usages this document doesn’t describe). The authentication system is already implemented in a separated server and is available through OAuth.

In order to accomplish your mission, you have to arbitrate with your team on the technologies stack you’re going to use for this interface. 

Describe (with words or a diagram) which technologies you’re going to use. The description should answer the following questions:

is your team going to code the interface twice (both for the web and the desktop)?
which frameworks or libraries would you like to use to build the interface?
which components would you build from scratch rather than using existing ones?

Please write down any questions that might occur to you while you’re elaborating
your plan (and you would ask if you had people to ask them to).