#ES6 (Better way of writing javascript)

6 Better ways of writing javascript

This blog is made with love and javascript

##1 : const and let keyword
const is a new keyword for declaring variables . a variable declared as 
const becomes immutable that means cannot be changed
let is also a new keyword and it makes mutable variables.

##2 : Arrow function

arrow functions are a new and better way of writing functions in javascript
 it makes the code more readable lets see an example

```javascript
let greeting = function(name){
       return "hello " + name;
    }
```
```javascript
let greeting = name => {
       return "hello " + name;
    }
```
As you can see the second code is more readable . The difference
between these two is that arrow function doesn't have its own this.

##3 : Template literal
we dont have to add concatenation (+) operator to concatenate strings
we can format strings using template literal 
let us take the same example

```javascript
let greeting = name => {
       return `hello  ${name}`;
    }
```

##4 : Destruction of array and object
Destruction allows us to assign values of array or objects to a
new variable easily  
```javascript
const user = {
    name : "sachin",
    id:123,
    age:18
};

let name = user.name;
let id = user.id;
let age = user.age;
```


now the es6 syntax of doing the same thing


```javascript
const user = {
    name : "sachin",
    id:123,
    age:18
};
let {name,age,id} = user;
```
same thing can be done with arrays
 
```javascript
const user = ["sachin" , 123 ,18];
let [name , id ,age] = user;
console.log(name);
console.log(id);
console.log(age);
```


##5 : Classes
Classes are the core of object oriented programming .They gives your
code a proper structure and make it more readable
```javascript
 class Yo
 {
     constructor()
     {
         this.super('yo')
     }
 }
```


##6 : Promises
Promise makes it easier to write asynchronous code It can be
used when let's say you want to fetch data from an API or if you have 
some statements in your code which are taking time to execute
```javascript
let promise = new Promise(function(resolve, reject){
     //do something
});
```

promises has 3 states 

1 - pending  : promise is pending means in progress

2 - resolved : promise is resolved

3 - rejected : promise is rejected

if the promise is resolved we can access its value then() block
and if its rejected we get error in catch() block

```javascript
//suppose this data is coming from an api
let age = apiData('/api/id/age'); 

let promise = new Promise(function(resolve, reject){
              if(age<18)
                  reject(new Error('cannot vote'));
              else
                  resolve('can vote');
    });

promise.then(result=>console.log(result))
       .catch(err=>  console.log(err))
```


