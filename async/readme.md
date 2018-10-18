async / await syntax is used for asynchronous programming in javascript.

## declare a async function like this
```js
async function asyncFuntion(){
  return 'hey i am an async function'
}
```
When above function is called as `asyncFunciton()` a promise is returned. a promise is an object which is resolved when the task is done. Even when returning a raw value, the value is casted to a `Promise` object.


To get the resolved value of a Promise we use `.then()` funciton. so the above code can be called as
```js
asyncFuntion().then(result => {
    console.log(result)
}
```


When we want to call a set of asynchronous function in a particular order we can do that with chanining`.then()`.

consider another async function that fetches some data from the database.

```js
async asyncFetchFromDB(){
  return 'fetching  results from the db'
}
```

now we want to call method `asyncFetchFromDB` only after the function `asyncFunction` has been called & resolved. so to di that we can use chaining of `.then()` like this

```js
asyncFuntion().then(result =>{
    console.log(result)
    return asyncFetchFromDB()
}).then( result =>{
    console.log(result)
 })
 
 // Output =>
 // hey i am an async function
 // fetching  results from the db
 ```

 
  



