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

200:OK\
201:Created\
202:Accepted\
203:Non-Authoritative information\
204:No content

400: Bad Request\
401: unauthorized\
403: Forbidden\
404:Not Found\
409: Conflict

500: Internal Server Error\
501: Not implemented\
502: Bad Gateway\
503: Service Unavalable\
504: Gateway Timeout\
599:Network Timeout

# To create our own API need to install following software
NODEJS
check node using = node --version\
check npm using = npm --version\

using using node run json-server\
npm install -g json-server\
insall json server

*********************************************************************

# JSON
********\
Java Script Object Notation\
it is s syntax for storing and exchanging data\
it was designed for hum readable data interchange\
json is text, written with java script=object notation\
it has been extended from the javascript scripting language\
extinstion is .json

## Json Data type
Number\
String\
Boolean\
Null\
Object\
Array

Note:\
Json file should be presented in key and value pair

### String
Strings in JSON must be written in double quotes.\
{\
"Name":"Sachin"\
}

### Number
Numbers in JSON must be an integer or a floating point.\
{\
"age":30\
}

### Object
Values in JSON can be objects.\
{\
"employee":\
{\
"name":"Batman",\
"age":30,\
"city":"Gotham"\
},\
		{\
			"name":"Superman",\
			 "age":33,\
			 "city":"Metropolis"\
		},\
		{\
			"name":"wonder woman",\
			 "age":38,\
			 "city":"Themyscira"\
		},\
}

To get the individual data\
employee[1].name

### Array
Values in JSON can be arrays.\
{\
	"employees":["John", "Anna", "Peter"]\
}

### Boolean
Values in JSON can be true/false.\
{\
	"sale":true\
}

### Null
Values in JSON can be null.\
{\
	"middlename":null\
}

***********************************************
# Response Validation
*******************
1) Status code\
2) Header\
3) Cookies\
4) Response time\
5) Response body

Assertion - Validation 

Uses pm library\
with in pm there are function which is written in java script

## Function
-------------
Normal Function\
Arrow Function

Chai Assertion Libray\
Normal Function\
pm.test("Test Name", Function(){\
// Assetion:\
}\
);

pm.test("Test Name", ()=>{\
// Assetion:\
}\
);


## Validating the status code
-------------------------------\
Test for the response status code:\ 
pm.test("Status code 200", ()=>{\
pm.response.to.have.status(200);\
});

## If you want to test for staus code being one of a set include them all in an array and use one of
pm.test("Successfull POST request", ()=>{\
pm.expect(pm.response.code).to.be.oneOf([201,202]);\
});

## Check the status code text
pm.test("Status code name has string", ()=>{\
pm.resonce.to.have.status("Created")\
});

## Testing Header
------------------\
### check that a response header is present
pm.test("Contant type header is present", ()=>{\
pm.response.to.hace.header("Content-Type")\
});

### Test for a response header having a particular value:
pm.test("Contant type header is application/json", ()=>{\
pm.expect(pm.response.headers.get("Content-Type")).to.eql('application/json');\
});

## Testing Cookies
--------------------
### Test if a cookie is present in the response
pm.test("Cookie 'Language' is present", ()=>{\
pm.expect(pm.cookies.has('language')).to.be.true;\
})

### Test for a particular cookie value

pm.test("Cookie Language has value 1", ()=>{\
pm.expect(pm.cookies.get('language')).to.eql('en-gb');\
});

Testing Response times
----------------------------
### Test for the response time to be within a specified range:

pm.test("Responsetime is less than 200ms", ()=>{\
  pm.expect(pm.response.responseTime).to.be.below(200);\
  });

Testing Response Body
---------------------


## Asserting a value type
---------------------------
### Test the type of any part of the response
    {
        "id": "2",\
        "name": "Jane Smith",\
        "location": "Los Angeles",\
        "phone": "+1 (987) 654-3210",\
        "courses": [\
            "History",\
            "Biology",\
            "Chemistry"\
        ]\
    }\
    const jsonData = pm.response.json();\
    pm.test("Test data type of the respose", ()=>{\
    pm.expect(jsonData).to.be.an("object");\
    pm.expect(jsonData.name).to.be.a("string");\
    pm.expect(jsonData.id).to.be.a("number");\
    pm.expect(jsonData.courses).to.be.an("array");\
    }\
    )
