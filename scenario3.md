# Statement

You have to lead your team while building a document search interface. The documents index (Elasticsearch) is located on ICIJ servers, accessible through a REST API. The interface your team have to create should run both on a website and a desktop application (for advanced usages this document doesn’t describe). The authentication system is already implemented in a separated server and is available through OAuth.

In order to accomplish your mission, you have to arbitrate with your team on the technologies stack you’re going to use for this interface. 

Describe (with words or a diagram) which technologies you’re going to use. The description should answer the following questions:

* Is your team going to code the interface twice (both for the web and the desktop)?
* Which frameworks or libraries would you like to use to build the interface?
* Which components would you build from scratch rather than using existing ones?

Please write down any questions that might occur to you while you’re elaborating
your plan (and you would ask if you had people to ask them to).



# Answer

Stack:

* React.js
* Electron.app for Desktop

### Is your team going to code the interface twice (both for the web and the desktop)?

*The interface will be code once in React.js AND then use electron to pack it for the desktop.*

### Which frameworks or libraries would you like to use to build the interface?

* React.js to build the interface
* Flux Architecture through Redux
* An oauth library to build the strategy to connect to the oauth server

### Which components would you build from scratch rather than using existing ones?

Now I doubt if there is any other component that needs to be done that can not be accomplished with the technology proposed.