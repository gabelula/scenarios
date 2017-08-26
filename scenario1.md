
# Statement

You have to deploy a web application, which will be accessed by the global Internet. Data exposed in that web app will include sensitive information about powerful people, so attacks are expected. The app has a high public impact, so there will be big fluctuations in traffic. App releases with new data are frequent. The app includes a form for sending information in a completely secure way to the app owner.

Design a system and communications architecture for deploying the application in production. Describe the external architecture (how the world views the system) and the internal one (how it is implemented) with all the technical details you can.


# Answer

## On fluctations in traffic

Not sure how many fluctations are but something that can be done for hight traffic is to have more than one backend server and do load balance between them. 

## On securing the web

The webserver has to be configure with SSL to encrypt the requests to the server. 

## On sending information in a "completely secure way" to the app owner

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


Each node:

```

---------                    ------------
| Nginx |       ---->        | Database |
---------                    ------------
    
```

The databases are replicated. 