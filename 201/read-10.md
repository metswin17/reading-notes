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