For too long I've failed to discern the distinction between query parameters and query strings, to I finally looked it up...

A Query String is what often accompanies the URL path in a GET request (e.g. `name=forest` in `http://example.com/over/there?name=forest`).
The Query Parameters are either the components of the query string or passed as part of the request body.  

Generally speaking, a Query String is used for GET requests and a Request Body is used for POST requests.

A request containing a request body should be a POST rather than GET as the request body is not part of the identification of the resource being requested.

GET requests are generally used for idempotent actions 
(where an idempotent action here is an HTTP method that can be called many times without different outcomes), 
and POST requests are used for non-idempotent actions.

When POSTing data, some advantages to using a request body (over a query string) include...
* Easier to send JSON (or XML) without translating between formats (no need for crazy URL encoding)
* URL’s can only be 2000 characters (or thereabouts depending on browser), while max size for request body is more likely to be around 2MB






