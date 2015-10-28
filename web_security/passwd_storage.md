[reference](https://blog.mozilla.org/webdev/2012/06/08/lets-talk-about-password-storage/)

1. Double hash.
1. use salt stored in file system, separated from database system. When database is hacked, hacker still can't crack the password
1. use a slow hash mechanism like bcrypt
1. password -> bcrypt(HMAC(password, local_salt), bcrypt_salt). 

