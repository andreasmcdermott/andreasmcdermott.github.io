---
  layout: post
  title: Getting started with NancyFx
  categories: [ Web ]
  tags: [ nancyfx, appharbor ]
---
I've been reading a bit about NancyFx the last few days. It seems like a lot of fun to use, so I thought I should try to get something working.
Getting something started with NancyFx might be the easiest thing I've ever done (considering I didn't use a Visual Studio project template even).
It took me at most 15 minutes to publish a Hello World-application to [AppHarbor](http://www.appharbor.com).

### First step

I started with an existing Asp.Net MVC application I had lying around. My first steps was to remove everything except the web.config (I'll be using the Asp.Net host and will need it),
the Content and Scripts folders, and the Microsoft.CSharp, System and System.Core dll's.

### Second step

I then got Nancy and Nancy.Hosting.AspNet from NuGet. Added a module that inherited from NancyModule and returned "Hello World!" on a get request to the root path.
And that is it. ~10 lines of code. Not bad.

{% highlight csharp linenos %}
  using Nancy;

  namespace M1.App
  {
    public class TestModule : NancyModule
    {
      public TestModule()
      {
        Get["/"] = ctx => "Hello World!";
      }
    }
  }
{% endhighlight %}

### Publishing to AppHarbor.

Finally I pushed everything to GitHub. Connected the repository to my AppHarbor application and that's it (AppHarbor pulls it and builds it). 
It is now up and running. 

### What now?

From what I've done and read so far, Nancy seems like a fun alternative to Microsoft's MVC. I'll for sure continue using it to see what it has to offer.
