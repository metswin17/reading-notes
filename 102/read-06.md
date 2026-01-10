read-06.md
JavaScript (JS) is a lightweight interpreted (or just-in-time compiled) programming language with first-class functions. That is used in non  browser apps as well ex. Adobe Acrobat
supporting multiple paradigms such as imperative, functional, and object-oriented.

JIT (Just-In-Time Compilation) is a compilation process in which code is translated from an intermediate representation or a higher-level language (e.g., JavaScript or Java bytecode) into machine code at runtime, rather than prior to execution. This approach combines the benefits of both interpretation and ahead-of-time (AOT) compilation.

AOT (Ahead-Of-Time) compilation = code is compiled before it runs in the browser or environment, instead of being compiled at runtime.
This contrasts with JIT (Just-In-Time) compilation, where code is compiled while the app is running.
However, AOT is used at the framework/build level, not the JS language level.
Prototype based programming - 
In simple words: this type of style allows the creation of an object without first defining its class.
 "GC," garbage collection is a fundamental component of the memory management system used by JavaScript. the process of finding and deleting objects which are no longer being referenced by other objects.
Dynamic typing
Dynamically-typed languages are those (like JavaScript) where the interpreter assigns variables a type at runtime based on the variable's value at the time.
Do not confuse JavaScript with the Java programming language — JavaScript is not "Interpreted Java". Both "Java" and "JavaScript" are trademarks or registered trademarks of Oracle in the U.S. and other countries. However, the two programming languages have very different syntax, semantics, and use.

Paradigms are just different styles or ways to write and think about code.
The sentence means:
 👉 Programming languages can be written using different styles, such as imperative, functional, and object-oriented.
Super simple summary
Imperative: tell the computer how to do things


Functional: focus on functions and results


Object-Oriented: organize code into objects


Bonus (important for JavaScript):
👉 JavaScript can use all three, which makes it very flexible.

The standards for JavaScript are the ECMAScript Language Specification (ECMA-262) and the ECMAScript Internationalization API specification (ECMA-402). 
JavaScript consists of the core language (ECMAScript), the DOM, and browser Web APIs.
1️⃣ The JavaScript Language (ECMAScript)
This is the core language itself.
It includes:
Variables (let, const)


Functions


Loops


Objects


Arrays


Scope, closures, etc.


👉 This part works the same everywhere (browser, Node.js).

2️⃣ The DOM (Document Object Model)
This is how JavaScript interacts with a web page.
It lets you:
Change HTML


Change CSS


Respond to clicks and typing


Example:
document.querySelector("h1").textContent = "Hello!";

👉 This part is provided by the browser, not JavaScript itself.
3️⃣ Web APIs (Browser APIs)
These give JavaScript extra powers in the browser.
Examples:
fetch() (APIs / data)


setTimeout()


localStorage


Events (clicks, keyboard)
👉 Also provided by the browser.

4 things common to all computers 
1 Input
2 Store information
3 Process information
4 Output

An operating system ( ex - windows) is software that manages a computer’s hardware and allows programs to run.
The CPU (Central Processing Unit) is the part (Brain) of a computer that processes instructions and performs calculations.

Answer Lab 6 
What are variables in JavaScript?
	Variables are named containers used to store and manage data in JavaScript

What does it mean to declare a variable?
	Declaring a variable means creating it and giving it a name so it can be used in the program

What is an “assignment” operator, and what does it do?
	An assignment operator is a symbol that puts a value into a variable.

What is information received from the user called?
	Information received from the user is called input.
