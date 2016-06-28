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
