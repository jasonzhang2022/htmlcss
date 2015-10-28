[reference](https://www.owasp.org/index.php/CSRF)
[FAQ: common ways to perform CSRF attack ](https://www.owasp.org/index.php/CSRF)
[Encrypted token](http://insidethecpu.com/2013/09/23/encrypted-token-pattern/)

#CSRF
CSRF targets server state changes function. It does not steal data. 

#How does it attack?
It assumes that victim is authenticated.  It then performs a http GET/POST against server as victim without victim knowing it. It is also termed as "session ride". The request originated from csrf attack will automatically have cookie supplied by browser.

##Attack by GET
For example, it sends an email(web email) containing a link with a attractive title like  My Picture. Once user clicks it, the action against server is performed. 

EVen click isn't required. Some tags such a img/iframe/script performs the GET automatically. Attacker can design the these element so that it has no visual display (width=0 and height=0). Once user accesses the page/read the html email, the attack is performed

##Attack by POST
Attacker can trick the end user access them page. In the page, a hidden form can be submitted to targeted server automatically.  Notice that form is allowed to be submitted cross origin. The form response can be redirected to a hidden iframe. The victim has no idea a form is submitted on his behalf.
 
Please notice that attacker can't use XMLHTTPRequest to perform post since cross domain post is not allowed by XMLHttpRequest. (Unless target domain explicitly opens itself for CORS).

#prevention
## Synchronized token
Server generates a token. The token is associated with session. When a URL is generated or a form is generated, the token is appended to url or added to form. Token is retrieved and verified when form is submitted or get request is received. Attacker has no way to know the token. 

If CSRF token is in the url and the url is passed to external site through http referer header. External site can retrieve the token from referer can launch attack. In this case,  CSP referer policy (origin-when-cross-origin) could be used to prevent token from being exposed to external site.

Ideally, server should only use POST to perform state changing action. By this way, the GET does not need a token.

Remember although attacker can use an iframe to host GET's data, it can't read it.

The key points for synchronzied token is **Comparising hidden field with value stored in session**. It requires session. There are two drawbacks

1. **use memory**
2. **session is bad for distributed system**

## Double Cookie Submission

One token in cookie,  and one token in http header(or hidden form field). Compare them in server.

1. **No session**
2. **No Memory**
3. **Comparison based **
4. **Cookies cannot be tagged as HTTPONLY**
5. **Potential XSS vulnerabilities in subdomains can introduce poisoned cookies in upper domains**
 
## Encrypted Token Pattern

[reference](http://insidethecpu.com/2015/04/10/protecting-asp-net-applications-against-csrf-attacks/)

## Origin header
Origin header is not a good way to defend against CRSF since it is not required for same origin request.

