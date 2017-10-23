* AngularJS is well equipped to communicate with various back-ends using XMLHttpRequest (XHR) and JSONP requests.
* Use $http service for issuing XHR and JSONP calls or specialized $resource service to easily target RESTful endpoints.

# A generic way to issuing XHR request

To issuing XHR request in generic way, we can use the `$http(configObject)` function with the config object can have the following properties:
* `method`: HTTP method to be issued
* `url`: URL to be targeted with a request
* `params`: parameters to be added to the URL query string
* `headers`: additional headers to be added to a request
* `timeout`: timeout (in ms) after which a XHR request will be dropped
* `cache`: enables XHR GET request caching
* `transformRequest`, `transformResponse`: transformation functions that allows us to pre-process and post-process data exchanged with a back-end.
# Dedicated shortcut methods to issue XHR request

* GET: `$http.get(url, config)`
* POST: `$http.post(url, data, config)`
* PUT: `$http.put(url, data, config)`
* DELETE: `$http.delete(url, config)`
* HEAD: `$http.head`

Use those shortcut methods since it's more concise and easier way to read code, and use this form over the generic one whenever possible. 