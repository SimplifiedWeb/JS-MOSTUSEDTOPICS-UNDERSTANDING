# JS Most Used Topics - Understanding

## Focus on Topics: Flows, Scopes, and Working

1. var, let, const

   Always Remember var gets Hoisted at the top of the Scope. Also, regular Function, not expression and arrow Function.
   Why? That's because of historical reasons. Like, previously, developers used the concept of hoisting to make variables and functions easily accessible.
   They are available to the entire scope, encountering errors. 
   And we know let and const give us errors before initializing, using strict checking.

2. This Value

   Always Remember this value refers to the window object by default. In constructor functions, when a new object is created using the new keyword, this value refers to that newly created object. For events, this value points to the current target element. And for functions, this value inside the function points to the window object when the function doesn't contain any objects. 
   So, the clear idea is, when you're using an event, you know now it points to the current element; for constructor functions, you know now it points to the object that was created by the new keyword. For example, const result = new Person("faizan", 32), so the Person object was created, and this value points to that. So always remember that whenever you see the this value, you'll get the idea. First, check the function, new keyword, events, call, apply, bind methods; they also use the this value. So you check who's giving the this value, and by that, you'll get an idea.

3. args in functions

   function(...args) simply gives us an array-like object that contains all the passed parameter values. It has a length property, and typeof is an object. That's because it's not a fully-fledged array.

4. Closure

   Simply understand that closure is used for private data or security. Like, we cannot access data directly; we'll have to get the data by some kind of function calls. We can call it data encapsulation.
   So, a function inside a function, when it gets returned, it takes all the values of outer functions and gets returned. Right. But now we know why, right? If you know the concept of get and set methods in object-oriented programming, you will get an idea of what I'm talking about. It's just a concept, like example, we create a function that contains balance as a variable. And one function is used to set the balance, and one function is used to get the balance. So we can't directly access the balance variable; we want to call a function like a get function to get the balance, or we want to update the function; we call the set function, giving them some arguments to update the balance value like that. Now, you understand it clearly. So when we call the function, it takes the values from the outer functions and gets returned. Like set function (balance = balance + num) and get function (return balance) like that.

5. Polyfill 

   So this topic is always asked in interviews. Polyfill simply means a piece of code that we use to build our custom things.
   And this polyfill piece of code is used to run in all the browsers, including the oldest versions of the browser. Like we want to build our custom filter array method, then we can build one. Using the Prototype.

6. Prototype

   First, keep in mind that the prototype is a blueprint that sits behind all the properties and methods. Like the push, pop, object properties, etc. We declare 100 arrays; then 100 arrays have their push, pop, shift, etc., all the methods, right? We have to declare them and use all the methods. So behind the functionality, we can call it a prototype that's sharing the same piece of code with all 100 arrays. We write it once and share it all over. It takes a reference to objects, arrays, etc. So call, apply, bind methods are only written once, so only the prototype gets a reference to it. And we can't directly add functionality inside a prototype; I said your prototype just gets a reference to the methods that are written underneath the hood.

   LIKE FOR ARRAYS, THE CODE WRITTEN UNDERNEATH THE HOOD, PROTOTYPE JUST GETS THAT CODE REFERENCE AND USES IT FOR ALL THE ARRAYS, YOU UNDERSTAND NOW. PROTOTYPE SITS IN THE MIDDLE, TAKES ALL THE REFERENCE, AND WE CAN USE IT. SAME FOR OBJECT, ETC.

   So we can't add functionality inside the prototype. If we want to add functionality, we want to first make an object constructor function using the new keyword. Then we can add the functionality there. Just use the constructorName.prototype.added = function() {} like that.

   Now you understand what is a prototype and why we use it.

   So on the previous polyfill topic, I said that we create our custom filter using prototype; now you get an idea. First, we have to write a piece of code and then connect it with the prototype so that it's going to take reference, and we can use it 1000 times, and it just references code from this.
   Like we use it as Array.prototype.customFilter = function(callback) {} like that.

7. Event Loop, Execution Context, Microstack, and Callback Queue.

   Firstly, for loop, function, block statement are all synchronous ways. And setTimeout, fetch, promises are all asynchronous.
   Execution Context - where all the execution is done.
   Microstack - contains promises and other executions.
   Callback - contains setTimeout, fetch, etc. executions.
   Event Loop - decides and controls or manages the execution of asynchronous ways.

   So, in the Execution context, when all the synchronous operations are done, the Event Loop takes asynchronous operations one by one in a step-by-step manner. That's all you have to understand. For a function, an execution context takes place within the execution context and gets released after its job is done.

   And Remember that inside the execution context, an object container is created that stores all the var keywords and function declarations. That's pointing to some values.

8. Fetch API

   So basically, it is used to handle network requests in a promise-based manner. I think I don't need to explain promises, right? That's because promises are easy; you just want to understand the flow of that and chain the .then property. Not a big deal. So, we have different methods, headers, request, and response objects.

   Methods - post, get, put, delete.
   Headers - like what type of content we are sending, what type of content we are going to accept from the server, we send the cookies and tokens to verify, etc.
   Response and Request objects contain all of their headers, methods, status codes, etc.

9. Reduce Method of Array

   So basically, we have to understand the Flow of its working, how it takes and uses the value.

   let num = [1, 2, 3, 4]
   we use num.reduce((accumulator, currentValue) => {}, 0)
   like that,
   So in simple telling you, we can say that the accumulator is a collector. and currentValue is the current value.
   So accumulator is pointing to 0, and currentElement pointing to 1.
   if I do accumulator + currentValue what will happen 0 + 1 = 1 so the accumulator is 1 now, next time currentValue is going to be 2 and then 1 + 2 = 3 so the accumulator is 3 now, you're getting it we are just iterating the currentValue not the accumulator, it just used to store the calculated value and currentValue is iterating one by one and Updating the Accumulator. That's how the working is going on, If I increase the initial value of accumulator that's pointing to 0, that's because we put 0 in that function if I change 0 to 100 that the initial value of accumulator should be 100. That's how the correct working is going on; some people think it like the first value inside the array is going to point to accumulator, and the second value is going to point to currentValue no that's is wrong.

10. Arrow Function

    For this, you have to understand that the this value refers to one step upper scope, not on the current scope. So if we try to declare and use the this value within its scope, it's going to give you an error; it always inherits the this value from one step upper; we often said it's the lexical environment.
    That's all you need to understand; because other things are the same, check out the syntax and return values in this function.

11. Difference between async/await and promises

    Simply, Understand that Async/await is an upper layer of promises. Underneath the hood, they are working as promises. This is made more easy to understand and more readable code. using Async/await there is not any other functionality difference they work both the same.
    just it makes code more manageable, readable and short.

12. Webpack and Babel

    Now simply understand this also, Webpack is used to bundle all the files into one, to make performance much faster,
    And Babel is used to convert ES6 code into ES5; we can write the most updated code; babel gets converts it into a suitable form.
    So in react, we write jsx; in that also, bable gets converting it into its usual form; you can copy the code and paste it on the bable official website; you can see there the actual code underneath the hood.
    Now, we have to set up this webpack and babel in javascript, but in react, babel is automatically converting the code. Underneath the hood.
    we have set up configure Webpack.

    Now you have the knowledge of what this is; you can search and see how to configure and use it more efficiently.

13. Something You Should Have to Know,

    When declaring a for loop with the var keyword, its value gets hoisted, and when we use any asyncronous operations or method inside there, we are going to get the hoisted value, and that value should be the same that because async value gets the value after the sync is completed means the for loop.
    so after the loops complete, it takes the hoisted value; so if the loop runs 10 times, then the last value gets printed 10 times.
    but on let, const the output should be different that because each time let or const gets created new, each time the loops complete its iteration. so if it runs 10 times then let or const created 10 times in memory that has its values, that is how the asyncronous operations or function prints different values.

    Same for function, each time when we call a function each time a new function scope is created with new variable values so it doesn't matter what calculation we do inside there the value reset to the default value and start again, so each time the function call new function scope is created and new variable and other things get created with their by default respective values and start again the calculation.

    Take this example you can understand it better,

    ```javascript
    function outerFunction() {
      let x = 0;
      function innerFunction() {
        setTimeout(() => {
          console.log(x);
        }, 1000);
      }
      x++;

      return innerFunction;
    }

    const innerFunc1 = outerFunction();
    const innerFunc2 = outerFunction();
    const innerFunc3 = outerFunction();
    const innerFunc4 = outerFunction();

    innerFunc1(); // Output: 1 (after 1000ms)
    innerFunc2(); // Output: 1 (after 1000ms)
    innerFunc3(); // Output: 1 (after 1000ms)
    innerFunc4(); // Output: 1 (after 1000ms)
    ```

    You Can understand this Code. Return function gets stored and called.

14. I Created A DOM user Interaction properties like clientWidth scrollX getBoundingClientRect, etc., Earlier. Go and Check out The Repository. I Guarantee you that the topics I explain in my way you can understand them better, the ones I struggled with to understand and use properly.

15. TextContent, innerHTML, innerText, querySelector, nextElementSibling, setAttribute.

    TextContent and innerText Text both are used to access the text of an element. like <h6>Hello Hii there</h6> So if I want to access the text, I'll use textContent or innerText. The Difference is TextContent Can't be modified directly, but innerText can be modified directly. So TextContent use for read-only purposes; we can't modify it. But for innerHTML we can modify it.

    And For QuerySelector, we know it gives us a nodeList. So it is an array-like object, not an actual array. remember that but we can use Foreach loops, 
    so htmlCollection jo getElementBy Whatever we use property using this, they give us htmlCollection.
    So the difference is htmlCollection can't use directly loop like forEach we have to make them first an array after that we can use them but nodeList can use directly ForEach, both can update dynamically when something changes like added or removed it should be updated automatically both the properties.
    nextElementSibling, childNodes they are just like who is next to me we use nextSibling, or childNodes we know that.
    classList, toggle we know that it's not that hard to understand this.
    Yes that's it, we use this most of the times. like we use setAttribute in major cases we have to just define like setAttribute('id or class', "then class or id name") we use different attributes too. like src href, etc. for removeAttribute just pass the name what attribute you want to remove like which class or id you wanna remove like that, you can remove any attribute you want just passed the attribute name of the target element.

16. Set and Map methods

    Always remember Set methods don't contain duplicated values
    Set always stores the unique values, and it has an order that maintains. And set only contains values, not keys. And basically, we will make it an array and use it to get or store only the unique values [...new Set(arr)] like that.

    Map stores the key-value pairs. It also maintains the order. They both are the collections that store values and use different methods like add, delete, length, has.

    JSON topic is easy, right? we have two things parse and stringify. and we know how it works, doesn't need me to tell you about it.

17. And Don't Get Confused By higherOrderFunctions; this is just a name,
    filter, reduce, map, foreach, setTimeout they all are higherOrderFunctions, A function that contains a function as arguments or return a function that we call a higherOrderFunction. Basically, it makes code reusable, modular, and maintainable.
    modular simply means small small modules or pieces of code that can be organized, reused, and maintained.

18. There is a function called IMMEDIATELY INVOKED FUNCTION (IIFE)

    so it executes immediately when we execute our code, but keep in mind when we put this function inside another function, then it should not get run until the outer function gets called. So remember that. And also, it's going to execute line by line, not that if I called the outer function, the inside IIFE function runs instantly no, it runs step by step from top to bottom. It should be asked in an interview, remember that.

19. Other Array methods are easy, only the reduce function has something I get a hard time with, so I explained that above.

20. And other things like Math function precision, toFixed, ceil, round, floor.
    simply Precision is simply how many digits we want like 23.3445 so I want 2 digits so it is 23. toPrecision(2)

    
    toFixed how many digits we want to remove from the decimal point. like 23.2442 I want 2 digits it is 23.24 like that

    
    ceil is for the greatest value 34.335 so it is 35.

    
    floor is for the nearest value 343.533 so it is 342

    
    round is for above 5 or above it should be greater if not then smaller.

21. Date and time

   so first understand this,
   1. Hour => 3600 seconds and 60 minutes
   2. 1 day => 86400 seconds and 1440 minutes
   3. 1 minutes => 60000 miliseconds 60 seconds.
   4. 1 second => 1000 miliseconds

    Now, 1000 * 60 * 60 * 24 = 86400000 Number of seconds in a day.
    basically 1000 is used for converting seconds into miliseconds. that bcz 1 seconds = 1000 miliseconds.

    Now new Date(year, month, day) we know that, if someone gives us a program to find out how many days is left for upcoming christmas.
    How we're gonna do that. 
    - we have to first find how much time is remaining, from today to chritmas day. 
    - we have to find out one day of time in miliseconds.
    - we have to check does the christmas is over and set to the next year for dynamic changes.
    - the we have to substract the value that we get from today to chritsmas day from current time and dividing it by milisecond of a day we get our answer.

    It's not that difficult like you get the time remain for christmas is cmas = new Date(today.getFullYear(), 11, 25) like that. you can do with your own.


So watever i epxlained you i get a hard time to understand that properly something i can't understand earlier something i can't remember that, so this explanation helps you and me.

