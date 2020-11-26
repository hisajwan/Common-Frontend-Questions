# Common-Frontend-Questions
Common questions we should know as a frontend developer

## What is a module pattern ?
  The only way to control what to exposed to the global scope. Scoping the variables within the module is hard, and you can only do it via the module pattern.
  
  Example: 
  
  ```sh
  // filename: utils.js
  var utils = (function() {
  // you hide `pi` within the function scope
  var pi = 3.142;
  function area(radius) {
    return pi * radius * radius;
  }
  return { area };
  })();
   ```
  
  ```sh
  // filename: app.js
  console.log(utils.area(5)); // 78.55

  console.log(pi); // Reference error, `pi` is not defined
  ```
