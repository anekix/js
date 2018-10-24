## synatx

```javascript
var promise = new Promise( (resolve, reject) => {
    // if evevry thing went good , we call resolve with the value
    
    if (true) {
        resolve('function succeeded')
     }
    
    //..else reject

})

//now attach a handler that will be called when the function successfully resolves

promise
  .then( result => {
    console.log(result)
  })
  .catch( error =>{
    Error(error)
  })
```

if there is some error ,i.e if the promise is rejected , `.catch()` handler is called.

## practical Example ( an async image loader)

```javascript
function asyncImageLoader(url){
    return new Promise( (resolve, reject) => {
        var image = new Image()
        image.src = url
        image.onload = () => resolve(image)
        image.onerror = () => reject(new Error('could not load image'))
    }
}    
```    
    


