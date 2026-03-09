read-10.md
## Things I want to know more about
checklist to set the beginning of a website

Debugging HTML

Writing HTML is fine, but what if something goes wrong, and you can't work out where the error in the code is? 

Here, the error message is relatively easy to understand — "unterminated double quote string". If you look at the listing, you can probably see how println!(Hello, world!"); might logically be missing a double quote. However, error messages can quickly get more complicated and less easy to interpret as programs get bigger, and even simple cases can look a little intimidating to someone who doesn't know anything about Rust.

Debugging doesn't have to be scary though — the key to being comfortable with writing and debugging any code is familiarity with both the language and the associated tools.

HTML is not as complicated to understand as Rust. HTML is not compiled into a different form before parsing (it is interpreted, not compiled). And HTML's element syntax is arguably a lot easier to understand than a "real programming language" like Rust, JavaScript, or Python.

But first of all, what do we mean by permissive? Well, generally when you do something wrong in code, there are two main types of error that you'll come across:

Syntax errors: These are typos in your code that cause the program not to run, like the Rust error shown earlier. These are usually easy to fix as long as you are familiar with the language's syntax and know what the error messages mean.
Logic errors: These are errors where the syntax is actually correct, but the code is not doing what you intended it to, meaning that the program runs incorrectly. These are often harder to fix than syntax errors, as there isn't an error message to direct you to the source of the error.

HTML itself doesn't suffer from syntax errors because browsers parse it permissively, meaning that the page still displays even if there are syntax errors in the source code. Browsers have built-in rules to state how to interpret incorrectly-written HTML markup (often called invalid or badly-formed markup), changing it automatically to some valid markup.

For example, the following HTML snippet contains incorrectly nested elements:

html

Copy
<p>I didn't expect to find the <em>next-door neighbor's <strong>cat</em></strong> here!</p>
The closing </strong> tag should be before the closing </em> tag, but it is not — it is after it.

If you load this HTML into a browser then look at the rendered DOM, you'll see that the nesting has been corrected by the browser:

html

Copy
<p>
  I didn't expect to find the
  <em>next-door neighbor's <strong>cat</strong></em> here!
</p>
So why is this both good and bad? Well, in this case the browser has created the intended result, but as you'll see later on, this is not always the case. You'll always get something running, but the browser doesn't always get it right, which can cause problems. It is better to write correct markup in the first place.

Note: HTML is parsed permissively because when the web was first created, it was decided that getting content published was more important than making sure the syntax was absolutely correct.

So how do you find markup errors? Later on we will show you how to find errors in HTML using a tool called the HTML validator, but first we will show you how to inspect your HTML manually using a DOM inspector, and then explore what kinds of markup errors you might be looking for, and how the browser might interpret those.

Handling JavaScript
After the CSS has been handled, any JavaScript found on the page (either included in the HTML file, or fetched from external script files) is parsed, interpreted, compiled, and executed. This happens at some point before the final page rendering is completed — after all, some JavaScript may affect the rendering, for example by adding nodes to the DOM or modifying existing ones.

What other rendering steps are there?
Several other things happen during page rendering, but we won't discuss them all here. One notable additional occurrence worth mentioning is that an accessibility tree is built, based on the DOM, for assistive technologies (for example screen readers) to hook into, which enables people who are not able to see the rendered content to interact with it.

Front-end web development can sometimes be frustrating, and some people consider the browser to be a hostile programming environment. This is because, unlike other programming environments, it is much harder to make guarantees about the environment your code will run on. You cannot know ahead of time all the different combinations of operating system, browser, language, location, network connection, CPU, GPU, memory, battery life, etc., that your users will have, therefore you cannot guarantee a perfect user experience for all of them.

Modern browsers tend to implement web standards pretty consistently, but there is still a lot of uncertainty to navigate. As a web developer, you will need to embrace that uncertainty, programming defensively and being conservative with the features you use. This relies on adhering to the best practices outlined in the previous article.

On the upside, the web is also an awesome programming environment, for many reasons.

For a start, it is designed with universal access in mind. The web's basic state is accessible and linkable. Some of these basics are harder to achieve in other environments.
App delivery across the web is simple and powerful. You don't need to take your users through a complicated installation process: you just point them to a web address and off they go.
App updates are usually straightforward. In many cases, visitors can see new versions of an application when they reload their browser tab. You don't need to worry about getting visitors to regularly download and install software updates.
The web community is vibrant and helpful. As we discuss later on in our Research and learning article, there are lots of places you can go to ask for help, and great resources available to learn from.

Debugging CSS
Sometimes when writing CSS you will encounter an issue where your CSS doesn't seem to be doing what you expect. Perhaps you believe that a certain selector should match an element, but nothing happens, or a box is a different size than you expected. This article will give you guidance on how to go about debugging a CSS problem, and show you how the DevTools included in all modern browsers can help you to find out what is going on.

What are browser developer tools?
Every modern web browser includes a powerful suite of developer tools. These tools do a range of things, from inspecting currently-loaded HTML, CSS and JavaScript to showing which assets the page has requested and how long they took to load. This article explains how to use the basic functions of your browser's devtools.

The JavaScript debugger
The JavaScript debugger allows you to watch the value of variables and set breakpoints, places in your code that you want to pause execution and identify the problems that prevent your code from executing properly.

Exploring the debugger
Each browser's JavaScript debugger is divided into three panes. The layout of these is somewhat different depending on the browser you are using; this guide uses Firefox as a reference.

The JavaScript debugger (found in the Sources or Debugger tab of browser developer tools) is typically divided into these three panes: 
File Navigator (Left Pane): Lists all the files loaded by the page, such as HTML, JavaScript, and CSS. You use this to find and select the specific script you want to debug.
Code Editor (Middle Pane): Displays the source code of the file selected in the navigator. This is where you can view the code, edit it directly, and set breakpoints by clicking on line numbers.
JavaScript Debugging Pane (Right Pane): Contains various tools for inspecting and controlling the execution of your code. It is further divided into collapsible sections, including:
Watch: For tracking the values of specific JavaScript expressions.
Call Stack: Shows the list of functions that were called to reach the current point of execution.
Scope: Displays the variables currently in scope and their values.
Breakpoints: Lists all the breakpoints you have set throughout your files. 
Chrome for Developers

In the rendered DOM the browser may have normalized the HTML, for example by correcting some badly-written HTML for you. If you incorrectly closed an element, for instance by opening an <h2> but closing with an </h3>, the browser will figure out what you were meaning to do and the HTML in the DOM will correctly close the open <h2> with an </h2>. The DOM will also show any changes made by JavaScript.
Understanding the box model
In previous lessons we have discussed the box model, and the fact that we have an alternate box model that changes how the size of elements are calculated based on the size you give them, plus the padding and borders. DevTools can really help you to understand how the size of an element is being calculated.

Layout view
The Layout view displays the box model of the page. If the page includes any sections using either the Flexbox display model or CSS Grids, this view shows the Flexbox or Grid settings used on the page.

Summary
So there we have it: an introduction to debugging CSS, which should give you some useful skills to count on when you start to debug CSS and other types of code later on in your career.

That's it for all the lessons in this module. To finish it off, we'll test your knowledge of the topics covered with a series of challenges.