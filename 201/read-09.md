

1. Why are forms so important in web development?
Forms are the primary bridge between a user and a system, transforming a static website into an interactive application. Beyond just "collecting names," they are essential for several technical and business reasons:


Allows user to send data an application. Easy access to user input. Easier form user to fill out a form,  make web applications more functional


2. When designing a form, what are some key things to keep in mind when it comes to user experience?
When designing a form, the goal is to reduce cognitive load and friction, making the "conversation" between the user and the system as smooth as possible.
Clarity and simplicity. Only ask for essential information. Organizes fields logically


3. List 5 form elements and explain their importance.
Input,  label, text area , select , buttons 
Radio buttons , select one option from a group
Check boxes , select with multiple items
Drop down menus, expandable options, save space useful for long options like state city and zip codes


To build a truly functional form, you need to choose elements that minimize the effort required from the user.
### [Learn JS](https://developer.mozilla.org/en-US/docs/Learn/JavaScript){:target="_blank"}


[Introduction To Events](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events){:target="_blank"}.


1. How would you describe events to a non-technical friend?
To explain events to a non-technical friend, you can think of them as the "sensory system" of a website.
In the real world, your brain is constantly waiting for "events" like a doorbell ringing, a phone vibrating, or a light changing at a crosswalk. On a website, an event is simply a notification that something interesting just happened.






2. When using the `addEventListener()` method, what 2 arguments will you
 need to provide?
When using the addEventListener() method, you are required to provide two main arguments to make it functional: 

GitHub Pages documentation +2
Event Type (The "When"): A case-sensitive string that specifies the name of the event you want to listen for.
Examples: 'click', 'submit', 'keydown', or 'mouseover'.
Note: Unlike older HTML attributes, you do not include the "on" prefix (use 'click', not 'onclick').
Listener/Callback Function (The "What"): The function or object that will execute whenever the specified event occurs. Call back references mentions the function argument (greet “hello”) call back references another function 
This can be a reference to an existing function or an "anonymous" function written directly inside the method.
Crucial Detail: You should pass the function name without parentheses (e.g., myFunction, not myFunction()). Adding parentheses calls the function immediately when the page loads, rather than waiting for the event








3. Describe the event object. Why is the target within the event object useful?
Tells you exactly which element was triggered. Which button and which form field changed. Without target you would not know which event was triggered
When an event occurs (like a click or a keypress), the browser doesn't just trigger your code; it also gathers a massive amount of "intelligence" about what happened. It packages all this data into a single package called the Event Object.
Think of the event object as a police report filed immediately after an incident. It records exactly where the event happened, who was involved, and what time it occurred.
1. What is the Event Object?
The event object is automatically passed (created) as an argument to your event listener function. It contains properties that describe the event's specific circumstances:
Coordinates: Where the mouse was on the screen (
).
Keys: Which specific key was pressed (like "Enter" or "Shift").










4. What is the difference between event bubbling and event capturing?
The main difference is the direction in which the event travels through the HTML structure. 
When you click an element (the "target"), the browser actually triggers a three-phase cycle: 

The Modern JavaScript Tutorial
1. Event Capturing (Trickle Down) starts at outermost element and moves inward to the element , outside to inside body to div to button
Direction: The event starts at the very top (the window or document) and moves down through every ancestor until it reaches the target element.
Usage: It is rarely used in common coding but is helpful if a parent needs to "intercept" an event before its children can even see it.
How to use: You must explicitly enable it by passing true as the third argument in addEventListener(). 

Learn to Code — For Free +4


2. The Target Phase
Direction: The event has arrived at the specific element you clicked. Any listeners directly on that element are triggered now. 

Learn to Code — For Free +2


3. Event Bubbling (Bubble Up) the default behaviour ex button div body 
Inside to outside  
Direction: After hitting the target, the event "bubbles" back up the tree to the top, triggering listeners on the parent, grandparent, and so on.
Usage: This is the standard default behavior in JavaScript.
Advantage: It is the foundation for event delegation, allowing you to put one listener on a parent (like a <ul>) to handle clicks for all its children (<li>). 

GreatFrontEnd +3













Students will be able to


#### Describe and Define


- JavaScript's `addEventListener()`.
- Anonymous functions and callbacks.
- Syntax and operations of an HTML `<form>`.
- Form structure, using semantic tags, including `<input>`, `<label>`, and `<fieldset>`.

Execute


- Code event listeners and handlers to capture events on the page.
- Collect form input and use it to instantiate new objects.
- Add a new row to dynamic data table(s) by storing, computing, and rendering data from the HTML form.
- Successfully pair-program with a fellow student and manage the collaborative and version control aspects of working with Git (from the command line) and GitHub (in the browser).

Forms demo 
Forms user input js uses the forms 

<br><br> is like hitting enter twice to space properly in form code 


demo
Form html 
  <h1>Guest List</h1>


  <!-- Click Element -->
  <div id="click-box">
    Click Me
  </div>


  <h2>Add Guest</h2>


  <!-- Basic Form -->
  <form id="guest-form">


    <label>
      Name:
      <input type="text" id="guest-name">
    </label>


    <br><br>


    <label>
      Age:
      <input type="number" id="guest-age">
    </label>


    <br><br>


    <button type="submit">Add Guest</button>


  </form>


  <h2>Guests</h2>


  <table id="guest-table" border="1">
    <thead>
      <tr>
        <th>Name</th>
        <th>Age</th>
      </tr>
    </thead>
    <tbody>
      <!-- Rows will go here -->
    </tbody>
  </table>


  <script src="app.js"></script>




Js code to apply 
/* =====================================================
   PART 1: BASIC CLICK EVENT
   ===================================================== */


// STEP 1: Grab the div
let clickBox = document.getElementById('click-box');


// STEP 2: Add event listener
// clickBox.addEventListener('click', handleClick);


// STEP 3: Create the function
function handleClick() {
  // Add something here
  // console.log('Box clicked');
}






/* =====================================================
   PART 2: FORM SETUP
   ===================================================== */


// STEP 4: Grab the form
let guestForm = document.getElementById('guest-form');


// STEP 5: Add submit listener
// guestForm.addEventListener('submit', handleSubmit);






/* =====================================================
   PART 3: HANDLE FORM SUBMIT
   ===================================================== */


function handleSubmit(event) {


  // STEP 6: Prevent page refresh
  // event.preventDefault();


  // STEP 7: Grab input fields
  // let nameInput = document.getElementById('guest-name');
  // let ageInput = document.getElementById('guest-age');


  // STEP 8: Get values
  // let name = nameInput.value;
  // let age = ageInput.value;


  // STEP 9: Call function to add row
  // addGuestToTable(name, age);


  // STEP 10: Reset form
  // guestForm.reset();


/* =====================================================
   PART 4: ADD ROW TO TABLE
   ===================================================== */


function addGuestToTable(name, age) {


  // STEP 11: Grab table body
  // let tableBody = document.querySelector('#guest-table tbody');


  // STEP 12: Create row
  // let row = document.createElement('tr');


  // STEP 13: Create cells
  // let nameCell = document.createElement('td');
  // nameCell.textContent = name;


  // let ageCell = document.createElement('td');
  // ageCell.textContent = age;


  // STEP 14: Append cells to row
  // row.appendChild(nameCell);
  // row.appendChild(ageCell);


  // STEP 15: Append row to table
  // tableBody.appendChild(row);
}






/* =====================================================
   PART 5: querySelectorAll PREP
   ===================================================== */


function updateGuestCount() {


  // STEP 16: Select all rows
  // let rows = document.querySelectorAll('#guest-table tbody tr');


  // console.log(rows.length);
}





Value pulls what the user has typed 

constructor is identified by a capital K in the function 


