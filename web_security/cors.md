[reference](http://www.html5rocks.com/en/tutorials/cors/)

#what can you do before cors?

1. html form post. You can't do XML form post using XmlHTTPRequest
1. http get in the form of script tag or img tag. This is the mechanism used by JSONP

#Simple cors: expand current supported to XmlHTTPrequest

extend the current available mechanism

## Requirement

1. method: GET, POST, HEADER
2. content type: those used by html form post. application/x-www-form-urlencoded,multipart/form-data,text/plain
3. limited header access

Flow:

1. Client sends request using XmlHTTPRequest( **you can't use XmlHTTPRequest before**)
1. Browse will add Origin header
1. Server checks Origin header and give response.
1. The response will have CORS-specific headers. Client is not allowed for CORS if there is no CORS header

	* Access-Control-Allow-Origin
	* Access-Control-Allow-Credential
	* Access-Control-Expose-Header

#Complicated cors: support more. Need preflight request
1. use other methods: PUT, DELETE
1. other content type

FLOW:

1. preflight request: OPTIONS method, ORIGIN header, some CORS header.

	* Access-Control-Request-Method
	* Access-Control-Request-Headers
	* Origin
  
1. preflight response

	+ Access-Control-Allow-Origin
	+ Access-Control-Allow-Methods
	+ Access-Control-Allow-Headers
	+ Access-Control-Max-Age

1. Access Control can be cached.





