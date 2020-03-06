# Read 01

## Responsive Web Design

> With the growth in mobile Internet usage comes the question of how to build websites suitable for all users.
>
> The industry response to this question has become _*responsive web design*_, also known as RWD.
>


* RWD is the practice of building a website suitable to work on every device and every screen size.
* Is focused around providing an intuitive and gratifying experience for everyone.
* *_Responsive*_ generally means to react quickly and positively to any change, such as viewport width.
* *_Adaptive*_ means to be easily modified for a new purpose or situation. These websites are built to a group of preset factors. 

>A combination of the two is ideal, providing the perfect formula for functional websites. Which term is used specifically doesn’t make a huge difference.

* Mobile generally means to build a separate website commonly on a new domain solely for mobile users.
* RWD dynamically adapts to different browser and device viewports, changing layout and content along the way. This solution has the benefits of being all three, responsive, adaptive, and mobile.

### Responsive web design is broken down into three main components

1. Flexible layouts.
1. Media queries.
1. Flexible media.

#### Flexible Layouts
Is the practice of building the layout of a website with a flexible grid, capable of dynamically resizing to any width. 

#### Flexible Grid
Let’s see how this formula works inside of a two column layout. Below we have a parent division with the class of container wrapping both the section and aside elements. The goal is to have have the section on the left and the aside on the right, with equal margins between the two. Normally the markup and styles for this layout would look a bit like the following.

#### Media Queries
Provide the ability to specify different styles for individual browser and device circumstances, the width of the viewport or device orientation for example. 


## All About Floats

Float is a CSS positioning property. Page elements with the CSS float property applied to them are just like the images in the print layout where the text flows around them. Floated elements remain a part of the flow of the web page. This is distinctly different than page elements that use absolute positioning. Absolutely positioned page elements are removed from the flow of the webpage, like when the text box in the print layout was told to ignore the page wrap. Absolutely positioned page elements will not affect the position of other elements and other elements will not affect them, whether they touch each other or not.

#### Valid values for the float property:
1. Left. 
1. Right.
1. None (the default) ensures the element will not float.
1. Inherit which will assume the float value from that elements parent element.