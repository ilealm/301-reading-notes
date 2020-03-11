# Read 03, Handlebars, Flexbox

## Handlebars
* Templating engine.
* Is based on the Mustache template language. 
* Handlebars separates the generation of HTML from the rest of your JavaScript and write cleaner code.

## Steps to implement it

### 0. Adding it to your project
* http://handlebarsjs.com/ to download button to get the latest version.
* Or use a CDN-hosted version, which has the added benefit that the same file might be cached already in the visitor's browser, if it has been used by another website.

> // From File
>
> `<script src="handlebars-v2.0.0.js"></script>`
>
> // From CDN
>
> `<script src="https://cdnjs.cloudflare.com/ajax/libs/handlebars.js/2.0.0/handlebars.js"></script>`

### 1. Templates
* The recommended way of adding templates to your page is by including them in `<script>` tags with a special type. 
* The type attribute is important, otherwise the browser will attempt to parse them as JavaScript (which they are not).
* Templates can contain HTML and text, mixed with Handlebars expressions. Expressions are wrapped in double or triple curly braces {{}}. Expressions tell Handlebars to include the value of variables or to execute helper functions. Templates need to be compiled to a JavaScript function before use

### 2. Expressions
* Any data that you print out in an {{ }} expression, will automatically get HTML escaped by handlebars. 
* For print raw HTML, you will use the triple curly brace expression {{{ }}}.

### 3. Context
* The object where properties you include in curly braces are looked up. 
* Every template you write has a context.

### 4. Helpers
* These are JavaScript functions that you can call from your templates, and help you reuse code and create complex templates. 
* To call a helper, just use it as an expression `- {{helpername}}`. 
* To can pass parameters as well `- {{helpername 12345}}`, which are passed as parameters to your helper function.

### 5. Block helpers
* They have an opening and a closing tag (like the #if and #each built-ins). 
* Helpers can modify the HTML and content they are wrapped around.
* Can use them to reuse functionality or to create large blocks of HTML in a reusable way.
* To create a block helper, you again use `Handlebars.registerHelper()`. The difference is that this time we will use the second parameter of our callback function - options


## Flexbox

* The Flexbox Layout (Flexible Box) module aims at providing a more efficient way to lay out, align and distribute space among items in a container, even when their size is unknown and/or dynamic (thus the word "flex").
* The main idea behind the flex layout is to give the container the ability to alter its items' width/height (and order) to best fill the available space.
* Flexbox layout is direction-agnostic as opposed to the regular layouts (block which is vertically-based and inline which is horizontally-based). 
* Flexbox layout is most appropriate to the components of an application, and small-scale layouts, while the Grid layout is intended for larger scale layouts.

### Examples

#### display
This defines a flex container; inline or block depending on the given value. It enables a flex context for all its direct children.

> `.container {
>  display: flex; /* or inline-flex */
> }`


#### flex-direction

>`.container {
>  flex-direction: row | row-reverse | column | column-reverse;
>}`

#### flex-wrap

>`.container{
>  flex-wrap: nowrap | wrap | wrap-reverse;
>}`

#### flex-flow (Applies to: parent flex container element)
> `flex-flow: <‘flex-direction’> || <‘flex-wrap’>`