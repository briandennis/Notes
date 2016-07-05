<img src="img/badger.png" height="300px">

#Mostly Adequate Notes

## First Class Functions

- Prefer first class functions when possible

```javascript
ajax('http://some/url', handleResonse);
```

instead of...

```JavaScript
ajax('http://some/url', function(json) {
  return handleResponse(json);
})
```
- Easier to maintain if you need to change the function
- Allows more generic naming
- If must use ```this ```, use bind


## Pure Functions

- Same input always maps to same output
- Side effects are one of the largest causes of added complexity
- Same as mathematical functions!
- Why use?
  - Cacheable
  - Self documenting when you list all dependencies
  - Portable since all the code is inherit in the function
  - Much more testable since you inject anything that matters
  - Can run in parallel, no race conditions

## Currying 

  - Call a function with less arguments, and it returns a function that takes the remaining arguments.
  - Useful turning any single variable function, into a function on arrays
  
  ```JavaScript
  let map =  ( mapFunc ) => {
  
    return (arrayArg) => arrayArg.map(mapFunc);
    
  }
  ```
  - Allows you to convert multivariable functions to 'transpile' to single variable functions, maintaining the mathematical definition of funciton
