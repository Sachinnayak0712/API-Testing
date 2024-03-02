# API Testing
API Introduction
**************************

## Client :- computer hardware device or software that access a service made available by a server\
## Server:- Server is a remote computer which provides information (data) or access to particular services.

## API:
Application Programing Interface: is a way to communication between 2 application where application may differ in ther platform/technology

## Difference between API and Webservices
### Web Services
All web services are APIs\
requred network or internet\
uses XML to data exchange

### APIs
not all APIs are web services\
does not necessarily need a network\
uses JSON


## Types of API
Simple objject access protocoal\
Rest(Representational state transfer)

## REST APIs HTTP method
*************\
Rest API methods / HTTP Requests

get - get the response from the server\
post - add new information into server \
put - Edit or update informarion in the server\
Patch -  Update partiial detail of resource\
delete - Delete infromation from ther server\

## HTTP vs HTTPS
*****************
### HTTP
HTTP- HyperText Transfer Protocol
works at application layer
No encryption is present

### HTTPs
HTTP- HyperText Transfer Protocol Secure
works at Transport layer
Both encryption and Decrption is present


## Terminologies
URL - uniform resource locator

## URL Detail
https://google.com/articles/articlename\
https:// = Scheme\
google.com/ = Host\
articles/articlename = PATH

## Resource and Feature
Feature is the term used in maual Testing to test some functionality
Resource is the term used in API Testing refering some functionality

## Payload
body in the HTTP request and response message
Request Payload 
Responcse Payload

## URL  
https://reqres.in/api/users?pages=2
https://reqres.in/ = Host Domain
api/users = Path Parameter
?pages=2 = Queary Parameter


## HTTP Status Code
![HTTP-Error-Codes](https://github.com/Sachinnayak0712/API-Testing/assets/66566069/4783246f-3158-486b-bc0e-b0fc4ed5031b)

3 different level
200:OK
201:Created
202:Accepted
203:Non-Authoritative information
204:No content

400: Bad Request
401: unauthorized
403: Forbidden
404:Not Found
409: Conflict

500: Internal Server Error
501: Not implemented
502: Bad Gateway
503: Service Unavalable
504: Gateway Timeout
599:Network Timeout
