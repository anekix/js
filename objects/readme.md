
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


## how to get multiple instances of the object 

```js
function createUser(name, age , address){
    return {
          name :name,
          age : age,
          address : address  
    }

}

var u1 = new createUser('rachel',20,'kentucky')
var u2 = new createUser('sam',21,'NYC')
```




