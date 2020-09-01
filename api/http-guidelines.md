## HTTP Guideline

### GET
* Never send payload in GET requests
* URI must be:
  * Descriptive
  * Meaningfull
  * Resource oriented
* Conditional GET:
  * Whenever server serves a representation, it should include a time value for Last-Modified HTTP header.This time denotes the last time the data underlying the representation was changed.
  * The client can store this value of Last-Modified and use it later. So the second time the client makes a GET request for that request, it can provide that time in the If-Modified-Since request Header.
  * When the server receives this GET request, it compares the time with the latest modified resource state time. If both are same, then Server sends a response code of 304 “Not Modified” and doesn’t send any data. But if the the time doesn’t match, then Server send 200 “OK” and provides the new representation in the response body.
* The server should set value for Cache-control headers to avoid caching of resources at client side or Web Gateways for indefinite period of time.

### POST
* To create a new resource whose URI is going to be determined by server.
* It is not idempotent.

### PUT
* To replace the current representation of an existing resource with a new representation.
* If client knows or decides the URI to create a new resource under that URI,then use PUT.
* It is idempotent.

#### PUT Versus POST (For new resources creation)
You can expose PUT, POST or both. But the Client can only use PUT to create resources when it can define the final URI of the new resource.

##### PUT use case
The Client will create a blog article and will define the slug that will be served through an api.

##### POST use case
The Cliente will create a new user and the user id will be used to get its data
