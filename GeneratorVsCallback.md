 <div align=center>  <h1>Generator Vs Callback </h1> </div>

### What are generators?
Generators are function executions that can be suspended and resumed at a later point.
Generators are useful when carrying out concepts such as ```lazy execution```. This basically means that by suspending execution and resuming at will, we are able to pull values only when we need to.
Generators have the below 2 key methods
**Yield method** – The yield method is called in a function to halt the execution of the function at the specific line where the yield method is called.
**Next method** – This method is called from the main application to resume the execution of a function which has a yield method. The execution of the function will continue till the next yield method or till the end of the method.

```javascript

function* Add(x) {
   yield x + 1;
   var y = yield(null);
   y = 6
   return x + y;
}

var gen = Add(9);
console.log(gen); //[object Generator] { ... }

console.log(gen.next());  //[object Object] {done: false,value: 10}

console.log(gen.next());  /[object Object] {done: false,value: null}

console.log(gen.next());  /[object Object] {done: done,value: 15}


```
