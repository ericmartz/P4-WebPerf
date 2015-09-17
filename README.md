<<<<<<< HEAD
## Website Performance Optimization portfolio project

Your challenge, if you wish to accept it (and we sure hope you will), is to optimize this online portfolio for speed! In particular, optimize the critical rendering path and make this page render as quickly as possible by applying the techniques you've picked up in the [Critical Rendering Path course](https://www.udacity.com/course/ud884).

To get started, check out the repository, inspect the code,

### Getting started

####Part 1: Optimize PageSpeed Insights score for index.html

Some useful tips to help you get started:

1. Check out the repository
1. To inspect the site on your phone, you can run a local server

  ```bash
  $> cd /path/to/your-project-folder
  $> python -m SimpleHTTPServer 8080
  ```

1. Open a browser and visit localhost:8080
1. Download and install [ngrok](https://ngrok.com/) to make your local server accessible remotely.

  ``` bash
  $> cd /path/to/your-project-folder
  $> ngrok 8080
  ```

1. Copy the public URL ngrok gives you and try running it through PageSpeed Insights! Optional: [More on integrating ngrok, Grunt and PageSpeed.](http://www.jamescryer.com/2014/06/12/grunt-pagespeed-and-ngrok-locally-testing/)

Profile, optimize, measure... and then lather, rinse, and repeat. Good luck!

####Part 2: Optimize Frames per Second in pizza.html

To optimize views/pizza.html, you will need to modify views/js/main.js until your frames per second rate is 60 fps or higher. You will find instructive comments in main.js. 

You might find the FPS Counter/HUD Display useful in Chrome developer tools described here: [Chrome Dev Tools tips-and-tricks](https://developer.chrome.com/devtools/docs/tips-and-tricks).

### Optimization Tips and Tricks
* [Optimizing Performance](https://developers.google.com/web/fundamentals/performance/ "web performance")
* [Analyzing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/analyzing-crp.html "analyzing crp")
* [Optimizing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/optimizing-critical-rendering-path.html "optimize the crp!")
* [Avoiding Rendering Blocking CSS](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-blocking-css.html "render blocking css")
* [Optimizing JavaScript](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/adding-interactivity-with-javascript.html "javascript")
* [Measuring with Navigation Timing](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/measure-crp.html "nav timing api"). We didn't cover the Navigation Timing API in the first two lessons but it's an incredibly useful tool for automated page profiling. I highly recommend reading.
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/eliminate-downloads.html">The fewer the downloads, the better</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer.html">Reduce the size of text</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization.html">Optimize images</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/http-caching.html">HTTP caching</a>

### Customization with Bootstrap
The portfolio was built on Twitter's <a href="http://getbootstrap.com/">Bootstrap</a> framework. All custom styles are in `dist/css/portfolio.css` in the portfolio repo.

* <a href="http://getbootstrap.com/css/">Bootstrap's CSS Classes</a>
* <a href="http://getbootstrap.com/components/">Bootstrap's Components</a>

### Sample Portfolios

Feeling uninspired by the portfolio? Here's a list of cool portfolios I found after a few minutes of Googling.

* <a href="http://www.reddit.com/r/webdev/comments/280qkr/would_anybody_like_to_post_their_portfolio_site/">A great discussion about portfolios on reddit</a>
* <a href="http://ianlunn.co.uk/">http://ianlunn.co.uk/</a>
* <a href="http://www.adhamdannaway.com/portfolio">http://www.adhamdannaway.com/portfolio</a>
* <a href="http://www.timboelaars.nl/">http://www.timboelaars.nl/</a>
* <a href="http://futoryan.prosite.com/">http://futoryan.prosite.com/</a>
* <a href="http://playonpixels.prosite.com/21591/projects">http://playonpixels.prosite.com/21591/projects</a>
* <a href="http://colintrenter.prosite.com/">http://colintrenter.prosite.com/</a>
* <a href="http://calebmorris.prosite.com/">http://calebmorris.prosite.com/</a>
* <a href="http://www.cullywright.com/">http://www.cullywright.com/</a>
* <a href="http://yourjustlucky.com/">http://yourjustlucky.com/</a>
* <a href="http://nicoledominguez.com/portfolio/">http://nicoledominguez.com/portfolio/</a>
* <a href="http://www.roxannecook.com/">http://www.roxannecook.com/</a>
* <a href="http://www.84colors.com/portfolio.html">http://www.84colors.com/portfolio.html</a>
=======
# P4-WebPerf
Udacity's Project 4 - Web Performance
>>>>>>> cf761305a009fe752c9429b594cfacb87ac73c3d

PROJECT 4 PART 1:
Optimization: (index.html)
First measured to optimize:  I used Google Page Speed insights.  Showed a mobile score of 28/100 with the following recommendations:
  - Optimize images.
  - Eliminate Render Blocking JS and CSS in above-the-fold content
  - Leverage Browser Caching

First looked at picture sizes.
  - The first one Build Your Own 2048 is 100x50 pixels, not too large.
  - The 2nd, Web Perf Optimization is 100x62 pixels, not too large.
  - The 3rd, Mobile Web Development is 100x61 pixels, not too large.
  - The 4th, Cam's Pizzeria is 2048x1536, which is too large.  Used Grunt Responsive Imagesto make the file smaller and provide for multiple image sizes (for
    pizza.html).

After optimizing images, Google PageSpeed showed a mobile score of 75/100, and the desktop score was 88/100.
  - Eliminate Render Blocking JS and CSS in above-the-fold content
  - Leverage Browser Caching

Now I added the async attribute to try to eliminate the Render Blocking JS.

Then for css:
  - For the print.css file, added the media attribute "print"
  - For Google Fonts, it looks like it is one of the first requests sent, and the last one in my timeline to come back in.  Takes 85ms to retrieve the file.
    - Used Google Web Font Loader to make the request asynchronous.
  - Used Grunt Cssmin to minify the CSS in print.css and style.css.  The minified style.css was then inlined in index.html.

After the above steps were taken I measured on Google's PageSpeed Insights again. Mobile score shows 92/100 and Desktop is 93/100. Still a couple steps it recommends:

Leverage Browser Caching
Optimize images. It thinks I can squeeze even more juice out of two of the pics on the website.
So noticed on Google PageSpeed Insights that there was an option to download optimized resources.
Found an article here: http://www.thesempost.com/google-pagespeed-insights-optimize-site-images-css-javascript/ from March 2015 which describes Google's efforts with these optimized resources.
So I figured why not just use what Google is handing me when it comes to the newer images. They comressed them, losslessly, and even made the images just a bit smaller in dimensions. Adding those to index.html and running PageSpeed Insights brought my score to 95/100. Not a huge jump, but I figured why not get the score as high as possible. Still, for JS and CSS I want to try to get that as small as possible using Grunt tasks.
So final score seems to be 95/100 for PageSpeed Insights. There is a recommendation to Leverage Browser Caching, and I thought there was a way to put in something in headers of HTML to make that work, but I didn't find any examples or info on that. One page I did see said it could be done, but most browsers ignored it. Everything else talked about adding info to your web server to help leverage browser caching. Since I am using GitHub as my web server for these projects, I am skipping leveraging browser caching.



