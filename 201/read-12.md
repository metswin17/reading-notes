JavaScript Canvas
What does the <canvas> allow a developer to acheive?
Blank drawing area. Drawing charts with JS and media 
HTML creates the space and JS provides the visual
What is the importance of the closing `</canvas> tag?
The closing </canvas> tag is important because it provides fallback content for browsers that do not support the <canvas> element. 🌐
Why it matters
Anything placed between <canvas> and </canvas> will be displayed only if the browser cannot render the canvas.
This helps make the webpage more accessible and compatible with older browsers or assistive technologies.

Explain what the getContext() method does.
The getContext() method is used with the <canvas> element to get the drawing environment that allows JavaScript to create graphics on the canvas. 🎨
What it does
getContext() tells the browser what type of drawing context you want to use and returns an object that contains the methods and properties needed to draw.
Without calling getContext(), you cannot draw anything on the canvas.

Chart.js Documentation:
What is Chart.js and how it can be brought into your project?
Chart.js is a JavaScript library used to create charts and graphs in web applications. 📊 It works with the <canvas> element to display data visually, such as bar charts, line graphs, pie charts, and more.
Via CDN 

List 3 different Chart types you can create using Chart.js.
Using Chart.js, developers can create many types of charts. Three common chart types are:
📊 Bar Chart – Used to compare values across categories using rectangular bars.


📈 Line Chart – Shows trends or changes in data over time using connected points.


🥧 Pie Chart – Displays parts of a whole as slices of a circle.


✅ Short answer: Bar chart, line chart, and pie chart.

Easily Create Stunning Animated Charts with Chart.js
What are some advantages to displaying data via a chart over a table?
Displaying data with charts (such as those created using Chart.js) has several advantages over using a table. 📊
1. Easier to Understand
Charts present data visually, making it easier for people to quickly grasp information compared to reading rows and columns in a table.
2. Shows Patterns and Trends
Charts help highlight trends, comparisons, and relationships in the data (for example, increases or decreases over time).
3. Faster Interpretation
Users can quickly interpret key insights from a chart without analyzing many numbers.
4. More Engaging Visually
Charts are more visually appealing and interactive, which can keep users more engaged with the information.
✅ Short answer:
 Charts make data easier to understand, reveal trends and patterns quickly, and provide a more visual and engaging way to present information compared to tables. 📈

How could Chart.js aid your previously created applications visually?
Ways it could help visually
Turn raw numbers into charts
 Instead of showing only numbers in text or tables, the app could display them as bar charts, line graphs, or pie charts.


Show trends over time
 A line chart could visually display changes in data, such as growth, decreases, or patterns.


Improve user experience
 Charts make applications more engaging and easier to read, helping users quickly understand the information.


Highlight comparisons
 Charts allow users to compare values visually, which is often much faster than scanning a table.


✅ Short answer:
 Chart.js could enhance earlier applications by converting data into visual charts and graphs, making the information clearer, more engaging, and easier for users to interpret. 📈
[Drawing Shapes With Canvas](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_shapes){:target="_blank"}


[Applying Style and Colors - Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Applying_styles_and_colors){:target="_blank"}


[Drawing Text - Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_text){:target="_blank"}

CDN Content Delivery Network
Library for charts 
You have to have put a closing tag for canvas 
Libraries must load 1st otherwise chart will be undefined 
Has js charts to be above in the head not at the bottom js
App js goes bottom before the last body tag

Needs this const ctx = document.getElementById('chart').getContext('2d');

Chart,  Canvas and settings 

Chart , name of new instance 1 parameter is canvas and 2nd is settings.
 

Introduction to the HTML5 Canvas element
HTML5 features the <canvas> element that allows you to draw 2D graphics using JavaScript.
The <canvas> element requires at least two attributes: width and height that specify the size of the canvas:


Like other elements, you can access the width and height properties of the <canvas> element via its DOM properties:

This means you can use JavaScript to read or change the canvasresolution (internal pixel size) directly, similar to modifying HTML attributes likediv.id. Using canvas.widthorcanvas.height` in JS changes the drawing surface's resolution, whereas CSS only changes its display size.

Unlike the <img> element, The <canvas> element requires the closing tag </canvas>

All coordinate values are calculated in relation to the (0,0)  (top left corner square) with x increasing to the right and y increasing to the bottom.
By default, the width and height determine the number of pixels is available in each direction.
Fills and strokes
Summary
Use the HTML5 canvas element for drawing 2D graphics.
Use the getContext('2d') to get the 2D drawing context for drawing 2D graphics on canvas.
Use the fillStyle and StrokeStyle properties to set the styles for the 2D drawing context.
Chart.js is a free, open-source JavaScript library used for creating responsive and interactive charts and graphs on websites using the HTML5 <canvas> element. It helps developers visualize data in a variety of formats with minimal code
Why Chart.js
Among many charting libraries for JavaScript application developers, Chart.js is currently the most popular one according to GitHub stars (~60,000) and npm downloads (~2,400,000 weekly).
Chart.js was created and announced in 2013 but has come a long way since then. It’s open-source, licensed under the very permissive MIT license , and maintained by an active community.
Features
Chart.js provides a set of frequently used chart types, plugins, and customization options. In addition to a reasonable set of built-in chart types, you can use additional community-maintained chart types . On top of that, it’s possible to combine several chart types into a mixed chart (essentially, blending multiple chart types into one on the same canvas).
Chart.js is highly customizable with custom plugins to create annotations, zoom, or drag-and-drop functionalities to name a few things.
Defaults
Chart.js comes with a sound default configuration, making it very easy to start with and get an app that is ready for production. Chances are you will get a very appealing chart even if you don’t specify any options at all. For instance, Chart.js has animations turned on by default, so you can instantly bring attention to the story you’re telling with the data.
Integrations
Chart.js comes with built-in TypeScript typings and is compatible with all popular JavaScript frameworks including React , Vue , Svelte , and Angular . You can use Chart.js directly or leverage well-maintained wrapper packages that allow for a more native integration with your frameworks of choice.
Developer experience
Chart.js has very thorough documentation (yes, you're reading it), API reference, and examples. Maintainers and community members eagerly engage in conversations on Discord , GitHub Discussions , and Stack Overflow where more than 11,000 questions are tagged with chart.js.
Canvas rendering
Chart.js renders chart elements on an HTML5 canvas unlike several others, mostly D3.js-based, charting libraries that render as SVG. Canvas rendering makes Chart.js very performant, especially for large datasets and complex visualizations that would otherwise require thousands of SVG nodes in the DOM tree. At the same time, canvas rendering disallows CSS styling, so you will have to use built-in options for that, or create a custom plugin or chart type to render everything to your liking.
Performance
Chart.js is very well suited for large datasets. Such datasets can be efficiently ingested using the internal format, so you can skip data parsing and normalization. Alternatively, data decimation can be configured to sample the dataset and reduce its size before rendering.
In the end, the canvas rendering that Chart.js uses reduces the toll on your DOM tree in comparison to SVG rendering. Also, tree-shaking support allows you to include minimal parts of Chart.js code in your bundle, reducing bundle size and page load time.
Community
Chart.js is actively developed and maintained by the community. With minor releases on an approximately bi-monthly basis and major releases with breaking changes every couple of years, Chart.js keeps the balance between adding new features and making it a hassle to keep up with them.




