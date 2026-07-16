Local Storage:
    =>It is a Permanent Storage place, Only disapper when we delete the storage ,it doesn't goimg to be disapper while switching tab, closing tab abd shutdowning the system.
    =>It stores the information like dark/light mode,language and recently used item.
    =>size limit : 5 to 10MB.

Session Storage:
    =>It is a temporary storage place where the data will be disappear when the browser closed or opened in new tab .
    =>The storage is 5MB.
    =>used to store data like Registration form, Quiz before summition.

Cookie:
    =>It works on both browser and server side.
    =>The server create a authentication token and send the cookie to the browser through the response header and the browser will store the data in thzat cookie and sent alon with the matching HTTP request.
    =>size limit : 4KB per cookie.
    =>mainly used for the authentication and login in session.

IndexedDB:
    =>It is a broswer DB where it stores the large amount of structured data.
    =>It can store Javascript array,list,object.
    =>Used when the application stores large dataset like google docs,WhatsApp webpage..
    =>size limit 5 to 10 MB.

Cache API:
    =>Cache stores the network resourse like HTML,CSS,JS rather then reloading every time.
    =>It is mainly used by server workers, it decide When to load, which file should store and to use cache or to fetch new one .
    =>It simply speed up the website loading.

PRACTICAL SESSION :

LocalStorage:
    =>localStorage.setItem("name","Preethika");
    =>localStorage.getItem("name");
    =>The data will be their utill manually deleting the data.

Session Storage:
    =>sessionStorage.setItem("course","javascript");
    =>sessionStorage.getItem("course");
    =>by closing the tab, the data  will be erased.

cookie:
    =>documnent.cookie("username=Preethika");
    =>automatically give the stored data in the cookie.

IndexedDB:
    =>The browser can stored more data in this DB.
    let request = indexedDB.open("StudentDB", 1);

request.onupgradeneeded = function(event) {
    let db = event.target.result;

    let store = db.createObjectStore("students", {
        keyPath: "id"
    });
};
request.onsuccess = function(event) {
    let db = event.target.result;

    let transaction = db.transaction("students", "readwrite");

    let store = transaction.objectStore("students");

    store.add({
        id: 1,
        name: "Preethika"
    });

    console.log("Record Added");
};

storage types persist across sessions:
    =>Except session storage all the other are persist across sessions.
    =>The types are LocalStorage, IndexedDB, CacheAPI and cookie.

storage types are automatically sent to the server:
    =>The cookie will automatically send from browser to the server.

storage type is most secure for sensitive information.
    =>The most secure one is cookie because it send the data through HTTP request and response.

storage type is best for large datasets:
    =>Indexed is the best type to store the large data types bec it contain larger dataset.It cab store the largest data's contain list,array,object,etc.

Be avoided for authentication tokens:
    =>the types that are avoided for authemtication token are localstorage and sessionStorage, bec the both can be accesed by Javascript for attackers can easily take the data only using the HTTP securethe data.

Browser Storage:
    =>Allow the website to store the data in the user's device.
    =>there are different types ofstorage localstrorage- only manual delete will disapper the data, sessionstorage-refreshing the website the data will disapper., indexedDB can store the large data, that has complex javascript array,objects. cookie that send the data through HTTP request si it is safer one. Cache API it stores the resource like HTML,CSS,JS so it will reduce the loading time of the webpage.   