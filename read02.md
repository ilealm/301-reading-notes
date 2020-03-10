# Read 02, jQuery, Events,  The DOM, and Reasons for Pair Programming

## jQuery
* jQuery is a simpler way to access elements. This selectors are more powerful and flexible.
* jQuery works in all browsers versions. 
* jQuery allows to update the DOM tree, animate elements, handle events, and loop thru a set of elements.
* jQuery is a file that is added in the web page.
* When one or more elements are selected, a jQuery object is returned.
* The process of placing several methods in the same selector is refered to as **chaining**.
* jQuery .ready() method checks that the page is ready for the code to work with.
* Scripts can be placed: in the head, in the page or before the closing tag `</body>`.

## Examples finding elements using CSS-style selectors

`$('li.hot')`

### Accessing element's methods
`$('li.hot').addClass('complete');`

### Getting information
`var content = $('li').html();`

### Setting information
`$('li').html('Updated');`

### Chaining
`$('li[id!="one"]').hide().delay(500).fadeIn(1400);`

## Event Object
* An event object is received in every event handling, and it has methods and properties. 

## Examples of Object Events Methods and Properties
.show()
.hide()
.toggle();
.slideUp();
.stop();


## Reasons for Pair Programming
1. Greater efficiency: 
When two people focus on the same code base, it is easier to catch mistakes in the making. 
2. Engaged collaboration:
When two programmers focus on the same code, the experience is more engaging and both programmers are more focused than if they were working alone. 
3. Learning from fellow students:
Often times, the developers in a pairing have different skill sets. If one programmer is more experienced in a certain skill, they can teach a student who is less familiar with that area. 
4. Social skills:
Pair programming help programmers develop their interpersonal skills.
5. Job interview readiness:
A common step in many interview processes involves pair programming between a current employee and an applicant, either in person or through a shared screen.
6. Work environment readiness:
Many companies that utilize pair programing expect to train fresh hires from CS-degree programs on how they operate to actually deliver a product. 
