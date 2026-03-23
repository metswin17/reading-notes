

Transforms
With CSS3 came new ways to position and alter elements. Now general layout techniques can be revisited with alternative ways to size, position, and change elements. All of these new techniques are made possible by the transform property.


The transform property comes in two different settings, two-dimensional and three-dimensional. Each of these come with their own individual properties and values.







Transitions
As mentioned, for a transition to take place, an element must have a change in state, and different styles must be identified for each state. The easiest way for determining styles for different states is by using the :hover, :focus, :active, and :target pseudo-classes.
There are four transition related properties in total, including transition-property, transition-duration, transition-timing-function, and transition-delay. Not all of these are required to build a transition, with the first three are the most popular.
If multiple properties need to be transitioned they may be comma separated within the transition-property value. Additionally, the keyword value all may be used to transition all properties of an element.
It is important to note, not all properties may be transitioned, only properties that have an identifiable halfway point. Colors, font sizes, and the alike may be transitioned from one value to another as they have recognizable values in-between one another. 

The duration in which a transition takes place is set using the transition-duration property

The transition-timing-function property is used to set the speed in which a transition will move

Animations Keyframes
To set multiple points at which an element should undergo a transition, use the @keyframes rule. The @keyframes rule includes the animation name, any animation breakpoints, and the properties intended to be animated.
8 simple CSS3 transitions that will wow your users
CSS3 has introduced countless possibilities for UX designers, and the best thing about them is that the coolest parts are really simple to implement.Just a couple of lines of code will give you an awesome transition effect that will excite your users, increase engagement and ultimately, when used well, increase your conversions. What’s more, these […]
Sara Vieira
Posted May 1, 2014
CSS3 has introduced countless possibilities for UX designers, and the best thing about them is that the coolest parts are really simple to implement.
Just a couple of lines of code will give you an awesome transition effect that will excite your users, increase engagement and ultimately, when used well, increase your conversions. What’s more, these effects are hardware accelerated, and a progressive enhancement that you can use right now.
(1) Earth 3D Map
2. Change color

3. Grow & Shrink

4. Rotate elements

5. Square to circle

6. 3D shadow

7. Swing


8. Inset border



Reading
CSS Transforms
What does a CSS transform allow the developer to do to an element?
A CSS transform lets a developer change the visual appearance and position of an element without affecting the normal layout of the page.

🧠 In simple terms:
It allows you to move, rotate, scale, or skew an element. 
 Skew to tilt change the shape size and position without changing the layout of nudge page 

Provide an example of a transform and how you could see that being used on a website.
🎯 Example of a CSS transform
button:hover {
 transform: scale(1.1);
}
Does not intrude on neighbors does not change layout, just has affect when engaged 
 What it does
When the user hovers over the button


The button becomes 10% larger


It creates a smooth, interactive feel



CSS Transitions & Animations
What does a CSS transition allow the developer to do to an element?
A CSS transition allows a developer to control how smoothly an element changes from one style to another over time.

🧠 In simple terms:
It lets you animate changes instead of having them happen instantly.
button {
  background-color: green;
  transition: background-color 0.3s;
}

button:hover {
  background-color: darkgreen;
}
What happens
Without transition → color changes instantly


With transition → color fades smoothly over 0.3 seconds


How does a CSS animation differ from a CSS transition?
Key difference
👉 Transitions happen between two states
 👉 Animations can have multiple steps and run on their own
🎯 CSS Transition
Needs a trigger (like hover, click, focus)


Goes from start → end


Simple and short

A CSS transition creates a smooth change between two states when triggered (such as on hover), while a CSS animation can run automatically and uses @keyframes to define multiple steps and stages more complex movements.
If you want a quick way to remember:
👉 Transition = simple change 2 steps
 👉 Animation = full motion sequence multiple steps


8 simple CSS3 transitions that will wow your users
What are some benefits to using CSS transitions on websites?
Improves user experience
Makes interactions feel smooth and natural


Instead of abrupt changes, elements fade, move, or resize gradually
Improves user experience
Makes interactions feel smooth and natural


Instead of abrupt changes, elements fade, move, or resize gradually
Helps users understand what’s happening
Makes websites feel more modern
Adds polish and professionalism   
Handled by the browser 



How this topic fit in with your long-term goals?
Companies expect you to understand Basic ux and ui affects 

UX (User Experience) and UI (User Interface) are two distinct but interconnected disciplines in product design. 

Baymard +2
The Core Difference
UX (User Experience): Focuses on the overall feel of the experience and how easy or pleasant it is for a user to accomplish their goals. It is analytical, structural, and rooted in user research to solve specific problems.
UI (User Interface): Focuses on the visual touchpoints—the actual screens, buttons, icons, and spacing the user interacts with. It aims to make the interface aesthetically pleasing, intuitive, and consistent with the brand. 

Figma +6


Static website into a user experience they want to come back to


