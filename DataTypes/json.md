# JSON

## JSON.parse

```javascript
JSON.parse('{"a": 1}');
// Object {a: 1}
JSON.parse({"a": 1});
// Uncaught SyntaxError: Unexpected token o in JSON at position 1(…)

data = '{"a": 1}';
// "{"a": 1}"
typeof data === 'string' ? JSON.parse(data) : data;
// Object {a: 1}
data = {"a": 1};
// Object {a: 1}
typeof data === 'string' ? JSON.parse(data) : data;
// Object {a: 1}

typeof data === 'object' ? data : JSON.parse(data);
// Object {a: 1}
```

