<img src="img/badger.png" height="300px">

#Mostly Adequate Notes

## First Class Functions

- Prefer first class functions when possible

```javascript
ajax('http://some/url', handleResonse);
```

instead of...

```JavaScript
ajax('http://some/url', (json) => {
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

## Composition

Composition allows you to create new functions by combining individual ones. 

```JavaScript

let shout = (phrase) => phrase.toUpperCase();
let exclaim = (phrase) => phrase + '!';

let yell = compose(exclaim, shout); // exclaim(shout(phrase))

yell('developers developers developers');
// DEVELOPERS DEVELOPERS DEVELOPERS!

```

Composition is also asociative 

```JavaScript

compose(compose(f,g), h) == compose(f, compose(g,h))
```

Composition comes from Category Theory, a branch of math that deals with unifying similar concepts from across other branches. 

In Category Theory, a category is: 

  1. A collection of objects
  2. A collection of morphisms
  3. A notion of composition on the morphisims
  4. A distinguished morphism called the identity

The category functional programming is concerned with: 

  1. Data types
  2. Pure functions
  3. Composition as described above
  4. The identity function: 
  ```JavaScript 
  (x) => x 
  ```

This usefulness viewing it in this mathematical lens will become apparent later. But for right now, the important thing Category Theory gives us is the identity function and the associativity of composition. 

