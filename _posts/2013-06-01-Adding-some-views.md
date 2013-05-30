---
  title: Adding first controllers, views and some AngularJs
  categories: [ project, m1pm ]
  tags: [ m1, angularjs ]
---
It is now time to add some views to the application. My plan is to structure my application so that each 
main section of the application (eg Projects, Dashboard, etc) will have its own controller and a main view. 
I will then use AngularJs to navigate within the page (eg Projects/Add, Projects/Edit/, etc) using partial views to load the appropriate page content.

The current, basic, Dashboard/Index page I've created looks like this:


The "ng-app" attribute tell AngularJs of the scope and will also load the "m1pm-dashboard" module in the modules.js file that I've created. 
The dashboard module will then handle the routing, load the patial view into the div marked with "ng-view", etc.



Finally the partial view just prints the "param" value onto the page.

See source code at [my Github page](http://github.com/andreasmcdermott).


