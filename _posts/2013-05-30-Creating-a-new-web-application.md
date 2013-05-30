---
  layout: post
  title: Creating a new web application
  categories: [ Project, M1PM ]
  tags: [ setup, angularjs, ravendb ]
---
It's time to slowly get started with my new project! I've decided to create a .Net MVC 4 web application that uses the Web Api to
talk to the server and AngularJs to handle the UI. RavenDB will be used as the database.

##New project
The first thing I did was create a new MVC 4 project and choose the Web Api template.
Visual Studio adds a lot of stuff I don't want, so I remove all of that through the NuGet manager (like Entity Framework, knockoutjs, etc).
I also remove the created controllers, views, the css, images, and anything else I don't want.
The resulting structure looks like this:
![Initial structure](http://andreasmcdermott.com/images/m1pm-initial-structure.JPG)

##RavenDB
First thing I do once the project is cleaned up is add RavenDB from NuGet. 
I choose the RavenDB Client version. When hosting on a shared hosting environment I normally choose Embedded, but since I will host this (as a demo)
on AppHarbor with the database on CloudBird I choose the Client version instead. I will get back to the code to setup RavenDB in a future post.

##AngularJs
I decide to add AngularJs using Google's CDN instead of NuGet.

##Initial layout file
 My layout file now looks like this:
{% highlight html linenos %}
  <!DOCTYPE html>
  <html>
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <title>M1 Project Manager | @ViewBag.Title</title>
    <link type="text/css" rel="stylesheet" href="@Url.Content("~/Content/Site.css")" />
    <script src="//ajax.googleapis.com/ajax/libs/angularjs/1.0.6/angular.min.js"></script>
  </head>
  <body>
    @RenderBody()
    @RenderSection("scripts", required: false)
  </body>
  </html>
{% endhighlight %}

##Result: A project to build upon
I now have a project I can continue to build upon. Next step will be to add some basic controllers and views as well as add a bit of AngularJs code.

See the latest source code at [my Github page](http://github.com/andreasmcdermott/m1-project-manager).
