How would you describe an object to a non-technical friend you grew up with?
An object is like a toolbox with different draws and mixed tools 
Thing with details about it , how old tricks it can do 
Array describes  lists 

What are some advantages to creating object literals?
Easy and quick to create
You can define an entire object in one place:
Organizes related data together
Can include functions (methods)
Works great with this
Object literals pair perfectly with this, letting methods refer to their own data:

Object literals help you:
Group data


Add behavior


Keep code clean
Objects let us store information the way humans describe real things 

How do objects differ from arrays?
Objects store data with descriptions  , Array are orders list you list by 0123 stores data in order 
Objects use brackets        use key value pairs divided best for 1 thing not a list of things  (describtion)

Const  Car {   has wheels . true
Make. Toyota
Nothing needed after the last 
} needs , after to end it
Arrays use curly braces   order matters 
Give an example for when you would need to use bracket notation to access an object’s property instead of dot notation.
Use dot notation when:

Property name is simple


You know it ahead of time


Use bracket notation when:
Property name has spaces


Property starts with a number


You’re using a property name is stored in a  variable
 When using a variable to access the property (VERY IMPORTANT)
This is the most common real-world reason.
let bread = {
 sourdough: 10,
 brioche: 5
};

let userChoice = "brioche";

console.log(bread[userChoice]); // ✅ 5
Dot notation would look for a property literally named userChoice:




🧠 Short Test Answer Version
Bracket notation is needed when the property name contains special characters, spaces, starts with a number, or when accessing a property dynamically using a variable.

Evaluate the code below. What does the term this refer to and what is the advantage to using this?

const dog = {
  name: 'Spot',
  age: 2,
  color: 'white with black spots',
  humanAge: function (){
    console.log(`${this.name} is ${this.age*7} in human years`);
  }
}
Inside the humanAge function, this refers to the object that is calling the method, which is dog.
So:
this.name → "Spot"


this.age → 2


If you run:
dog.humanAge();
Output will be:
Spot is 14 in human years

Using this makes your code dynamic and reusable.
Instead of hardcoding values like:

Use back ticks ( ` ${this.name} is ${this.age#7} in human years 
console.log("Spot is 14 in human years")

;Key idea (important for your class)
this = “the current object” 


It lets your function work with whatever object is using it



⚠️ One thing to watch out for
If you use an arrow function:
humanAge: () => { ... }
👉 this will NOT work the same way (it won’t refer to dog)


Introduction To The DOM
What is the DOM?
Think of the DOM (Document Object Model) as the bridge between your web page's code js and what you actually see on your screen. How js sees the web page 
A way that js sees your html tags like href attributes etc 
When a browser loads a website, it takes the flat, static HTML text and turns it into a living, breathing tree structure. This allows programming languages like JavaScript to "talk" to the page, change colors, move elements around, or handle clicks.

1. The Tree Structure
The DOM organizes everything in a hierarchy of nodes. Every element, attribute, and piece of text in your HTML becomes a node in this tree.
+1
Document: The root of the entire "tree."
Elements: The tags like <body>, <h1>, or <div>.
Attributes: Properties of tags, like href or src.
Text: The actual words inside a heading or paragraph.
2. Why does the DOM matter?
Without the DOM, JavaScript wouldn't understand what a "button" is. It would just see a string of text. Because of the DOM, developers can:
Add/Delete elements: Dynamically adding a new comment to a feed.
Change styles: Switching a page from "Light Mode" to "Dark Mode."
React to users: Making a pop-up appear when a specific button is clicked.
3. A Simple Comparison
Imagine a blueprinted house:
HTML is the blueprint (the plan on paper).
The DOM is the actual physical house built from that blueprint.
JavaScript is the person living in the house who can paint the walls or move the furniture.

A Quick Example
If you have this HTML:
HTML
<button id="magicBtn">Click Me</button>


The DOM allows JavaScript to find that specific button and change it like this:
JavaScript
// Finding the element in the DOM
const btn = document.getElementById('magicBtn');


// Modifying the DOM
btn.style.backgroundColor = 'blue';
btn.textContent = 'I have been changed!';
Use const when the variable will not change ex year born 
Let variable will change ex age 
Objects generally use const  unless you know its going to change use let
Different data types can be inside an object
Instead of making 5 different variables I can make 1 object with all 5 variables inside it and functions
Objects is made of properties each properties made up of key value par
Geno,speak ( ); (calling it)
This is the most important concept this === (strictly equal to) Geno
This makes it reusable 
Parameters are place holders waiting for values to be designated 
Math . random random numer 
Math .floor turns decimal in to a whole number 
Calling function geno.getAge ( ); 
Html build page , The DOM is a representation of the page and JS brings it to life 


Briefly describe the relationship between the DOM and JavaScript.
JavaScript interacts with the DOM to read, modify, and update the content and structure of a webpage, making it interactive.


The DOM (Document Object Model) and JavaScript work together to make web pages interactive.
The DOM is a structured representation of your HTML page (like a tree of elements).


JavaScript uses the DOM to access and manipulate those elements.


👉 In simple terms:
 JavaScript controls and updates the webpage by interacting with the DOM.
Example:
document.querySelector("h1").textContent = "Hello!";
document = the DOM


JavaScript changes the <h1> text on the page


Why this matters:
You can change text, styles, images


Respond to user actions (clicks, input, etc.)


Make your page dynamic instead of static
How to Solve Programming Problems


A simple set of steps
I am going to give you a simple set of steps to follow which you can use for any algorithm type programming problem.
Read the problem completely twice.
Solve the problem manually with 3 sets of sample data.
Optimize the manual steps.
Write the manual steps as comments or pseudo-code.
Replace the comments or pseudo-code with real code.
Optimize the real code.
As much as 70% of our time should be spent in steps 1-3.
Programming is automation plain and simple.  You may have the ability to skip the manual steps and jump directly to code, but there is a manual process which is the foundation of any code you write.
It is very important to solve the problem manually first, so that you know what you are going to automate, otherwise you are just slinging code around.  Which while can be fun, will make you look like an idiot in a programming interview and will probably cause you to sweat profusely.

Key Aspects of POUR Website Construction:
Perceivable (Information & UI): Provide text alternatives for non-text content, captions for audio/video, and adaptable layout for screen readers.
Operable (Navigation & Function): Make all functionality keyboard-accessible, provide sufficient time for users, and help users navigate.
Understandable (Information & Operation): Ensure content is readable, consistent, and predictable in operation.
Robust (Compatibility): Maximize compatibility with current and future user tools, including assistive technologies. 
Americas with Disabilities ACT ADA Prohibits disability discrimination in any place of public accommodation like websites 
Avoid discrimination and legal complaints 
Improved experience for everyone
Reach a wider audience
Economic gains with little additional cost	
Users with disabilities 
Visual, Auditory, Cognitive, Motor/Physical, 
Neurological/Vestibular, Speech 


git mkdir hotfix  x
Answer 2:
git add .
Answer 3:
git commit -m"hotfix"  x
Answer 4:
git push origin hotfix
Lab 1 in put out 
Lab 5 b and 5 c and feedback week 1 
IDs should be unique


Classes can be used on multiple elements


That was a good catch — those tiny syntax details are what separate beginners from people who actually understand CSS 💪


Check for color contrast


Method is a function inside of an object 











Jason instructions on cookie salmon

Wire frame for 3 pages  
1Home page 
 2 locations addition min max sales page 
 3 contact page



