# two-tear-demo

This is a demo of 2 tier application stack with Nginx as a Edge tier, terminating SSL and checking for the client cert. 
Once the handshake finished, Nginx sets the CN name of the client cert in one of the http headers of the downstream. The downstream server is implemented in javascript (express) and java (springboot)