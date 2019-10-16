### Closure
- Everytime we run a function, the engine will switch to a local context, some variables are created during the runtime of that function
- When we finish that function, everything else except the return value are erased from memory.
- What if we could keep some part of the variable stored in the memory for caching purpose?
  - That's closure


### Further
- When you return a `function` from a `function`(high-order function), `associated data` with that returned function will be stored in `[[scope]]`, which is in global context but not accessible by user.
- And this is called `closure`.

### Example
```javascript
function outer() {
  let counter = 0; // this variable will be stored in [[scope]], which is in global context
  function incrementCounter() {
    console.log(++counter);
  }
  return incrementCounter;
}
const incrementCount = outer();

incrementCount();
incrementCount();
// what is the ouput?
```
### Callback
- execution go upwards
- return go downwards
- data searching direction is downwards
  - local > `[[scope]]` > global

### Duplicate or not?
- It won't pollute the global environment
- A good way to modulize things in Javascript
```javascript
function outer() {
  let counter = 0;
  function incrementCounter() {
    console.log(++counter);
  }
  return incrementCounter;
}


const incrementCount = outer();
incrementCount();  
incrementCount();


const anotherFunction = outer();
anotherFunction();
anotherFunction();
incrementCount();

// what is the ouput?
```
### The power of Closure
- `Memorize`: cache the function
- `Modulize`: things withouth pollute the global environment
### Summary
> Closure is a returned function with its surrounding environment where related variables are stored.
## Reference
[javascript作用域，作用域链，`[[scope]]`属性](https://segmentfault.com/a/1190000008042501)
- `[[scope]]` is called the lexical scope