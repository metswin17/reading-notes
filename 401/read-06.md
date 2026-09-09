Read 401 -06  


Securing Passwords
(https://thehackernews.com/2014/04/securing-passwords-with-bcrypt-hashing.html)  


Explain to a non-technical friend how you would safely hash and store a password.

Hashing is like putting a password through a one-way scrambler. Instead of storing the actual password, the system stores a unique scrambled version called a hash. When you log in, your password is hashed again and compared with the stored hash. This way, the actual password does not need to be stored. 

Class input: Turns a password into a unique stream of characters that is stored instead of the password.



What is Bcrypt?

Bcrypt is a password-hashing function designed to securely hash passwords. It adds a salt and has a configurable work factor that makes calculating hashes intentionally slower.
Class input: Adds a salt — random data added to the password before hashing.



Why might you use something like Bcrypt? 

Bcrypt is used because it is more secure than simple password hashing. It gives users unique salted hashes and is intentionally slow, making password-cracking attempts more expensive.
Class input: Every user gets a unique hash. Bcrypt is intentionally slow and widely recommended.





Basic Auth(https://en.wikipedia.org/wiki/Basic_access_authentication) 

What is Basic Authentication?

Basic Authentication is a simple way for a client to prove its identity to a server by sending a username and password with an HTTP request.
Class input: Because the credentials are encoded rather than encrypted, Basic Auth should be used over HTTPS so the communication itself is encrypted.


What properties are necessary in the header of a Basic Auth request?

Authorization: Basic <credentials>
The <credentials> portion contains the username and password joined with a colon and Base64 encoded: 
username:password -> Base64 




How are username:password in Basic Auth encoded?


The username and password are joined with a colon (username:password) and the entire string is encoded using Base64. 
Base64 is encoding, not encryption. It can easily be decoded, which is why Basic Authentication should be used over HTTPS. 



OWASP auth cheatsheet (https://www.owasp.org/index.php/Authentication_Cheat_Sheet) 

Define the authentication process to a non-technical recruiter.

Authentication is the process of proving that you are who you claim to be. Think of yourself as a store owner trying to enter your business. Your username identifies who you are, and your password is like the key used to prove you are authorized to enter. 




How should your error messaging respond (both HTTP and HTML) ?

Authentication errors should use appropriate HTTP responses, such as 401 Unauthorized, while displaying a vague message such as “Invalid username or password.” The response should not reveal whether the username or password specifically was incorrect. 

 Why? 
Detailed authentication errors can give an attacker information about which accounts exist. Generic error messages reveal less information and make the application more secure. 

3 Important Takeaways 
Passwords shouldn't be stored directly. Bcrypt hashes passwords, adds a salt, and is intentionally slow.
Basic Auth sends Base64-encoded username:password. Base64 is not encryption, so HTTPS is important.
Authentication errors should be vague. Don't tell a potential attacker whether the username or the password was specifically wrong.

Hashing passwords
password
   ↓
bcrypt + salt
   ↓
hash stored in database

Versus 
Basic Authentication 
username:password
       ↓
     Base64
       ↓
Authorization header
       ↓
HTTPS protects the connection
Those are two different jobs.
Bcrypt protects how a password is stored.
Base64 formats credentials so they can be sent in a Basic Auth header.
HTTPS provides the encryption while they're traveling.
