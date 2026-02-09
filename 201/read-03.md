When should you use an unordered list in your HTML document?
 when you need to group a collection of related items whose order or sequence or ranking is not important. Does not matter  ex grocery list if nthe changing of the order does not matter use the unordered list
How do you change the bullet style of unordered list items?
List-style-type choose SQUARE   Disk Circle Square and None 
When should you use an ordered list vs an unorder list in your HTML document?
Ordered list for caring about the order it is important. Unordered list when the order does not matter 
Describe two ways you can change the numbers on list items provided by an ordered list?
List style type with css  external 
or html start = ‘ 5 ‘ inside tag  inline 

Goal class 3 
- Use of arrays, array literals and index based access.
- Apply control flow in JavaScript using loops and conditional statements.
- Proper use of HTML element attributes.
- Application of the CSS box model for layout.


Array , list that sores multiple values in 1 variable. = Group related data together 
Ex colors -  green , blue , orange
What is a for loop , repeats the same acton   
For loop when you know how many times you want something to repeat
Whiile lupus goes for as long as it can till it reaches a false and it stops
Conditional logic 
Allows your program to make decisions  else if when you have 3 or more options 
An if statement setschecks a condition and runs the code only if the condition is true

Box model
how every html element is spaced and sized  
Padding space in the box edge border margin outside the box

Padding inside 
margin out 

4 parts to BOX MODEL 

Center box content 
Padding between the content and the border space inside the element 
Border is outline around edge of element 
Margin Space outside of the border separating or between the elements 


What data types can you store inside of an Array?
Array familiar apples oranges bananas 
Number s strings booleans 
Objects ,  holds related objects to 1 specific things  apples , kind color etc 

Is the people array a valid JavaScript array? If so, how can I access the values stored? If not, why?
const people = [['pete', 32, 'librarian', null], ['Smith', 40, 'accountant', 'fishing:hiking:rock_climbing'], ['bill', null, 'artist', null]];
Array 
People  [ 0  ]    [   1  ]  [  2  ]

List five shorthand operators for assignment in javascript and describe what they do.

+= add and assigns 
= minus and assigns
 
asterisk * = 
/ = 
! == 
== 

Read the code below and evaluate the last expression and explain what the result would be and why.

let a = 10;
 let b = 'dog';
 let c = false;

 // evaluate this
 (a + c) + b;
= 10 dogs 

Describe a real world example of when a conditional statement should be used in a JavaScript program.
Checking if a user is lodded in before showing the dashboard 
Checking someones age before entering a liquor store
Give an example of when a Loop is useful in JavaScript. 
List of products or names or locations and display them

While loop goes until the condition is not true anymore then stops

Every html element is a box 
When layout is weird one of these things are out of whack 
Margin border padding content 
Css will affect it’s width and height 
only control the content area not the box itself 

Padding pushes content away from the border. 
Makes text more readable. 
Makes it look  more comfortable and not crammed 
Breathing room for the elementary
Add to total size of the element 
 .box is a class thats reusable  
Entire page is your body 
Padding adds to your total size expands other blocks 
Adding to your original box  ex box is 150 x 200 and you add 50 padding now it really is 200 x 250

Border is the outline of the element 

Margin outward are the space between it and the other elements  etc boxes 
Wraps around padding

 Border is useful when you are 1st creating those elements because it helps see where things are at to visibly see where that border starts and stops to help setting up. You can take it off later 
Border Does make box visible

Margin
The space outside of the border. Margin push boxes away from each other 
Does not have a background color. How much space the box demands from its neighbors
Margin left right top lower 

How to change the box margin 
Margin: 20px ; means 20 all around 
margin -left: 20  margin-right: 10px; margin-top: 15px;  margin-bottom: 25px; 

Margin: 20px 40px ; 20 is top and left 40 is bottom and right 
Margin: 10px 20px 30px 40px  clockwise 10 top 20 right 30 bottom 40 on left 

Auto is used with a set width  browser will decide the rest
Padding pushes in margin pushes out

* { 
Box-sizing: border-box;  deals with amount of px you said you have
If you dont want it to go
T over the size you said 

Use borders when starting to get a visual. You can take it off later

The content is object in box
Padding space between content and wall of box
The border fence wall
Margin distance fro you to neighbors 
Every element is a box. Spacing issues are usually one of these 4 areas

Box sizing helps save time instead of going back to adjust later 

Array is a way to store multiple  related variables in one array
Especially useful when you dont know how many items you will have
Shopping list , users visiting site 

An array literal  we need a variable name 
Let Colors make it an array square brackets [  ]  to intialize it set the brackets as empty. Declaring , it’s empty it null nothing in it. But when it has elements with each having an index always starting at 0 
Access using position there index 
Call upon array use name of array and inside brackets the number index of element 0 is the 1st
Arrays can store mixed data 
Let boy = [ “alex”, 12, true ]

Let foods = [“taco”, “pizza”, “sushi”]
Arrays are the foundation of loops guessing games and displaying list on a page
Arrays can store strings booleans 


Let fruits = [“apple”, “banana”, “orange”, “grapes” ];
Let i=0 is where it starts  
For (lets i=0; i<  fruits.length; i++) { 
console.log(fruits[i])
*
While (condition) { console
Code you want to repeat
I++ 
}
*/
 While (count < 3)  {
console .log(count); 
Count++ 
}

let
Form
while loop the only thing that is in the parentheses is thevcondition is 

Infinite loop
Let count1+0;

while(count1 < ) {
console.log(count1)
}


Do while loop
When you want the code to run at least once, the condition 
Do  { 
repeated code
} while (condition) ;leg (“ask user password.lo
}} while (number <5);


Do runs 1st no question asked 

Let password ;
“);} while (condition) ;leg (“ask user password.lo

Password =’1234


 Do while loops less common but used in the right condition

Lab 3 then reading 4 priorities 

