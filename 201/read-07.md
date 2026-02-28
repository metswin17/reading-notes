Domain ModelingLinks to an external site.


1. Explain why we need domain modeling.

Why Do We Need Domain Modeling?
Domain modeling helps us understand and organize a problem before we start coding.
It creates a clear blueprint of:
What objects exist


What data they store


How they relate to each other


What behavior they should have



🔎 In Simple Terms
Domain modeling helps you answer:
What are the main things in this system?


What information do they hold?


What actions can they perform?


Instead of jumping straight into code, you plan the structure first.

🧠 Why It’s Important
1️⃣ Prevents Confusion
You understand the system before building it.
2️⃣ Reduces Errors
Planning first helps avoid logic mistakes later.
3️⃣ Keeps Code Organized
You create clear objects and structure instead of messy code.
4️⃣ Makes Teamwork Easier
Everyone understands how the system is supposed to work.

💡 Example (Like Your Salmon Cookies Project)
If you’re modeling cookie stores, you might define:
Store


Location


Hours


Sales


Employee


Name


Role


Instead of random variables everywhere, you create structured objects.

🎯 Simple One-Sentence Answer (If This Is For A Quiz)
Domain modeling is used to identify the key objects, data, and relationships in a problem so we can design organized and efficient code before building the application.
We use domain modeling to understand the problem before we write code
What things exist in the problem as the objects 
what data they need 
and what they can do
The cookie the customer and the order
Reduce bugs confusion and rewrites because you wrote it before you coded it
These objects are the blueprint of how to reuse it

HTML Table BasicsLinks to an external site.


1. Why should tables not be used for page layouts?
 Tables used for data and not layouts because they hurt readability and maintenance  layouts 

It mixes structure with presentTION WHICH WE DON’T WANT TO DO

LAYOUT WITH DIVS SECTION 

TAbles with schedules pricelist and grades 

 List and describe 3 different semantic HTML elements used in an HTML <table>

<Thead> hold table row and contains column 
<Tbody> holds the main data row where most data go
<Tfoot> summary of table used for summary and final notes 

Introducing ConstructorsLinks to an external site.


1. What is a constructor and what are some advantages to using it?

A constructor is a special function used to create and initialize objects.
It sets up:
The object’s properties (data)


The object’s initial state


In JavaScript, a constructor is usually used with the new keyword.

🧠 Example in JavaScript
function Store(location, hours) {
 this.location = location;
 this.hours = hours;
}

let seattle = new Store("Seattle", "6am - 7pm");
Here:
Store is the constructor


new Store() creates a new object


this assigns values to that object



✅ Advantages of Using a Constructor
1️⃣ Creates Multiple Objects Easily
You can create many objects with the same structure.
let tokyo = new Store("Tokyo", "7am - 6pm");
let paris = new Store("Paris", "8am - 5pm");
No repeating code.

2️⃣ Keeps Code Organized
Instead of random variables everywhere, you group related data into structured objects.

3️⃣ Makes Code Reusable
You define the blueprint once and reuse it many times.

4️⃣ Improves Readability
Other developers can clearly see what properties an object should have.

🎯 Short Answer Version (For a Quiz)
A constructor is a special function used to create and initialize objects. It allows developers to create multiple objects with the same structure, keeps code organized, and improves reusability and readability.



A constructor is a special function used to create objects with the same structure
Instead of writing the same object over and over again helps write many objects and is like using a blueprint

Cookie { 
Type :chocalte chip
Gluten free : true
Nuts : false
Organic : true
Weight : big
Price : #?
}
No methods or parameters added, it is only an object now 
Less repeating code, easier to scale whether 5 - a 1000
Objects stay consistent , more organized

2. How does the term this differ when used in an object literal versus when used in a constructor?
 
 How this Differs
The meaning of this depends on how and where it is used.

1️⃣ this in an Object Literal
In an object literal, this refers to the object itself.
Example:
let store = {
 location: "Seattle",
 greet: function() {
   console.log(this.location);
 }
};

store.greet();
Here:
this refers to store


It accesses store.location


So in object literals, this points to the object that owns the method.

2️⃣ this in a Constructor
In a constructor, this refers to the new object being created when you use new.
Example:
function Store(location) {
 this.location = location;
}

let seattle = new Store("Seattle");
Here:
this refers to the newly created object


Each time new Store() runs, a new this object is created



🔥 Key Difference
Object Literal
Constructor
this refers to the existing object
this refers to the new object being created
Used inside a single object
Used as a blueprint for many objects


🎯 Short Answer Version (For a Quiz)
In an object literal, this refers to the object that contains the method. In a constructor, this refers to the new object being created when the constructor is called with the new keyword.
In a constructor this refers to a new object being created 
Object literal this refers the object it is inn
In a constructor This refers to creating an new property a new object
Object Prototypes Using A ConstructorLinks to an external site.


1. Explain prototypes and inheritance via an analogy from your previous work experience.
#### NOTE: This is a very common front end developer interview question



Prototypes & Inheritance (Medical Clinic Analogy)
In JavaScript, prototypes allow objects to share methods and properties.
 Inheritance means objects can access features from a shared source.

🏥 Analogy: Medical Clinic Staff
Think of a job role description at a clinic.
🧾 The “Prototype” = Clinic Policy Manual
At the clinic:
There is a standard policy manual.


It contains shared responsibilities like:


Verify patient identity


Take vital signs


Follow HIPAA procedures


Every medical assistant doesn’t get a brand-new copy rewritten from scratch.
Instead:
They all refer to the same manual.


If the clinic updates the policy (like requiring 2 patient identifiers), everyone follows it.


That shared manual is like a prototype.

👩‍⚕️ The “Objects” = Individual Staff Members
Each staff member:
Has their own name


Has their own schedule


Works with different patients


But they all inherit shared procedures from the clinic manual.
So:
Maria (Medical Assistant)


John (Medical Assistant)


You (Medical Assistant)


Each person is different, but they all inherit the same clinic procedures.

🧠 How This Relates to JavaScript
The constructor creates new objects (like hiring a new staff member).


The prototype stores shared methods (like clinic policies).


All instances inherit those shared methods without duplicating them.


This makes the system:
More efficient


Easier to update


More organized



🎯 Short, Professional Version (For Submission)
Prototypes are like a clinic policy manual that all medical assistants follow. Instead of each assistant having their own separate copy of procedures, they share a common set of rules. In JavaScript, objects inherit shared methods from a prototype, which improves efficiency and organization. Inheritance allows individual objects to access shared behavior while still maintaining their own unique properties.
You don't rewrite the handbook for every teacher. The teachers inherit it 
The object you are creating will inherit and take over those properties from the constructor functions


1. What is a Constructor function?

A template for making many similar things 

Subdivision , same blueprint for all the houses
One recipe and 1 cookie cutter 
Cutter constructor also called an instance (new object we create object instance same thing)
Appt building same layout
Floor plan is the constructor

Without a constructor you would have to manually do it over and over again
With a constructor you write constructor one and ask it to make more like it
If you only need 1 kitten you never need a constructor function. If you need a thousand make the constructor (the template) do it for you 

Functio, Car (make, model , year , color) { - These are parameters)
this,make= makel;
this.model= model;
this.year= year
this.color= color 

Function constructor function based on the capital letter

 const car1=  new Car(“Ford” , “Ranger”, 2010, “Purple”
 console.log (car1.make);

Method is a function inside of an object  this.drive= function ( ) {
consol.log(`you drive the ${this.model}`)
Back tics `  makes a template string
 car1.drive1  calling the function
Must be in same order as you have them in the parameters

Parameters are first then we replace those with arguments 
Parameters are place holders ex make model, created arguments Dodge , charger

Prototypes each time 
Prototype inheritance instead of giving every car a copy of drive, we will let all cars share the same function. Thats inheritance they all have the same functionality

 car.prototype.drive= function ( ) { 
console.log(`you drive the ${this.model}.`)
}; 

Car.prototype.

Prototype can change the objects state 
<div is a container and can hold lots of different things text video audio or tables
Create the cell
 fill the cell 
 attach the cell 
Like llego blocks

Table {border collapse , collapse 
 Th, td 
Const container = document,getElement

Dont make an array unless you are going to use it.

In construction function  
Instance is an object and object does not always has to be an instance
An instance is weh n a new object is created. It is the filled out form instead of the form by itself

A prototype is going to be adding information to your constructor function 
Prototype goes outside the constructor function and can be used globally


Construction functions is a template of objects 
The order of the parameters and order of objects matters. Incorrect order incorrect data 
Them must match 
new is keyword for instance
Order in the construtor funcion does not matter but in the parameters does matter 

Create,  fill,  append (attach
read-07.md

