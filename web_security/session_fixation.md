[reference in wikipedia](https://en.wikipedia.org/wiki/Session_fixation)

# Attack
1. Phish user to click a URL with query string. The query string has a sesison id which can be
	+ arbitrary string
	+ valid session id for attacker 
2. Session can also be introduced by **cross-subdomain cookie attack**

How can attacker know that victim logged in using the introduced session?

Victim can try with the session repeatedly to see whether he can perform some logged function on the behalf of another user?

The purpose of session fixation is tricking user login  with attacker session id so attacker can use the same session id and impersonate as victim.


Another scenario is the opposite. Attacker tricks victim uses website with his logined session. Attacker can come back to see what happen in the logined session and obtain some useful information.


#counter measure.
1. Don't let client to define the session. 
	+ don't accept session from query string or post parameter.
	+ don't allow set session as cookie using javascript
	+ session is set as Httponly cookie. In another word, only browser can manage it. 
1. change session at user login time or important momenent so hacker session becomes invalid
1. timeout old session

The session fixation attack is a class of Session Hijacking, **which steals the established session between the client and the Web Server after the user logs in**. Instead, the Session Fixation attack **fixes an established session on the victim's browser, so the attack starts before the user logs in.**



  