A design pattern that can be tricky in responsive design is a sidebar that sits inline with some content. Where there is viewport space, this pattern works great, but where space is condensed, that rigid layout can become problematic.

The Flexible Box Layout Model (flexbox) is a layout model designed for one-dimensional content. It excels at taking a bunch of items which have different sizes, and returning the best layout for those items.

This is the ideal layout model for this sidebar pattern. Flexbox not only helps lay the sidebar and content out inline, but where there's not enough space remaining, the sidebar will break onto a new line. Instead of setting rigid dimensions for the browser to follow, with flexbox, you can instead provide flexible boundaries to hint how the content could display.

They can display as a row, or a column.
They respect the writing mode of the document.
They are single line by default, but can be asked to wrap onto multiple lines.
Items in the layout can be visually reordered, away from their order in the DOM.
Space can be distributed inside the items, so they become bigger and smaller according to the space available in their parent.
Space can be distributed around the items and flex lines in a wrapped layout, using the Box Alignment properties.
The items themselves can be aligned on the cross axis.
Flex items move as a group on the main axis. Remember: we've got a bunch of things and we are trying to get the best layout for them as a group.
The cross axis runs in the other direction to the main axis, so if flex-direction is row the cross axis runs along the column.

To use flexbox you need to declare that you want to use a flex formatting context and not regular block and inline layout. Do this by changing the value of the display property to flex.

.container {
  display: flex;
}
Reversing the flow of items and accessibility
You should be cautious when using any properties that reorder the visual display away from how things are ordered in the HTML document, as it can negatively impact accessibility. The row-reverse and column-reverse values are a good example of this. The reordering only happens for the visual order, not the logical order. This is important to understand as the logical order is the order that a screen reader will read out the content, and anyone navigating using the keyboard will follow.
Therefore the way flex items behave by default is linked to the writing mode of the document. Most tutorials are written using English, or another horizontal, left to right writing mode. This would make it easy to assume that flex items line up on the left, and run horizontally.

To cause the items to grow, while allowing large items to have more space than small ones use flex:auto
The set of properties can be placed into two groups. Properties for space distribution, and properties for alignment. The properties which distribute space are:
justify-content: space distribution on the main axis.
align-content: space distribution on the cross axis.
place-content: a shorthand for setting both of the above properties.
The properties used for alignment in flexbox:
align-self: aligns a single item on the cross axis.
align-items: aligns all of the items as a group on the cross axis.
If you are working on the main axis then the properties begin with justify-. On the cross axis they begin with align-.
Why is there no justify-self in flexbox?
Flex items act as a group on the main axis. So there is no concept of splitting an individual item out of that group.
In grid layout the justify-self and justify-items properties work on the inline axis to do alignment of items on that axis within their grid area. Due to the way that flex layouts treat items as a group, these properties are not implemented in a flex context.
It is worth knowing that flexbox does work very nicely with auto margins. If you come across a need to split off one item from a group, or separate the group into two groups you can apply a margin to do this. In the example below the last item has a left margin of auto. The auto margin absorbs all space in the direction it is applied. This means that it pushes the item over to the right, thus splitting the groups.
## Things I want to know more about

How to choose the best flexbox for the task 

Learn CSS - Flexbox
Flexbox is designed for one-dimensional content. Explain what this means.
 refers to how it calculates space and aligns items
Flexbox is "one-dimensional" because its logic is almost entirely focused on how items pack together, stretch, or shrink along that Main Axis. 
Explain the difference between the main axis and cross axis.
The main axis is the one set by your flex-direction property. If that is row your main axis is along the row, if it is column your main axis is along the column.
How can using certain properties of flexbox negatively impact accessibility?
decouple visual presentation from the underlying HTML structure creates significant accessibility risks
CSS Layout - Flexbox
Read up to “Flex-Flow Shorthand”
What are some advantages of using flexbox over float?
While the float property was originally designed only for wrapping text around images, Flexbox was built specifically as a layout module to solve the limitations of floating elements. 

Reddit +2


How does this topic connect with your long term goals?
Powerful Alignment: Flexbox provides native properties like justify-content and align-items to easily center items or distribute space along a single axis. 
Equal Height Columns: In a flex container, child items can be made to have equal heights automatically, even if they have different amounts of content

