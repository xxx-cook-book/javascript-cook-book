# Element in Array

## Array.prototype.indexOf()

The `indexOf()` method returns the first index at which a given element can be found in the array, or -1 if it is not present.

* Syntax

  ```javascript
  arr.indexOf(searchElement[, fromIndex = 0])
  ```

* Usage

  ```javascript
  Array.indexOf(Element) >= 0
  ```

* Polyfill

  ```javascript
  // Production steps of ECMA-262, Edition 5, 15.4.4.14
  // Reference: http://es5.github.io/#x15.4.4.14
  if (!Array.prototype.indexOf) {
    Array.prototype.indexOf = function(searchElement, fromIndex) {

      var k;

      // 1. Let o be the result of calling ToObject passing
      //    the this value as the argument.
      if (this == null) {
        throw new TypeError('"this" is null or not defined');
      }

      var o = Object(this);

      // 2. Let lenValue be the result of calling the Get
      //    internal method of o with the argument "length".
      // 3. Let len be ToUint32(lenValue).
      var len = o.length >>> 0;

      // 4. If len is 0, return -1.
      if (len === 0) {
        return -1;
      }

      // 5. If argument fromIndex was passed let n be
      //    ToInteger(fromIndex); else let n be 0.
      var n = +fromIndex || 0;

      if (Math.abs(n) === Infinity) {
        n = 0;
      }

      // 6. If n >= len, return -1.
      if (n >= len) {
        return -1;
      }

      // 7. If n >= 0, then Let k be n.
      // 8. Else, n<0, Let k be len - abs(n).
      //    If k is less than 0, then let k be 0.
      k = Math.max(n >= 0 ? n : len - Math.abs(n), 0);

      // 9. Repeat, while k < len
      while (k < len) {
        // a. Let Pk be ToString(k).
        //   This is implicit for LHS operands of the in operator
        // b. Let kPresent be the result of calling the
        //    HasProperty internal method of o with argument Pk.
        //   This step can be combined with c
        // c. If kPresent is true, then
        //    i.  Let elementK be the result of calling the Get
        //        internal method of o with the argument ToString(k).
        //   ii.  Let same be the result of applying the
        //        Strict Equality Comparison Algorithm to
        //        searchElement and elementK.
        //  iii.  If same is true, return k.
        if (k in o && o[k] === searchElement) {
          return k;
        }
        k++;
      }
      return -1;
    };
  }
  ```

## in

```javascript
function oc(a) {
    var o = {};
    for(var i = 0; i < a.length; i++) {
        o[a[i]] = '';
    }
    return o;
}

if( name in oc(['Qimin', 'Huang', 'China']) ) { ... }
```

## References

[1] MDN, [Array.prototype.indexOf()](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf)

[2] Jonathan Snook, [Testing for a Value in JavaScript Array](https://snook.ca/archives/javascript/testing_for_a_v)