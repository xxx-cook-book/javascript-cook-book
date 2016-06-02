# MySQL Emoji Support

## Connection options

- `socketPath`: The path to a unix domain socket to connect to. When used `host` and `port` are ignored.

## Examples

```javascript
var mysql = require('mysql');


var connection = mysql.createConnection({
    host: 'localhost',
  	user: 'root',
  	password: '',
  	database: 'emoji_utf8mb4'
});

connection.query('select * from emojidemo;', function(err, rows) {
	console.log(rows);
});
/*
  [ { id: 1,
    created_at: Fri Aug 28 2015 11:01:28 GMT+0800 (CST),
    updated_at: Fri Aug 28 2015 11:01:28 GMT+0800 (CST),
    emoji: '?',
    status: 1 },
  { id: 2,
    created_at: Fri Aug 28 2015 11:01:53 GMT+0800 (CST),
    updated_at: Fri Aug 28 2015 11:01:53 GMT+0800 (CST),
    emoji: '?',
    status: 1 } ]
*/


var connection = mysql.createConnection({
  	host: 'localhost',
  	user: 'root',
  	password: '',
  	database: 'emoji_utf8mb4',
  	charset: 'UTF8MB4_GENERAL_CI'
});

connection.query('select * from emojidemo;', function(err, rows) {
  	console.log(rows);
});
/*
  [ { id: 1,
    created_at: Fri Aug 28 2015 11:01:28 GMT+0800 (CST),
    updated_at: Fri Aug 28 2015 11:01:28 GMT+0800 (CST),
    emoji: '😀',
    status: 1 },
  { id: 2,
    created_at: Fri Aug 28 2015 11:01:53 GMT+0800 (CST),
    updated_at: Fri Aug 28 2015 11:01:53 GMT+0800 (CST),
    emoji: '😀',
    status: 1 } ]
*/


connection.end(function(err) {
  // The connection is terminated now 
});
```

## References

[1] mysql@NPM, [mysql — A node.js driver for mysql. It is written in JavaScript, does not require compiling, and is 100% MIT licensed](https://www.npmjs.com/package/mysql)

