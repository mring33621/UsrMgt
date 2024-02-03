## 'UsrMgt' is a minimal User Management library.
1. Uses a text file at $baseDir/$appName_um.txt ($baseDir defaults to user's home directory)
2. To add a new user, simply append a new line to the file in the format `username|password`
3. A successful login will return a token, which can be used to authenticate future requests
4. A scheduled task will hash plaintext passwords with BCrypt
5. Another scheduled task will expire user tokens after 4 minutes of inactivity (non-renewal of token)
6. User tokens are kept in memory, and are not persisted to disk
7. Currently, supports only AUTHN, not AUTHZ
8. This library tries to be thread-safe 
9. This library is not intended to scale to more than a few hundred users
10. This library does not track any user activity
11. I'm using Java 21, but should be easily convertable to Java 8.
12. UsrMgt is used in my [Grambaal-UI](https://github.com/mring33621/grambaal-ui) project