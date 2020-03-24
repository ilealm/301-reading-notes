# Read 12 EJS Partials

* Partials come in handy when you want to _reuse the same HTML across multiple views_.

### Example of how to create partials:

1. Under the views/partials/ directory 
2. Create a file callednavbar.ejs which will contain only the HTML for the navigation bar at the top of the home and post pages:

`<!-- views/partials/navbar.ejs -->`
`    <div class="header clearfix">`
`        <nav>`
`            <ul class="nav nav-pills pull-right">`
`                <li role="presentation"><a href="/">Home</a></li>`
`            </ul>`
`            <h3 class="text-muted">Node.js Blog</h3>`
`        </nav>`
`    </div>`

3. And File called footer.ejs in that same directory:
`<!-- views/partials/footer.ejs -->`
`    <footer class="footer">`
`        <p>© 90210 Lawyer Stuff.</p>`
`    </footer>`

4. With partials defined, we can use them in our home.ejs and post.ejs. Example: 


`<!-- views/home.ejs -->`

`    <!DOCTYPE html>`

`    <html>`

`    <head>`

`        <meta charset="utf-8">`

`        <title>Node.js Blog</title>`

`       <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css">`

`        <style>`

`           body {`

`                padding-top: 20px;`

`                padding-bottom: 20px;`

`            }`

`            .jumbotron {`

`              margin-top: 10px;`

`            }`

`        </style>`

`    </head>`

`    <body>`

`        <div class="container">`

`            <%- include('partials/navbar') %>`

`            <div class="jumbotron">`

`                <h1>All about Node</h1>`

`                <p class="lead">Check out our articles below!</p>`

`            </div>`

`            <div class="row">`

`                <div class="col-lg-12">`

`                    <div class="list-group">`

`                      <!-- loop over blog posts and render them -->`

`                      LIST_OF_POSTS`

`                    </div>`

`                </div>`

`            </div>`

`            <%- include('partials/footer') %>`

`        </div>`

`    </body>`

`    </html>`



`<!-- views/post.ejs -->`

`   <!DOCTYPE html>`

`    <html>`

`    <head>`

`        <meta charset="utf-8">`

`        <title>POST_TITLE | Node.js Blog</title>`

`        <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css">`

`        <style>`

`            body {`

`                padding-top: 20px;`

`                padding-bottom: 20px;`

`            }`

`        </style>`

`    </head>`

`    <body>`

`        <div class="container">`

`            <%- include('partials/navbar') %>`

`            <div>`

 `               <h2>POST_TITLE</h2>`

`                <p>by <a href="#">POST_AUTHOR</a></p>`

`                <p>POST_CONTENT</p>`

`                <hr>`

 `           </div>`

 `           <%- include('partials/footer') %>`

 `       </div>`

`    </body>`

`    </html>`