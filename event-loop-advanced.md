JavaScript call stack:
    =>It is simple a order of the execution of code.
    =>It acts on the principle of last in first out(LIFO)
    =>Flow

        global execution context is created --> go into the stack --> complete execution --> removed from the stack

MicroTask & MacroTask - It is a event loop (says the event of the execution)
    =>MicroTask has high pirioty then macroTask.
    eg event of microtask: promise.then()it will execte only after the Promise.resolve() is fullfilled.

    =>MacroTask after all the exection of microtask will be proceed.
    eg : setTimeout().

queueMicrotask(), and setTimeout() behave differently in execution order because:
    =>queueMicrotask() is a microTask
    =>setTimeout()is a macroTask


How the event loop decides what runs when,   
it can be answered simply that:
    
    function calls --> syn code --> microTask --> macroTask --> End


Exercise 1 – Microtasks vs Macrotasks

console.log('1');                  //syn code

setTimeout(() => {                 //macro
   console.log('2');
}, 0);

Promise.resolve().then(() => {     //micro
   console.log('3');
});

queueMicrotask(() => {             //micro
   console.log('4');
});

console.log('5');                  //syn code

Output:
    1       //It is a Synchronous Line
    5                "
    3       //It is a microTask as there is 2 microTask it will execute the first microTask
    4       //It is second microTask 
    2      //It's a macroTask

Describe how the event loop handles each of them:

step :1 the Synchronous code will go into callStack
step :2 complete the code in the callstack and remove the code
step :3 event loop move all the microTask into the callstack for the execution
step :4 after the completion of microTask in the callstack the  event loop move macroTask into callstack
Step :5 at last the event loop will check is there any new entry is yes the same will be repeated.


Exercise 2 – Nested and Sequential Tasks

console.log('start');

setTimeout(() => {
   console.log('setTimeout 1');
   Promise.resolve().then(() => console.log('Promise 1'));
}, 0);

setTimeout(() => {
   console.log('setTimeout 2');
}, 0);

Promise.resolve().then(() => console.log('Promise 2'));

console.log('end');

Output order:

    start      
    end
    Promise 2
    setTimeout 1
    Promise 1
    setTimeout 2

explanation:

console.log('start');           //Synchronous code is added to callstack 
setTimeout(() => {              //event loop will move MacroTask to callstack
   console.log('setTimeout 1');
   Promise.resolve().then(() => console.log('Promise 1'));    //inside the macro the same flow will be follws syn->micro->macro
}, 0);
setTimeout(() => {             
   console.log('setTimeout 2');       //event loop will move MacroTask to callstack
}, 0);

Promise.resolve().then(() => console.log('Promise 2'));     //event loop will move MicroTask to callstack

console.log('end');   //Synchronous code is added to callstack



Key Takeaways :

Execution order:
    =>Synchronous code is executed first.
    =>MicroTask is executed after the synchronous code.
    =>MacroTask is executed after the MicroTask.

Async behavior:
    =>bec of some issues like network problem the execution can be terminated this is called Asynchronous to avoid this can you events like SetTimeout()

How it affects real projects 

    It make the application more faster in the usage of fecting the API's, uploading the files, getting data from another website and so on.
