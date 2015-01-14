[![build status](https://secure.travis-ci.org/bebraw/swagger2client.png)](http://travis-ci.org/bebraw/swagger2client)
# swagger2client - Client for Swagger 2.0

Usage:

```javascript
var swaggerClient = require('swagger2client');

var client = swaggerClient({
    url: ..., // url to API root
    schema: ..., // swagger 2.0 schema
    headers: { // optional headers (handy for auth)
        'Authorization': 'Bearer ' + ...
    }
});

// Swagger resources can be accessed like this
// parameters are optional. in case of GET they are passed to query,
// otherwise to body
client.todos.get({...}).then(function(res) {
    ...
}).catch(function(err) {
    ...
});

// in addition it is possible to access metadata related to resources
client.todos.parameters
client.todos.responses
client.todos.description

// these map to Swagger definition. $refs have been expanded
```

Internally the requests are based on [axios](https://www.npmjs.com/package/axios) so check that out for specifications for return values and such.

## License

`swagger2client` is available under MIT. See LICENSE for more details.

