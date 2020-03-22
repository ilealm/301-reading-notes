# EJS
* Embedded JavaScript templating, which templating language that lets you generate HTML markup with plain JavaScript.
* JavaScript code in simple, straightforward scriptlet tags. 
* EJS caches the intermediate JS functions for fast execution.
* Errors are plain JavaScript exceptions, with template line-numbers included.

### To install EJS with NPM
`$ npm install ejs`


### Example to use
`let ejs = require('ejs'),`
`    people = ['geddy', 'neil', 'alex'],`
`    html = ejs.render('<%= people.join(", "); %>', {people: people});`

`<script src="ejs.js"></script>`
`<script>`
`  let people = ['geddy', 'neil', 'alex'],`
`      html = ejs.render('<%= people.join(", "); %>', {people: people});`
`</script>`

### Example of Usage
`let template = ejs.compile(str, options);`
`template(data);`
`// => Rendered HTML string`

`ejs.render(str, data, options);`
`// => Rendered HTML string`

`ejs.renderFile(filename, data, options, function(err, str){`
`    // str => Rendered HTML string`
`});`

### Some examples of Options
* `cache` Compiled functions are cached, requires filename
* `filename` Used by cache to key caches, and for includes
* `context` Function execution context
* `compileDebug` When false no debug instrumentation is compiled
* `client` Returns standalone compiled function
* `delimiter` Character to use with angle brackets for open/close


### Some examples of Tags
* `<% 'Scriptlet`' tag, for control-flow, no output
* `<%_ ‘Whitespace Slurping’` Scriptlet tag, strips all whitespace before it
* `<%= Outputs` the value into the template (HTML escaped)
* `<%- Outputs` the unescaped value into the template

### Includes
* Includes are relative to the template with the include call. (This requires the 'filename' option.) 

For example if you have "./views/users.ejs" and "./views/user/show.ejs" you would use `<%- include('user/show'); %>.`

### Caching
EJS ships with a basic in-process cache for caching the intermediate JavaScript functions used to render templates. It's easy to plug in LRU caching using Node's `lru-cache` library:

`let ejs = require('ejs'),`
`    LRU = require('lru-cache');`
`ejs.cache = LRU(100); // LRU cache with 100-item limit`

### Custom file loader
* The default file loader is fs.readFileSync.

`let ejs = require('ejs');`
`let myFileLoader = function (filePath) {`
`  return 'myFileLoader: ' + fs.readFileSync(filePath);`
`};`

`ejs.fileLoader = myFileLoad;`


### Layouts
* EJS does not specifically support blocks, but layouts can be implemented by including headers and footers, like so:

`<%- include('header'); -%>`
`<h1>`
`  Title`
`</h1>`
`<p>`
`  My page`
`</p>`
`<%- include('footer'); -%>`

