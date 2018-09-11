# javascript-questions

### 1. What are Closure, Lexical Environment & Execution Context in javascript ?
Closure: In JavaScript, closures are created every time a function is created, at function creation time. To use a closure, simply define a function inside another function and expose it.<br/>
Lexical Environment: In JavaScript, every running function, code block, and the script as a whole have an associated object known as the Execution Context: When your code runs in the JavaScript Engine. Each statement of your code is executed in a certain Execution Context. A new Execution Context is created whenever function invocation is there. <br/>
[closures](http://javascript.info/closure)<br/>
[execution-context](https://hackernoon.com/javascript-execution-context-and-lexical-environment-explained-528351703922)

### 2. What is Hoisting ? Are let & const are also hosted in JS ?
Hoisting: It is JavaScript's default behavior of moving declarations to the top.<br/>
All declarations (var, let, const, function, function*, class) are "hoisted" in JavaScript.<br/>
A variable declared by let or const has a so-called temporal dead zone (TDZ): When entering its scope, it can’t be accessed (got or set) until execution reaches the declaration.<br />
[hoisting](https://stackoverflow.com/questions/31219420/are-variables-declared-with-let-or-const-not-hoisted-in-es6)

### 3. Create Private variable in Javascript.
Using Classic prototype pattern<br/>
```js
var Car = (function(){
  var speed = 80;
  function Car(model,wheels,seats){
    this.model = model;
    this.wheels = wheels;
    this.seats = seats;
  }
  Car.prototype.run = function(){
    console.log('car of model '+this.model+' having '+this.wheels+' wheels & '+this.seats+' seats is running at speed of '+speed+' km/hr');
  }
  return Car;
})();
var maruti = new Car('Maruti 800',4,5);
maruti.run();
```
Using Singleton pattern<br/>
```js
var watch = (function(){
  var timer = 0;
  function increment(){
    timer++;
    console.log('timer value is: '+timer);
  }
  function decrement(){
    timer--;
    console.log('timer value is: '+timer);
  }
  return {
   increment: increment,
   decrement: decrement,
   };
})();
watch.increment();
watch.decrement();
```
