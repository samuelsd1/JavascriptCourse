# Promises


### Task #1
Write method called compareToTen which receives a number and returns a promise which checks whether the number is smaller, equal or bigger than 10

```js
function compareToTen(num) {
  // TODO: your code here
}

compareToTen(15)
  .then(result => console.log(result))
  .catch(error => console.log(error))
// Expected output: 15 is greater than 10

compareToTen(8)
  .then(result => console.log(result))
  .catch(error => console.log(error))
  // Expected output: 8 is less than 10
```

### Task 2
Write 2 functions which return promises which you can chain.
First function called makeAllCaps will receive array of strings,
and will modify all the strings to be upper case
if there is a non-string element, the promise should reject

Second function should be called sortArray, which will return promise that sorts the array
if the input is not an array, the promise will reject

```js
function makeAllCaps(arr) {
  // TODO: your code here
}
```

```js
function sortArray(arr) {
  //TODO: your code here
}
```
