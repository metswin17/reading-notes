Why would a developer use local storage for a web application?
To keep an application at it’s most recent state


What information should not be stored in local storage?
Local storage should never contain sensitive information, as it is accessible by any JavaScript on the page, making it vulnerable to XSS (cross-site scripting) attacks. Avoid storing authentication tokens (JWTs), passwords, personal data, or credit card details. It is best suited for non-sensitive data like UI themes or user preferences.

Local storage can store what type of data? How would you convert it to that type before storing?

Strings: Stored as-is.
Numbers: Converted to strings (e.g., 123 becomes "123").
Booleans: Converted to strings (e.g., true becomes "true").
Objects: Must be stringified (e.g., {a: 1} becomes '{"a":1}').
Arrays: Must be stringified (e.g., [1, 2] becomes "[1,2]"). 
How to Convert Data Before Storing
To store complex data structures like objects or arrays properly, you must use JSON.stringify() to convert them into a JSON string before passing them to localStorage.setItem()










C Is For Cookie. Is That Good Enough For Me? #
The classic way to do this is by using a cookie. A cookie is a text file hosted on the user’s computer and connected to the domain that your website runs on. You can store information in them, read them out and delete them. Cookies have a few limitations though:
They add to the load of every document accessed on the domain.
They allow up to only 4 KB of data storage.
Because cookies have been used to spy on people’s surfing behavior, security-conscious people and companies turn them off or request to be asked every time whether a cookie should 
Using Local Storage In HTML5-Capable Browsers #


Using local storage in modern browsers is ridiculously easy. All you have to do is modify the localStorage object in JavaScript. You can do that directly or (and this is probably cleaner) use the setItem() and getItem() method:
localStorage.setItem('favoriteflavor','vanilla');
Copy
If you read out the favoriteflavor key, you will get back “vanilla”:
var taste = localStorage.getItem('favoriteflavor');
// -> "vanilla"
Copy
To remove the item, you can use — can you guess? — the removeItem() method:
localStorage.removeItem('favoriteflavor');
var taste = localStorage.getItem('favoriteflavor');
// -> null
Copy
That’s it! You can also use sessionStorage instead of localStorage if you want the data to be maintained only until the browser window closes.
be set.
Working Around The “Strings Only” Issue #
One annoying shortcoming of local storage is that you can only store strings in the different keys. This means that when you have an object, it will not be stored the right way.
Use Case #1: Local Storage Of Web Service Data #
Use Case #2: Maintaining The State Of An Interface The Simple Way #
The Dark Side Of Local Storage #
Of course, any powerful technology comes with the danger of people abusing it for darker purposes. Samy, the man behind the “Samy is my hero” MySpace worm, recently released a rather scary demo called Evercookie, which shows how to exploit all kind of techniques, including local storage, to store information of a user on their computer even when cookies are turned off. This code could be used in all kinds of ways, and to date there is no way around it.
Further Reading on SmashingMag: #
Auto-Save User’s Input In Your Forms With HTML5 And Sisyphus.js
Keeping Web Users Safe By Sanitizing Input Data
An In-Depth Introduction To Ember.js
Building A Simple Cross-Browser Offline To-Do List
Research like this shows that we need to look at HTML5’s features and add-ons from a security perspective very soon to make sure that people can’t record user actions and information without the user’s knowledge. An opt-in for local storage, much like you have to opt in to share your geographic location, might be in order; but from a UX perspective this is considered clunky and intrusive. Got any good ideas?

