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

now we want to call method `asyncFetchFromDB` only after the function `asyncFunction` has been called & resolved. so to do that we can use chaining of `.then()` like this

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
We can see that the above syntax gets cumbersome pretty quickly so we should have something better..

## Enter await statement
consider this example below:

```js

async function asyncFunc() {

  const data = await asyncFunction()
  console.log(data)
  
  const data2 = await asyncFetchFromDB()
  console.log(data2)
  
  return 'hey i got my results'
}
```
The `await` statement will pause the execution of the async function & wait until the data comes in /is resolved for the first async funtion( & then for other async funcitons used with await statement).

***Await is simply a more elegant way to write a promise within an async function. It improves readability immensely and hence the reason we use it***



## Error Handling in async await

**await** provides clean way to do error handling using the good old **try/catch** statements. Ex;
```js
async function asyncFunc() {
  try {
  
    // fetch data from a url endpoint
    const data = await axios.get("/some_url_endpoint");
    return data;
    
     } catch(error) {
  
    console.log("error", error);
    // appropriately handle the error
  }
}
```
  



