---
  title: Adding Disqus comments to a Jekyll blog
---
Because Jekyll only serves static html-pages I have to use a commenting system that stores all the data for me.
I only knew of [Disqus][1], so made some research to see what else was out there. 
I found a good article comparing the top three Google results when searching for "comments system":

* [Disqus][1]
* [LiveFyre][2]
* [IntenseDebate][3]

They all seem to be good, but I decided on using Disqus.

How to get Disqus working with Jekyll?
--------------------------------------
It is very easy actually! I've outlined the steps I took below.

###Step 1: Sign up for an account
Start with heading to Disqus' [website][1] and sign up for an account (assuming you don't already have one). 
Just follow their sign up process and you will be ready for step 2 in a few minutes.

###Step 2: Get the code
After setting up your site you are ready to add some code to your page.

Disqus has install instructions for many popular blog tools (like Wordpress, Tumblr, etc), but for Jekyll you should choose "Universal Code".
![Universal Code]({{ site.url }}/assets/disqus_universal.jpg)

First, get the code that adds the comments to your page:

{% highlight javascript %}

  <div id="disqus_thread"></div>
  <script type="text/javascript">
      /* * * CONFIGURATION VARIABLES: EDIT BEFORE PASTING INTO YOUR WEBPAGE * * */
      var disqus_shortname = 'YOUR_SHORTNAME'; // required: replace example with your forum shortname

      /* * * DON'T EDIT BELOW THIS LINE * * */
      (function() {
          var dsq = document.createElement('script'); dsq.type = 'text/javascript'; dsq.async = true;
          dsq.src = '//' + disqus_shortname + '.disqus.com/embed.js';
          (document.getElementsByTagName('head')[0] || document.getElementsByTagName('body')[0]).appendChild(dsq);
      })();
  </script>
  <noscript>Please enable JavaScript to view the <a href="http://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>
  <a href="http://disqus.com" class="dsq-brlink">comments powered by <span class="logo-disqus">Disqus</span></a>
    
{% endhighlight %}

Copy that snippet to your post-layout-file where comments should appear. Don't forget to replace "YOUR_SHORTNAME" with your actual shortname.

If you publish the changes your comments should already be working! But lets add some more features.

###Step 3: Add option to turn off comments for a post
Disqus allow you to specify that comments should be turned off for a post after a certain number of days. 
But it could also be nice to have the option to turn off comments completley for a post.

Put the following code around the Disqus code in step 2:

{% highlight liquid %}
  
  {% if page.allow_comments != false %}
    // Discus comment code goes here
  {% endif %}
  
{% endhiglight %}

And then in your post you can add "allow_comments: false" in the front-matter when you want to disable comments for a specific post.

###Step 4: Get comment count for your post
The final step is to add a comment count for each post. Disqus will give you that code as well.

{% highlight javascript %}

  <script type="text/javascript">
  /* * * CONFIGURATION VARIABLES: EDIT BEFORE PASTING INTO YOUR WEBPAGE * * */
  var disqus_shortname = 'YOUR_SHORTNAME'; // required: replace example with your forum shortname

  /* * * DON'T EDIT BELOW THIS LINE * * */
  (function () {
      var s = document.createElement('script'); s.async = true;
      s.type = 'text/javascript';
      s.src = '//' + disqus_shortname + '.disqus.com/count.js';
      (document.getElementsByTagName('HEAD')[0] || document.getElementsByTagName('BODY')[0]).appendChild(s);
  }());
  </script>

{% endhighlight %}

Add that code to the bottom of your page that will be displaying comment counts. Then, for each post you'll add a link like this: 

{% highlight html %}

  <a href="{{ post.url }}#disqus_thread"></a>
  
{% endhighlight %}

Disqus will add the comment count for all links with the "#disqus_thread" automatically.

### Done!
And that is it. If you want to see a specific example, feel free to have a look at how I did it for my page. 
The code is available at [GitHub](http://github.com/andreasmcdermott/andreasmcdermott.github.io "The repository for my page").

[1]: http://disqus.com/ "Disqus website"
[2]: http://www.livefyre.com/ "LiveFyre website"
[3]: http://intensedebate.com/ "IntenseDebate website"
