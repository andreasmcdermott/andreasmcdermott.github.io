---
  layout: post
  title: Adding views with AngularJs
  categories: [ Project, M1PM ]
  tags: [ angularjs ]
---
It is now time to add some views to the application. My plan is to structure my application so that each 
main section of the application (eg Projects, Dashboard, etc) will have its own controller and a regular view. 
I will then use AngularJs to navigate within the page (eg Projects/Add, Projects/Edit/, etc) using partial views to load the appropriate page content.

The current, basic, Dashboard/Index page I've created looks like this:
{% highlight html linenos %}
  @{
    ViewBag.Title = "Dashboard";
  }

  <div ng-app="m1pm-dashboard">
    <h2>Dashboard</h2>
    <div ng-view></div>
  </div>

  @section scripts {
    <script src="@Url.Content("~/Scripts/DashboardCtrl.js")"></script>
  }
{% endhighlight %}

It is very simple of course, and its only purpose is to make sure that I have AngularJs hooked up correctly.
The "ng-app" attribute tell AngularJs of the scope and will also load the "m1pm-dashboard" module in the modules.js file that I've created. 
The m1pm-dashboard module will then handle the routing. For the default route ("/") it will load the partial view from the controller into the div marked with "ng-view".
It will also load the specified ng-controller.

{% highlight javascript linenos %}
  // From modules.js
  var dashboardModule = angular.module('m1pm-dashboard', []).
  config(['$routeProvider', function ($routeProvider) {
    $routeProvider.
      when('/', { templateUrl: '/Dashboard/Overview', controller: 'OverviewCtrl' }).
      otherwise({ redirectTo: '/' });
  }]);

  // From DashboardCtrl.js
  dashboardModule.controller('OverviewCtrl', function ($scope) {
    $scope.param = "Hello World!";
  });
{% endhighlight %}

Finally the partial view just prints the "param" value onto the page to show its working.

See the latest source code at [my Github page](http://github.com/andreasmcdermott/m1-project-manager).