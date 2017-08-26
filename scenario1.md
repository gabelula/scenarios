
# Statement

You have to deploy a web application, which will be accessed by the global Internet. Data exposed in that web app will include sensitive information about powerful people, so attacks are expected. The app has a high public impact, so there will be big fluctuations in traffic. App releases with new data are frequent. The app includes a form for sending information in a completely secure way to the app owner.

Design a system and communications architecture for deploying the application in production. Describe the external architecture (how the world views the system) and the internal one (how it is implemented) with all the technical details you can.


# Answer

To build a secure web application the most important thing is to look at threat modeling. Try to identify all the ways that an intruder may access or change the data.  I'm assuming that this is all data that can be public. Or is the data behind an authorization service? Who can access this data?

## On fluctations in traffic

Not sure how many fluctations are but something that can be done for hight traffic is to have more than one backend server and do load balance between them. 

## On securing the web (secure your host)

The webserver has to be configure with SSL to encrypt the requests to the server. The server has to be secure.

## On sending information in a "completely secure way" to the app owner (secure your communication)

Not sure if what they mean here is that they need to receive data in an anonymous way or not.  If that is the case then the best tool right now is Secure Drop to receive information in a secure way. The Secure drop will be integrated in the same domain with instructions for the clients on how to use it.


```
                                       --------------------                   --------
-------------                          |                  |                   |      |
|   Client  |       ------->           | Load Balancer    |    ---------->    | Node |  
-------------                          | (SSL by default) |    \       .      |      |
                                       -------------------      \      .      --------
                                                                 \     .
                                                                  \
                                                                    --------
                                                                    |      |
                                                                    | Node |
                                                                    |      |
                                                                    --------
```           


Each node (secure your application):

```

---------                    ------------
| Nginx |       ---->        | Database |
---------                    ------------
    
```

* The databases are replicated. There will be a master node with its primary database. This is the database that is being updated when needed. Databases can only be acceded from the local server.  
* Exception management should be considered. Be careful about what is revealed when the application fails.
* Logging is an important part of the equation when securing a web application. We need to be able to do forensic analysis when there are problems.