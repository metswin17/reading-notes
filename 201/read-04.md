HTML is the technology that defines the content and structure of any website. Written properly, it should also define the semantics (meaning) of the content in a machine-readable way, which is vital for accessibility, search engine optimization, and making use of the built-in features browsers provide for content to work optimally.

HTML lives inside text files called HTML documents, or just documents, with a .html file extension.
The most common HTML file you'll encounter is index.html, which is generally used to contain a website's home page content. 

Nesting elements
Elements can be placed within other elements. This is called nesting. If we wanted to state that our cat is very grumpy, we could wrap the word very in a <strong> element, which gives the word strong(er) text formatting:








Learn HTML
Creating Hyperlinks
To create a basic link, we wrap text or other content inside what element?
To create a basic link, you wrap text (or other content) inside the:
<a> element
That’s called the anchor tag.
<a> → the element (the thing wrapping the content)


href → the attribute that tells it where to go


The href attribute contains what information?
A link to a url , website or a file location ex image 

What are some ways we can ensure links on our pages are accessible to all readers?
Use descriptive and clear link text
Make sure links are keyboard accessible
Use color contrast but dont relay on color alone use bold or italic
Add attributes when needed 
(No href means it won’t behave like a real link.)
CSS Layout
CSS Layout: Normal Flow CSS Layout: Positioning
What is meant by “normal flow”?
normal flow is the default way a browser lays out block and inline content.
Normal flow is the default way the browser places elements on a page when you don’t change their positioning with If you don’t use:
position: absolute


position: fixed


float


flexbox


grid


… then everything follows normal flow.

What are a few differences between block-level and inline elements?
Block elements (like <div>, <p>, <h1>)
Stack vertically


Take up the full width available


Appear one under another

Inline elements (like <span>, <a>, <strong>)
Flow left to right


Only take up as much space as they need


___ positioning is the default for every html element.
Static  
Static elements:
Stay in normal flow


Cannot use top, left, right, or bottom


Stack naturally according to block/inline behavior


So anytime you haven’t written position: relative, absolute, fixed, or sticky — you’re using static positioning.


Name a few advantages to using absolute positioning on an element.
Precise control over placement
Ability to overlap elements
 Removed from normal flow
Can be positioned relative to a container
Absolute positioning provides precise control over element placement, allows overlapping elements, removes elements from normal flow, and enables positioning relative to a specific container.

What is a key difference between fixed positioning and absolute positioning?
The key difference:
Absolute positioning is positioned relative to its nearest positioned parent.
position: absolute;
Moves relative to the nearest parent with position: relative


Scrolls with the page


Can move around if its container moves


So if you scroll down the page, an absolutely positioned element will scroll away with everything else.

Fixed positioning is positioned relative to the browser window (viewport).
position: fixed;
Always positioned relative to the browser window


Does NOT move when you scroll


Stays stuck in place




Learn JS
Functions – Reusable Blocks of Code
Describe the difference between a function declaration and a function invocation.
A function declaration is when you define the function — you’re basically telling JavaScript:
“Here’s a reusable block of code. Save it for later.”
function greet() {
  console.log("Hello!");
}
A function invocation (or function call) is when you actually run the function.
greet();  =  Hello!
Declaration = writing the recipe


Invocation = cooking the food


What is the difference between a parameter and an argument?
The difference:
Parameter → the variable listed in the function definition


Argument → the actual value you pass into the function when you call it


function greet(name) {
  console.log("Hello " + name);
}
Here:
name is the parameter


It’s a placeholder


It’s part of the function declaration


Now when we call it:
greet("Luis");
"Luis" is the argument


It’s the real value being passed in


Parameter = what the function expects
Argument = what you actually give it

Miscellaneous
6 Reasons for Pair Programming
Pick 2 benefits to pair programming and reflect on how these benefits could help you on your coding journey.
Two benefits of pair programming:
1️⃣ Learning from someone else’s perspective
When you work with another person, you see how they approach problems, structure code, and debug errors.


Reflection for you: This can help you discover new techniques and best practices faster than working alone. You might pick up shortcuts, coding styles, or ways to think about problems that you hadn’t considered.


2️⃣ Fewer errors and better code quality
With two sets of eyes on the code, mistakes are caught earlier and solutions are often more efficient.


Reflection for you: This reduces frustration from bugs and helps you learn to write cleaner, more organized code. Over time, you’ll become more confident in your own debugging skills.



Extra reflection thought:
Pair programming also encourages communication and teamwork, which is crucial in real-world coding projects. You’ll get comfortable explaining your thinking, which reinforces your own understanding.
read-04.md
