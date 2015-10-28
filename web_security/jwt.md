[jwt](http://www.toptal.com/web/cookie-free-authentication-with-json-web-tokens-an-example-in-laravel-and-angularjs)

#Session-based authentication

1. Hard to scale
2. Hard to work with CORS(auth server is separated from api server)
3. Can not share session with different web framework

#JWT

1. stateless
2. cross framework, and auth server and api server can be separated easily(CORS)
3. performance: no session management
4. security(no subject to session-riding)


With the rising popularity of single page applications, mobile applications, and RESTful API services, the way web developers write back-end code has changed significantly. With technologies like AngularJS and BackboneJS, we are no longer spending much time building markup, instead we are building APIs that our front-end applications consume. Our back-end is more about business logic and data, while presentation logic is moved exclusively to the front-end or mobile applications. 