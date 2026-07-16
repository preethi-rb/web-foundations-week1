HTTP:
    =>HTTP is the language used to communicate between sever and browser.
    =>Browser sents the HTTP request and server gives the HTTP response.

HTTP methods:
    =>IT simply says what action it should be performed.
    GET : It retrive the data from the server
    POST : It give the data to the server from the browser.
    PUT : It update the data in the database server.
    DELETE : It delete the data in the server.

HTTPS status code:
    =>It tell what status does the request and the response is,
    1xx : Informational
    2xx : Success
    3xx : Redirect
    4xx : Client Error
    5xx : Server Error

HTTP headers:
    =>It is the meta data , that tells how to process the request and responds.
    =>It is a key value pairs

what is an API:
    =>It is basically a intermediate between the brower and the server.
    =>with API the broswer can't share it data directly from the server to the broswer,
    =>API is the one who will take the data from the server and give it to the browser.it will checks the authentication .

REST API:
    =>here the REST follows a set of rules ie, everything it will treated a Resources.
    REST API is the set of endpoints that allow broswer to communicate with the server through the HTTP methods like GET,POST,PUT,DELETE.

ENDPOINT:
    https://jsonplaceholder.typicode.com/users , here the endpoint is users, it says give all the users that is in the resources.


JSON :
    =>javascript object notation.
    =>JSON is used to store and exchange the data between the browser and server.
    =>it is a text-based language.

JSON differ from JS object:
    =>javascript object is programming language it contains Variables,Function..
    =>but,JSON is just a text-based language not a programming language.

Why JSON:
    =>browser sent the request in JSON because all programming language can understand the JSON based data.it is also lightweighted .

Why not XML or Plaintext:
    =>It is a hierarchical model.
    =>plain text will be confused which is key and value.
    =>compare to XML, JSON is easier,faster

 Exploring a Public REST API:
    =>Using POSTMAN tool and using JSONPlaceholder public API.
    Base URL : https://jsonplaceholder.typicode.com
    GET Method:
        Request URL:https://jsonplaceholder.typicode.com/posts/1
        Response:
            {
                "userId": 1,
                "id": 1,
                "title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
                "body": "quia et suscipit\nsuscipit recusandae consequuntur expedita et cum\nreprehenderit molestiae ut ut quas totam\nnostrum rerum est autem sunt rem eveniet architecto"
            }
        status code: 200K
        Header Recived .
    POST Method:
        request URL:https://jsonplaceholder.typicode.com/posts
        Body -> raw-> JSON :
            {
                "title": "Learning REST API",
                "body": "This is my first POST request.",
                "userId": 1
            } 
        Response:
            {
                "title": "Learning REST API",
                "body": "This is my first POST request.",
                "userId": 1,
                "id": 101
            }
        status code:200K or 201
        Headers :Content-Type : application/json; charset=utf-8
    
    PUT method:
        Request URL:https://jsonplaceholder.typicode.com/posts/1
        Body -> raw-> JSON :
            {
                "id": 1,
                "title": "Updated Title",
                "body": "Updated Body",
                "userId": 1
            }
        status code:200K or 201
        Headers :Content-Type: application/json; charset=utf-8

one header you observed during your API testing :
    Content-Type: application/json; charset=utf-8
    It is important bec,It says the browser ,in which format does the response is.


Takeway:
    API gives the response to the server
    HTTP is the language to communicate with server and browser.
    REST API it takes everything as a response by the group of URL with the endpoint.
    HTTP method : GET,PUT,POST,DELETE.
    HTTP status : 1xx,2xx,3xx,4xx,5xx.
    JSON : the language by which all the server can understand it, it is text-based has keys and value.
    POSTMAN : the platform used for API testing and development.







