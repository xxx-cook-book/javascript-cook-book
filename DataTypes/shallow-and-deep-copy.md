# Shallow And Deep Copy

## Shallow Copy

## Deep Copy

* JSON

  ```javascript
  function clone(obj) {
      return JSON.parse(JSON.stringify(obj));
  }
  var cloned = clone({ a:1 });
  ```

* deepcopy

  * Installation

    ```shell
    npm install deepcopy
    ```

  * Usage

    * Node

      ```javascript
      var deepcopy = require("deepcopy");
      ```

    * Browser

      ```javascript
      <script src="deepcopy.min.js"></script>
      ```

  * Example

    ```javascript
    var base, copy;
     
    base = {
      desserts: [
        { name: "cake"      },
        { name: "ice cream" },
        { name: "pudding"   }
      ]
    };
     
    copy = deepcopy(base);
    base.desserts = null;
     
    console.log(base);
    // { desserts: null } 
    console.log(copy);
    // { desserts: [ { name: 'cake' }, { name: 'ice cream' }, { name: 'pudding' } ] }
    ```

## References

[1] deepcopy@NPM, [deepcopy — deep copy for any data](https://www.npmjs.com/package/deepcopy)