### Object-Oriented Programming
- **Encapsulation**: bind attribute and behaviour together

### Directly create object in Javascript
- **Method 1**
```javascript
let user1 = {
  name: 'will',
  score: 3,
  increment: function() {
    this.score++;
  }
}
user1.increment();
console.log(user1);
```
- **Method 2**
```javascript
let user2={};
user2.name="Tim";
user2.score=6;
user2.increment = function(){
  this.score++;
}
user2.increment();
console.log(user2);
```
- **Method 3**
```javascript
let user3 = Object.create(null);
user3.name="Eva";
user3.score=9;
user3.increment=function(){
  this.score++;
}
user3.increment();
console.log(user3);
```
### How to Increase Code Reuse?
- **Node**: Add `Wrapper` (From `Encapsulation` to `Inheritance`) 
- **Link**: Add `Protocol` for Communication through **parameters** (From Interface to Polymorphism) 


### Touch on Node-Reuse
```javascript
function userGenerator(name, score){
  let newUser = {};
  newUser.name = name;
  newUser.score = score;
  newUser.increment = function(){
    newUser.score++;
  }
  return newUser;
}

const user1 = userGenerator("James", 3);
user1.increment();
console.log(user1);
```
- But function is not reused!
### Again, Touch on Node-Reuse
- `Encapsulate` functions part
- Separate the functions part and store in a shared place: `prototype`
- `reference` the function part
```javascript
function userGenerator(name, score){
  // the userFunctionStore is defined in the prototype
  let newUser = Object.create(userFunctionStore)
  newUser.name = name;
  newUser.score = score;
  return newUser;
}

let userFunctionStore={
  increment: function(){this.score++},
  login: function(){console.log("You're loggedin")}
}

const user1 = userGenerator("James", 3);
user1.increment();
console.log(user1);
```

### Small Summary for Node Use
- Little Dip
  - `Encapsulate` as a small node.
  - Put it in a `shared` place.
  - `Reference` it when you need to use it.
- Abstract
  - `Wrap it up`
  - Many things' `shared place` **pay attention to scope**
  - `Reference`
    - But when you `reference` sth
      - You can generalize `type`: **Generics**
      - You can change `value`


### There is a sugar
- declare **function** through `prototype`
```javascript
function User(name, score) {
  this.name=name;
  this.score=score;
}

User.prototype;
User.prototype.increment = function(){
  this.score++;
}

let user1 = new User("Bob",100)
user1.increment();
console.log(user1);
```

### ES2015 Sugar
```javascript
class User {
  constructor(name, score){
    this.name = name;
    this.score = score;
  }

  increment() {
    this.score++;
  }

  login() {
    console.log("Login");
  }
}
```