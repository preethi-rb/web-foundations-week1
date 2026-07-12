The Journey of a URL: 

There are mainly 5 steps:
    =>Find
    =>Connect
    =>Communicate
    =>Build
    =>Display


 Work FLow:

    1.User Enter URL:
        Browser Breaks it into 3 part 
        https://www.google.com/index.html
        here https => Protocol,
        www.google.com => Domain,
        index.html =>path

    2.Browser checks Cache:
        cache is the temporary storage place where the website resourses are stored
        It avoid unnecessary downloading of resources again and again
        resources like (HTML,CSS,JS)
    
    3.DNS lookup:
        After Entering the URL the browser should find the resources.
        using Domain name we can't connect with the server.
        DNS lookup is used to find the IP address of the domain name.
        
        There are some levels to find the IP address:
        Browser DNS Cache
        Operating System Cache
        Router Cache
        ISP DNS Server
        Root DNS Server
        Top-Level Domain (TLD) Server
        Authoritative DNS Server

    4.TCP - Transmission control Protocol:
        using the IP addredd the TCP will connect to the server
        It is simple giving the connection from browser to the server

    5.TLC/SSL :
        It gives a security to the Conversation between the Broswer and the server
        SSL - is the new security Protocol
        TCl - is the old security Protocol

        the server gives the data only after the browser sent the certificate.
        only the certificate is verified then the data will be shared.
    
    6.HTTP request : Hyper Text Transfer Protocol
        After all those thing now the HTTP from the browser will ask the website to the server. It send an msg,
            GET /index.html HTTP/1.1
            Host: www.example.com
            User-Agent: Chrome
            Accept: text/html

        GET is to get the data from index.html
        the domain name is www.example.com
        by using Chrome

    Server Process the request
            |
    HTTP will recevie the response
            |
    Then the browser will get the resources HTML->CSS->JS->images...
            |
    Render Tree

    7.Render Tree :
        It is the combination of DOM and CSSOM
        DOM says what are the elements should be displayed.
        CSSOM says how it should looks.

    After all those layout, painting, positioning the website will be displayed.


Takeway:

    =>Find (Get Domain from user --> find the IP of that domain)
    =>Connect (using IP connect with server by TCP)
    =>Communicate (after the certification by TLS,SSL the browser and server will communicate)
    =>Build (send the request through HTTP to the server and receive get resource)
    =>Display (after positioning display the website)