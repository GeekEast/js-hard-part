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
- 


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