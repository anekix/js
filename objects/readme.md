
## creating objects using literal notaion

```js
var user = {
  name :'rachel',
  age : 20,
  address : 'kentucky'
}
```

```js
var user = {};
user.name = 'rachel'
user.age = 20
user.address = 'kentucky'
```


## how to get multiple instances of the object with same flavour

```js
function createUser(name, age , address){
    return {
          name :name,
          age : age,
          address : address  
    }

}

var u1 = createUser('rachel',20,'kentucky')
var u2 = createUser('sam',21,'NYC')
```

## using function constructor
```js
function User(name, age){
  this.name = name
  this.age = age
}

var u1 = new User('rachel',20)
var u2 = new User('sam',21)

```

## using ES6 class syntax

```js
class User  {
  constructor(name) {
    this.name = name;
  }
}

var e = new User("hello");
```

## prototype

All JavaScript objects inherit properties and methods from a prototype.

our `User`  object inherits properties from `User.prototype`.The `Object.prototype` is on the top of the prototype inheritance chain:

## Adding new properties/methodds to the existing function constructor

```js
class User  {
  constructor(name) {
    this.name = name;
  }
}

User.prototype.address = 'kolkata';

var e = new User("hello");
console.log(e.address)
```




