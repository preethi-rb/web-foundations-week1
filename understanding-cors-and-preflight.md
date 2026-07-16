CORS: Cross-Origin Resources Sharing:
    =>It is a browser safety measures,that controls the website from one origin can be access the resources of other origin.
    =>It product the website from, accessing the unauthorized website to get thier data.

Origin :
    =>Unique identity of an website
    https://www.amazon.com//20045
    https ->Protocol
    www.amazon.com ->Domain
    20045 ->Port

Same-Origin:
    https://www.google.com/home  and https://www.google.com/profile are Same-origin.

Cross-Origin:
    https://google.com and http://google.com are Cross-origin.

Cross-Origin Request:
    =>It happens when the differnt origin needs to access the data.
    =>whenever the Cross-Origin happens ie, different(port,domain,protocol) consider as the request count.

Simple Request :
    => It looks safe , so the browser sent the request directly to the server request is consider as simple only if it contains GET,HEAD,POST, request headers and content-type.  
    
Preflighted Request :
    => before send the acutal request to the server the brower first sent the OPTIONS request if server accept it then browser will sent the actual request. 
    =>To be a preflighted request it should not be a simple request like it should have Methods like PUT,DELETE,PATCH and custom headers.

Why Postman not in Browser:
    =>CORS is enforced by the browser, not by the server.
    =>Postman and curl do not enforce the Same-Origin Policy.
    =>If the request doesnot matches the browser stop the javascript but the Postman simply shows the error.

1) Simple GET (no preflight, allowed)
Cross-origin GET to a permissive API (CORS enabled with Access-Control-Allow-Origin: *).
    OPTIONS REQUEST : Only simple GET request is passed so no OPTIONS REQUEST.
    MAIN REQUEST : It is shown "304 Not Modified" so it is SUCCEEDS.
    CORS error message : No,bec the request succeeded 
    REQUEST HEADER: shows the methos GET so it is simple cross-option.
    RESPONSE HEADER : sec-fetch-mode : cors, this tells that the browser says it making cross-origin resourses making.

2) Use a “simple” Content-Type (application/x-www-form-urlencoded) so the browser does not preflight.
    OPTIONS REQUEST:Only simple POST request is passed so no OPTIONS REQUEST
    MAIN REQUEST : 201 Created so it is SUCCEED.
    CORS error message : No,bec the request succeeded.
    REQUEST HEADER : Content-Type: application/x-www-form-urlencoded so it is consider as simple request.
    RESPONSE HEADER : origin : null means the file opens in desktop locally and sec-fetch-mode : cors, this tells that the browser says it making cross-origin resourses making.

3) Use Content-Type: application/json to force a preflight OPTIONS before the POST.
    OPTIONS REQUEST: Yes,There is an option request that appeared before post request.
    MAIN REQUEST : 201 Created so it is SUCCEED.
    CORS error message : No,bec the request succeeded.
    REQUEST HEADER : method/path - OPTIONS /posts so it is preflight
    RESPONSE HEADER : access-control-allow-methods :POST and access-control-allow-headers : content-type and access-control-allow-origin:null it is file://

4) Add credentials: 'include'. With ACAO: *, the browser blocks credentialed requests.
    OPTIONS REQUEST: Yes,There is an option request that appeared before post request.
    MAIN REQUEST : 201 Created so it is SUCCEED.
    CORS error message : No,bec the request succeeded.
    REQUEST HEADER :OPTIONS /posts
                    Origin: null
                    Access-Control-Request-Method: POST
                    Access-Control-Request-Headers: content-type
    RESPONSE HEADER:Access-Control-Allow-Origin: null
                    Access-Control-Allow-Methods: GET, HEAD, PUT, PATCH, POST, DELETE
                    Access-Control-Allow-Headers: content-type
                    Access-Control-Allow-Credentials: true
    =>In this case the page says "should be blocked", the request was not blocked because the server returned valid CORS headers:
                    Access-Control-Allow-Origin: null
                    Access-Control-Allow-Credentials: true


Part - 2
Access-Control-Allow-Origin: * doesnot allows :
    Access-Control-Allow-Origin: * allows every origin only for requests without credentials.
    => Access-Control-Allow-Origin: http://localhost:5500
    Access-Control-Allow-Credentials: true

    Not Accepted :
        Access-Control-Allow-Origin: *
        Access-Control-Allow-Credentials: true

Takeaway: 
    CORS : Security mechanism That controls the webpage to access form one origin to another origin.
    Origin : Protocol + Domain + Port.
    Cross-Origin Request : Happens when the different origin needs to access the data.
    Simple Request: Same Origin The request to access.
    Preflighted Request : webpages that need to access with different origin.
    

