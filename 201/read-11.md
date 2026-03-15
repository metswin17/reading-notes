Reading
Video and Audio Content
Explain how the ability to use video and audio on the web has evolved since the early 2000s.
Third party download plug ins  HTML % had built in video elements. No more plug ins and mobile control. Less problems 

Describe the use of the src and controls attributes in the <video> element.
Src the src tells browser where file is located on computer or link web. 
Controls tells browser to display built in play pause and full screen buttons 
Video 

Why is it important to have fallback content inside the <video> element?
In case video does not load, its the alt backup
User with older browser still sees a message. 
Write a very short story where <audio> and <video> are characters.
Hey Audio, can you speak up I can’t hear you. 
Alright video but it would be helpful if you could run so I can see where I need to speak

A Complete Guide To Grid
How does Grid layout differ from Flex?
The fundamental difference between CSS Grid and Flexbox is their dimensionality: Flexbox is designed for one-dimensional layouts row or column 
, while Grid is built for two-dimensional layouts. Rows and columns at the same time good for full entire page
Grid container, grid item, and grid line are a few important terms to understand when using Grid. Please describe these terms in a few sentences.
Grid Container: This is the parent element that has display: grid or display: inline-grid applied to it. It establishes the new grid formatting context for all its contents.
Grid Item: These are the direct child elements of a grid container. Once the parent becomes a container, these children are automatically positioned according to the grid's rules. Any direct child of the grid container. Grid container and grid items
Grid Line: These are the horizontal and vertical dividing lines that form the structure of the grid. They are referenced by numbers (starting at 1) or names to precisely place grid items across specific rows or columns
The paper is the grid container the boxes you place on the grid are grid items and graph lines are the grid lines of the container 
Responsive Images
Besides making a site visually appealing across different screen sizes, why should developers make images responsive?
Mobile and desktop and tablet display adjustments reduces data usage . better for SEO i proves user experience. No oversize images. Looks good on all devises 

Define the following <img> attributes srcset and sizes. Write an example of how they are used.
Definitions
srcset: A list of image files and their widths (using the w descriptor) or pixel densities (using x). This tells the browser which files are available and how large they are. Tells multiple 
sizes: A set of conditions (media queries) that tell the browser how much space the image will occupy on the screen (e.g., 100% of the viewport or a fixed pixel width). Tells how much screen space the image will take up. Only addresses specific images being worked on. 



How is srcset more helpful for responsive images than CSS or JavaScript?
Prevents larger images from loading unnecessarily. Lets browser make smartest choice immediately
srcset is more helpful than CSS or JavaScript because it allows the browser to make intelligent loading decisions before the page even finishes parsing, which significantly improves performance.
1. Speed and the "Pre-loader"
The Problem with JS/CSS: Browsers typically start downloading images as soon as they see them in the HTML. If you use JavaScript to swap images, the browser might download the default src first and then download a second, responsive version later, wasting bandwidth.
The srcset Advantage: Because srcset is part of the HTML, the browser's preload scanner can see the image options immediately. It picks the correct version and starts the download before any CSS or JavaScript is even loaded or executed. 
Context Awareness, Dynamic Selection
Bookmark and Review
Images in HTML
This article is review from Class 05.
Other Embedding Technologies

Dot . push an array function
. for each runs for evey single item in the list 

Most commonly used Array methods in JS 
Example array:


``` javascript
const numbers = [1, 2, 3, 4, 5];
```


------------------------------------------------------------------------


# 1. forEach()


## What it does


Runs a function **once for every item in the array**.


## Example


``` javascript
const numbers = [1, 2, 3];


numbers.forEach(function(num) {
  console.log(num);
});
```


## Output


    1
    2
    3


## Simple Explanation


`forEach()` is used when you want to **do something with every item**,
like printing them or updating them.



# 2. map()


## What it does


Creates a **new array** by changing each item in the original array.


## Example


``` javascript
const numbers = [1, 2, 3];


const doubled = numbers.map(function(num) {
  return num * 2;
});


console.log(doubled);
```


## Output


    [2, 4, 6]


## Simple Explanation


`map()` takes each value, **changes it**, and returns a **new array**.


# 3. filter()


## What it does


Creates a **new array with only items that match a condition**.


## Example


``` javascript
const numbers = [1, 2, 3, 4, 5];


const evens = numbers.filter(function(num) {
  return num % 2 === 0;
});


console.log(evens);
```


## Output


    [2, 4]


## Simple Explanation


`filter()` **removes items you don't want**.



% is the Remainder operator  2 asks for even numbers 1 ask for odd



 4. reduce()


## What it does


Combines all values into **one final value**.


## Example


``` javascript
const numbers = [1, 2, 3, 4];


const total = numbers.reduce(function(sum, num) {
  return sum + num;
}, 0);


console.log(total);
```


## Output


    10


## Simple Explanation


`reduce()` is often used for **totals, averages, or calculations**.




# 5. includes()


## What it does


Checks if an array **contains a value**.


## Example


``` javascript
const fruits = ['apple', 'banana', 'orange'];


console.log(fruits.includes('banana'));
```


## Output


    true


## Simple Explanation


Returns **true or false** depending on whether the value exists.


------------------------------------------------------------------------


# 6. find()


## What it does


Returns the **first item that matches a condition**.


## Example


``` javascript
const numbers = [5, 10, 15];


const result = numbers.find(function(num) {
  return num > 8;
});


console.log(result);
```


## Output


    10


## Simple Explanation


`find()` returns **the first match only**.


------------------------------------------------------------------------


# 7. push()


## What it does


Adds a new item to the **end of the array**.


## Example


``` javascript
const fruits = ['apple', 'banana'];


fruits.push('orange');


console.log(fruits);
```


## Output


    ['apple', 'banana', 'orange']


## Simple Explanation


`push()` **adds something to the end**.


------------------------------------------------------------------------


# 8. pop()


## What it does


Removes the **last item** from the array.


## Example


``` javascript
const fruits = ['apple', 'banana', 'orange'];


fruits.pop();


console.log(fruits);
```


## Output


    ['apple', 'banana']


## Simple Explanation


`pop()` **removes the last item**.


------------------------------------------------------------------------


# 9. shift()


## What it does


Removes the **first item** from the array.


## Example


``` javascript
const fruits = ['apple', 'banana', 'orange'];


fruits.shift();


console.log(fruits);
```


## Output


    ['banana', 'orange']


## Simple Explanation


`shift()` removes **the first item**.


------------------------------------------------------------------------


# 10. unshift()


## What it does


Adds a new item to the **beginning of the array**.


## Example


``` javascript
const fruits = ['banana', 'orange'];


fruits.unshift('apple');


console.log(fruits);
```


## Output


    ['apple', 'banana', 'orange']


## Simple Explanation


`unshift()` **adds something to the front**.


------------------------------------------------------------------------


# Quick Summary


  Method       What it does
  ------------ -----------------------------------
  forEach()    Loop through each item
  map()        Create a new changed array
  filter()     Keep items that match a condition
  reduce()     Combine values into one
  includes()   Check if value exists
  find()       Get the first matching item
  push()       Add item to end
  pop()        Remove item from end
  shift()      Remove first item
  unshift()    Add item to beginning


------------------------------------------------------------------------


# Final Tip


A good rule of thumb:


-   **map()** → transform data\
-   **filter()** → remove unwanted data\
-   **reduce()** → calculate something\
-   **forEach()** → just loop through items


Grid two dimensional 2 rows Grid is better to use. To align items both vertically and horizontally
When flexbox alone is not enough. 

Grid container the parent element where we use 

display: grid;  

Grid items child item inside the container
Grid track space between the grid lines column or a row

Cel intersection between a row and an item

Grid \: template; columns 
Define the width of each column
1fr 2fr 3fr the width of 3 columns  frame fr 

Grid: template; row
 100 px 200 px 

grid :gap  sets space between rows and columns 

Justify items Horizontal center , left , right items aligns items
Align items - aligns items vertically 

Grid template areas 
Names areas (places)  in the grid for easy placements 

Properties
Grid column specifies which column and item sans  ⅓ 
Start 1st line end on 3rd multi rows
Grid row 2/4
Start on line 2 ends on 4 

Justify self 
Overrides justify item. 1 item needs adjustment

Align self overrides the align item  1 only  


The first influx of online videos and audio were made possible by proprietary plugin-based technologies like Flash and Silverlight. Both of these had security and accessibility issues, and are now obsolete, in favor of native HTML solutions <video> and <audio> elements and the availability of JavaScript APIs for controlling them. We'll not be looking at JavaScript here — just the basic foundations that can be achieved with HTML.

First, let's go through the terminology quickly. Formats like OGG, WAV, MP4 and WebM are called container formats. They define a structure in which the audio and/or video tracks that make up the media are stored, along with metadata describing the media, what codecs are used to encode its channels, and so forth. 
The audio and video tracks within the container hold data in the appropriate format for the codec used to encode that media. Different formats are used for audio tracks versus video tracks. Each audio track is encoded using an audio codec, while video tracks are encoded using (as you probably have guessed) a video codec. As we talked about before, different browsers support different video and audio formats, and different container formats (like OGG, MP4, and WebM, which in turn can contain different types of video and audio).
For example:
A WebM container typically packages Vorbis or Opus audio with VP8/VP9 video. This is supported in all modern browsers, though older versions may not work.
An MP4 container often packages AAC or MP3 audio with H.264 video. This is also supported in all modern browsers.
The Ogg container tends to use Vorbis audio and Theora video. This is best supported in Firefox and Chrome, but has basically been superseded by the better quality WebM format.
The codecs described in the previous section exist to compress video and audio into manageable files, since raw audio and video are both exceedingly large.

Due to the intricacies of ensuring your app's media is viewable across every combination of browsers, platforms, and devices you wish to reach, choosing the best combination of codecs and container can be a complicated task

One additional thing to keep in mind: mobile browsers may support additional formats not supported by their desktop equivalents, just like they may not support all the same formats the desktop version does.

Features include:
width and height
You can control the video size either with these attributes or with CSS. In both cases, videos maintain their native width-height ratio — known as the aspect ratio. If the aspect ratio is not maintained by the sizes you set, the video will grow to fill the space horizontally, and the unfilled space will just be given a solid background color by default.
autoplay
Makes the audio or video start playing right away, while the rest of the page is loading. You are advised not to use autoplaying video (or audio) on your sites, because users can find it really annoying.
loop
Makes the video (or audio) start playing again whenever it finishes. This can also be annoying, so only use if really necessary.
muted
Causes the media to play with the sound turned off by default.
poster
The URL of an image which will be displayed before the video is played. It is intended to be used for a splash screen or advertising screen.
preload
Used for buffering large files; it can take one of three values:
"none" does not buffer the file
"auto" buffers the media file
"metadata" buffers only the metadata for the file


Key Terms
Before diving into the concepts of CSS Grid, it’s important to understand the terminology. Since the terms involved here are all kinda conceptually similar, it’s easy to confuse them with one another if you don’t first memorize their meanings defined by the CSS Grid specification. But don’t worry, there aren’t many of them.
Grid Container
The element on which display: grid is applied. It’s the direct parent of all the grid items. In this example container is the grid container.
<div class="container">
  <div class="item item-1"> </div>
  <div class="item item-2"> </div>
  <div class="item item-3"> </div>
</div>
Grid Item
The children (i.e. direct descendants) of the grid container. Here the item elements are grid items, but sub-item isn’t.
<div class="container">
  <div class="item"> </div>
  <div class="item">
    <p class="sub-item"> </p>
  </div>
  <div class="item"> </div>
</div>
Grid Line
The dividing lines that make up the structure of the grid. They can be either vertical (“column grid lines”) or horizontal (“row grid lines”) and reside on either side of a row or column. Here the yellow line is an example of a column grid line.
Grid Track
The space between two adjacent grid lines. You can think of them as the columns or rows of the grid. Here’s the grid track between the second and third-row grid lines.
Grid Area
The total space surrounded by four grid lines. A grid area may be composed of any number of grid cells. Here’s the grid area between row grid lines 1 and 3, and column grid lines 1 and 3.
Grid Cell
The space between two adjacent row and two adjacent column grid lines. It’s a single “unit” of the grid. Here’s the grid cell between row grid lines 1 and 2, and column grid lines 2 and 3.

CSS Grid Properties

Parent Container Properties
display
Defines the element as a grid container and establishes a new grid formatting context for its contents.
Values:
grid: Generates a block-level grid
inline-grid: Generates an inline-level grid
.container {
  display: grid | inline-grid;
}
The ability to pass grid parameters down through nested elements (aka subgrids) has been moved to CSS Grid Specification Level 2. Here’s a quick explanation.
grid-template-*
Defines the columns and rows of the grid with a space-separated list of values. The values represent the track size, and the space between them represents the grid line.
Values:
<track-size>: Can be a length, a percentage, or a fraction of the free space in the grid using the fr unit.
<line-name>: An arbitrary name of your choosing.
.container {
  grid-template-columns: ...  ...;
  /* e.g. 
      1fr 1fr
      minmax(10px, 1fr) 3fr
      repeat(5, 1fr)
      50px auto 100px 1fr
  */
  grid-template-rows: ... ...;
  /* e.g. 
      min-content 1fr min-content
      100px 1fr max-content
  */
}
Grid lines are automatically assigned positive numbers from these assignments (-1 being an alternate for the very last row).

But you can choose to explicitly name the lines. Note the bracket syntax for the line names:
.container {
  grid-template-columns: [first] 40px [line2] 50px [line3] auto [col4-start] 50px [five] 40px [end];
  grid-template-rows: [row1-start] 25% [row1-end] 100px [third-line] auto [last-line];
}

Note that a line can have more than one name. For example, here the second line will have two names: row1-end and row2-start:
.container {
  grid-template-rows: [row1-start] 25% [row1-end row2-start] 25% [row2-end];
}
If your definition contains repeating parts, you can use the repeat() notation to streamline things:
.container {
  grid-template-columns: repeat(3, 20px [col-start]);
}
Which is equivalent to this:
.container {
  grid-template-columns: 20px [col-start] 20px [col-start] 20px [col-start];
}
If multiple lines share the same name, they can be referenced by their line name and count.
.item {
  grid-column-start: col-start 2;
}
The fr unit allows you to set the size of a track as a fraction of the free space of the grid container. For example, this will set each item to one third the width of the grid container:
.container {
  grid-template-columns: 1fr 1fr 1fr;
}
The free space is calculated after any non-flexible items. In this example the total amount of free space available to the fr units doesn’t include the 50px:
.container {
  grid-template-columns: 1fr 50px 1fr 1fr;
}
Continue Reading
grid-template
A shorthand for setting grid-template-rows, grid-template-columns, and grid-template-areas in a single declaration.
Values:
none:  Sets all three properties to their initial values.
<grid-template-rows> / <grid-template-columns>: Sets grid-template-columns and grid-template-rows to the specified values, respectively, and sets grid-template-areas to none
.container {
  grid-template: none | <grid-template-rows> / <grid-template-columns>;
}
It also accepts a more complex but quite handy syntax for specifying all three. Here’s an example:
.container {
  grid-template:
    [row1-start] "header header header" 25px [row1-end]
    [row2-start] "footer footer footer" 25px [row2-end]
    / auto 50px auto;
}
That’s equivalent to this:
.container {
  grid-template-rows: [row1-start] 25px [row1-end row2-start] 25px [row2-end];
  grid-template-columns: auto 50px auto;
  grid-template-areas: 
    "header header header" 
    "footer footer footer";
}
Since grid-template doesn’t reset the implicit grid properties (grid-auto-columns, grid-auto-rows, and grid-auto-flow), which is probably what you want to do in most cases, it’s recommended to use the grid property instead of grid-template.
Continue Reading
grid-template-areas
Defines a grid template by referencing the names of the grid areas which are specified with the grid-area property. Repeating the name of a grid area causes the content to span those cells. A period signifies an empty cell. The syntax itself provides a visualization of the structure of the grid.
Values:
<grid-area-name>: The name of a grid area specified with grid-area.
.: A period signifies an empty grid cell.
none: No grid areas are defined.
.container {
  grid-template-areas: 
    "<grid-area-name> | . | none | ..."
    "...";
}
Example:
.item-a {
  grid-area: header;
}
.item-b {
  grid-area: main;
}
.item-c {
  grid-area: sidebar;
}
.item-d {
  grid-area: footer;
}

.container {
  display: grid;
  grid-template-columns: 50px 50px 50px 50px;
  grid-template-rows: auto;
  grid-template-areas: 
    "header header header header"
    "main main . sidebar"
    "footer footer footer footer";
}
That’ll create a grid that’s four columns wide by three rows tall. The entire top row will be composed of the header area. The middle row will be composed of two main areas, one empty cell, and one sidebar area. The last row is all footer.

Each row in your declaration needs to have the same number of cells.
You can use any number of adjacent periods to declare a single empty cell. As long as the periods have no spaces between them they represent a single cell.
Notice that you’re not naming lines with this syntax, just areas. When you use this syntax the lines on either end of the areas are actually getting named automatically. If the name of your grid area is foo, the name of the area’s starting row line and starting column line will be foo-start, and the name of its last row line and last column line will be foo-end. This means that some lines might have multiple names, such as the far left line in the above example, which will have three names: header-start, main-start, and footer-start.
Continue Reading
grid
A shorthand for setting all of the following properties in a single declaration: grid-template-rows, grid-template-columns, grid-template-areas, grid-auto-rows, grid-auto-columns, and grid-auto-flow 
You can only specify the explicit or the implicit grid properties in a single grid declaration.
Values:
none: Sets all sub-properties to their initial values.
<grid-template>: Works the same as the grid-template shorthand.
<grid-template-rows> / [ auto-flow && dense? ] <grid-auto-columns>?: Sets grid-template-rows to the specified value. If the auto-flow keyword is to the right of the slash, it sets grid-auto-flow to column. If the dense keyword is specified additionally, the auto-placement algorithm uses a “dense” packing algorithm. If grid-auto-columns is omitted, it is set to auto.
[ auto-flow && dense? ] <grid-auto-rows>? / <grid-template-columns>: Sets grid-template-columns to the specified value. If the auto-flow keyword is to the left of the slash, it sets grid-auto-flow to row. If the dense keyword is specified additionally, the auto-placement algorithm uses a “dense” packing algorithm. If grid-auto-rows is omitted, it is set to auto.
Examples:
The following two code blocks are equivalent:
.container {
  grid: 100px 300px / 3fr 1fr;
}

.container {
  grid-template-rows: 100px 300px;
  grid-template-columns: 3fr 1fr;
}
The following two code blocks are equivalent:
.container {
  grid: auto-flow / 200px 1fr;
}

.container {
  grid-auto-flow: row;
  grid-template-columns: 200px 1fr;
}
The following two code blocks are equivalent:
.container {
  grid: auto-flow dense 100px / 1fr 2fr;
}

.container {
  grid-auto-flow: row dense;
  grid-auto-rows: 100px;
  grid-template-columns: 1fr 2fr;
}
And the following two code blocks are equivalent:
.container {
  grid: 100px 300px / auto-flow 200px;
}

.container {
  grid-template-rows: 100px 300px;
  grid-auto-flow: column;
  grid-auto-columns: 200px;
}
It also accepts a more complex but quite handy syntax for setting everything at once. You specify grid-template-areas, grid-template-rows and grid-template-columns, and all the other sub-properties are set to their initial values. What you’re doing is specifying the line names and track sizes inline with their respective grid areas. This is easiest to describe with an example:
.container {
  grid: [row1-start] "header header header" 1fr [row1-end]
        [row2-start] "footer footer footer" 25px [row2-end]
        / auto 50px auto;
}
That’s equivalent to this:
.container {
  grid-template-areas: 
    "header header header"
    "footer footer footer";
  grid-template-rows: [row1-start] 1fr [row1-end row2-start] 25px [row2-end];
  grid-template-columns: auto 50px auto;    
}
Continue Reading
justify-items
Aligns grid items along the inline (row) axis (as opposed to align-items which aligns along the block (column) axis). This value applies to all grid items inside the container.
Values:
stretch (default): Fills the whole width of the cell.
start: Aligns items to be flush with the start edge of their cell
end: Aligns items to be flush with the end edge of their cell
center: Aligns items in the center of their cell
.container {
  justify-items: start | end | center | stretch;
}
Examples:
.container {
  justify-items: start;
}

.container {
  justify-items: end;
}

.container {
  justify-items: center;
}

.container {
  justify-items: stretch;
}

This behavior can also be set on individual grid items via the justify-self property.
Continue Reading
align-items
Aligns grid items along the block (column) axis (as opposed to justify-items which aligns along the inline (row) axis). This value applies to all grid items inside the container.
Values:
stretch (default): Fills the whole height of the cell (this is the default)
start: Aligns items to be flush with the start edge of their cell
end: Aligns items to be flush with the end edge of their cell
center: Aligns items in the center of their cell
baseline: Align items along text baseline. There are modifiers to baseline — first baseline and last baseline which will use the baseline from the first or last line in the case of multi-line text.
.container {
  align-items: start | end | center | stretch;
}
Examples:
.container {
  align-items: start;
}

.container {
  align-items: end;
}

.container {
  align-items: center;
}

.container {
  align-items: stretch;
}

This behavior can also be set on individual grid items via the align-self property.
There are also modifier keywords safe and unsafe (usage is like align-items: safe end). The safe keyword means “try to align like this, but not if it means aligning an item such that it moves into inaccessible overflow area”, while unsafe will allow moving content into inaccessible areas (“data loss”).
Continue Reading
place-items
place-items sets both the align-items and justify-items properties in a single declaration.
Values:
<align-items> / <justify-items>: The first value sets align-items, the second value justify-items. If the second value is omitted, the first value is assigned to both properties.
This can be very useful for super quick multi-directional centering:
.center {
  display: grid;
  place-items: center;
}
Continue Reading
justify-content
Sometimes the total size of your grid might be less than the size of its grid container. This could happen if all of your grid items are sized with non-flexible units like px. In this case you can set the alignment of the grid within the grid container. This property aligns the grid along the inline (row) axis (as opposed to align-content which aligns the grid along the block (column) axis).
Values:
start: Aligns the grid to be flush with the start edge of the grid container.
end: Aligns the grid to be flush with the end edge of the grid container.
center: Aligns the grid in the center of the grid container.
stretch: Resizes the grid items to allow the grid to fill the full width of the grid container.
space-around: Places an even amount of space between each grid item, with half-sized spaces on the far ends.
space-between: Places an even amount of space between each grid item, with no space at the far ends.
space-evenly: Places an even amount of space between each grid item, including the far ends.
.container {
  justify-content: start | end | center | stretch | space-around | space-between | space-evenly;    
}
Examples:
.container {
  justify-content: start;
}

.container {
  justify-content: end;    
}

.container {
  justify-content: center;    
}

.container {
  justify-content: stretch;    
}

.container {
  justify-content: space-around;    
}

.container {
  justify-content: space-between;    
}

.container {
  justify-content: space-evenly;    
}

Continue Reading
align-content
Sometimes the total size of your grid might be less than the size of its grid container. This could happen if all of your grid items are sized with non-flexible units like px. In this case you can set the alignment of the grid within the grid container. This property aligns the grid along the block (column) axis (as opposed to justify-content which aligns the grid along the inline (row) axis).
Values:
start: Aligns the grid to be flush with the start edge of the grid container.
end: Aligns the grid to be flush with the end edge of the grid container.
center: Aligns the grid in the center of the grid container.
stretch: Resizes the grid items to allow the grid to fill the full height of the grid container.
space-around: Places an even amount of space between each grid item, with half-sized spaces on the far ends.
space-between: Places an even amount of space between each grid item, with no space at the far ends.
space-evenly: Places an even amount of space between each grid item, including the far ends.
.container {
  align-content: start | end | center | stretch | space-around | space-between | space-evenly;    
}
Examples:
.container {
  align-content: start;    
}

.container {
  align-content: end;    
}

.container {
  align-content: center;    
}

.container {
  align-content: stretch;    
}

.container {
  align-content: space-around;    
}

.container {
  align-content: space-between;    
}

.container {
  align-content: space-evenly;    
}

Continue Reading
place-content
place-content sets both the align-content and justify-content properties in a single declaration.
Values:
<align-content> / <justify-content>: The first value sets align-content, the second value justify-content. If the second value is omitted, the first value is assigned to both properties.
Continue Reading
grid-auto-*
Specifies the size of any auto-generated grid tracks (aka implicit grid tracks). Implicit tracks get created when there are more grid items than cells in the grid or when a grid item is placed outside of the explicit grid. (See The Difference Between Explicit and Implicit Grids.)
Values:
<track-size>: Can be a length, a percentage, or a fraction of the free space in the grid (using the fr unit).
.container {
  grid-auto-columns: <track-size> ...;
  grid-auto-rows: <track-size> ...;
}
To illustrate how implicit grid tracks get created, think about this:
.container {
  grid-template-columns: 60px 60px;
  grid-template-rows: 90px 90px;
}

This creates a 2×2 grid.
But now imagine you use grid-column and grid-row to position your grid items like this:
.item-a {
  grid-column: 1 / 2;
  grid-row: 2 / 3;
}
.item-b {
  grid-column: 5 / 6;
  grid-row: 2 / 3;
}

We told .item-b to start on column line 5 and end at column line 6, but we never defined a column line 5 or 6. Because we referenced lines that don’t exist, implicit tracks with widths of 0 are created to fill in the gaps. We can use grid-auto-columns and grid-auto-rows to specify the widths of these implicit tracks:
.container {
  grid-auto-columns: 60px;
}

Continue Reading
grid-auto-flow
If you have grid items that you don’t explicitly place on the grid, the auto-placement algorithm kicks in to automatically place the items. This property controls how the auto-placement algorithm works.
Values:
row: Tells the auto-placement algorithm to fill in each row in turn, adding new rows as necessary (default)
column: Tells the auto-placement algorithm to fill in each column in turn, adding new columns as necessary
dense: Tells the auto-placement algorithm to attempt to fill in holes earlier in the grid if smaller items come up later
.container {
  grid-auto-flow: row | column | row dense | column dense;
}
Note that dense only changes the visual order of your items and might cause them to appear out of order, which is bad for accessibility.
Examples:
<section class="container">
  <div class="item-a">item-a</div>
  <div class="item-b">item-b</div>
  <div class="item-c">item-c</div>
  <div class="item-d">item-d</div>
  <div class="item-e">item-e</div>
</section>
You define a grid with five columns and two rows, and set grid-auto-flow to row (which is also the default):
.container {
  display: grid;
  grid-template-columns: 60px 60px 60px 60px 60px;
  grid-template-rows: 30px 30px;
  grid-auto-flow: row;
}
When placing the items on the grid, you only specify spots for two of them:
.item-a {
  grid-column: 1;
  grid-row: 1 / 3;
}

.item-e {
  grid-column: 5;
  grid-row: 1 / 3;
}
Because we set grid-auto-flow to row, our grid will look like this. Notice how the three items we didn’t place (item-b, item-c and item-d) flow across the available rows:

If we instead set grid-auto-flow to column, item-b, item-c and item-d flow down the columns:
.container {
  display: grid;
  grid-template-columns: 60px 60px 60px 60px 60px;
  grid-template-rows: 30px 30px;
  grid-auto-flow: column;
}

Continue Reading
gap
The gap property explicitly controls the space between flex items. It applies that spacing only between items not on the outer edges. It is a shorthand that combines the row-gap and column-gap properties.
.container {
  display: flex;
  /* ... */
  gap: 10px;
  gap: 10px 20px; /* row-gap column gap */
  row-gap: 10px;
  column-gap: 20px;
}
The behavior could be thought of as a minimum gutter, as if the gutter is bigger somehow (because of something like justify-content: space-between;) then the gap will only take effect if that space would end up smaller.
It is not exclusively for CSS Grid, gap works in Flexbox and multi-column layout as well.
Continue Reading

Child Item Properties
grid-column-*
grid-row-*
Determines a grid item’s location within the grid by referring to specific grid lines. grid-column-start/grid-row-start is the line where the item begins, and grid-column-end/grid-row-end is the line where the item ends.
Values:
<line>: Can be a number to refer to a numbered grid line, or a name to refer to a named grid line.
span <number>: The item will span across the provided number of grid tracks.
span <name>: The item will span across until it hits the next line with the provided name.
auto: Indicates auto-placement, an automatic span, or a default span of one.
.item {
  grid-column-start: <number> | <name> | span <number> | span <name> | auto;
  grid-column-end: <number> | <name> | span <number> | span <name> | auto;
  grid-row-start: <number> | <name> | span <number> | span <name> | auto;
  grid-row-end: <number> | <name> | span <number> | span <name> | auto;
}
Examples:
.item-a {
  grid-column-start: 2;
  grid-column-end: five;
  grid-row-start: row1-start;
  grid-row-end: 3;
}

.item-b {
  grid-column-start: 1;
  grid-column-end: span col4-start;
  grid-row-start: 2;
  grid-row-end: span 2;
}

If no grid-column-end/grid-row-end is declared, the item will span 1 track by default.
Items can overlap each other. You can use z-index to control their stacking order.
grid-column
grid-row
Shorthand for grid-column-start + grid-column-end, and grid-row-start + grid-row-end, respectively.
Values:
<start-line> / <end-line>: Each one accepts all the same values as the longhand version, including span
.item {
  grid-column: <start-line> / <end-line> | <start-line> / span <value>;
  grid-row: <start-line> / <end-line> | <start-line> / span <value>;
}
Example:
.item-c {
  grid-column: 3 / span 2;
  grid-row: third-line / 4;
}

If no end line value is declared, the item will span 1 track by default.
grid-area
Gives an item a name so that it can be referenced by a template created with the grid-template-areas property. Alternatively, this property can be used as an even shorter shorthand for grid-row-start + grid-column-start + grid-row-end + grid-column-end.
Values:
<name>: A name of your choosing.
<row-start> / <column-start> / <row-end> / <column-end>: Can be numbers or named lines.
.item {
  grid-area: <name> | <row-start> / <column-start> / <row-end> / <column-end>;
}
Examples:
As a way to assign a name to the item:
.item-d {
  grid-area: header;
}
As the short-shorthand for grid-row-start + grid-column-start + grid-row-end + grid-column-end:
.item-d {
  grid-area: 1 / col4-start / last-line / 6;
}

Continue Reading
justify-self
Aligns a grid item inside a cell along the inline (row) axis (as opposed to align-self which aligns along the block (column) axis). This value applies to a grid item inside a single cell.
Values:
start: Aligns the grid item to be flush with the start edge of the cell
end: Aligns the grid item to be flush with the end edge of the cell
center: Aligns the grid item in the center of the cell
stretch: Fills the whole width of the cell (this is the default)
.item {
  justify-self: start | end | center | stretch;
}
Examples:
.item-a {
  justify-self: start;
}

.item-a {
  justify-self: end;
}

.item-a {
  justify-self: center;
}

.item-a {
  justify-self: stretch;
}

To set alignment for all the items in a grid, this behavior can also be set on the grid container via the justify-items property.
Continue Reading
align-self
Aligns a grid item inside a cell along the block (column) axis (as opposed to justify-self which aligns along the inline (row) axis). This value applies to the content inside a single grid item.
Values:
stretch (default): Fills the whole height of the cell.
start: Aligns the grid item to be flush with the start edge of the cell.
end: Aligns the grid item to be flush with the end edge of the cell.
center: Aligns the grid item in the center of the cell.
.item {
  align-self: start | end | center | stretch;
}
Examples:
.item-a {
  align-self: start;
}

.item-a {
  align-self: end;
}

.item-a {
  align-self: center;
}

.item-a {
  align-self: stretch;
}

To align all the items in a grid, this behavior can also be set on the grid container via the align-items property.
Continue Reading
place-self
place-self sets both the align-self and justify-self properties in a single declaration.
Values:
auto: The “default” alignment for the layout mode.
<align-self> / <justify-self>: The first value sets align-self, the second value justify-self. If the second value is omitted, the first value is assigned to both properties.
Examples:
.item-a {
  place-self: center;
}

.item-a {
  place-self: center stretch;
}

All major browsers except Edge support the place-self shorthand property.