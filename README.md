## Website Performance Optimization portfolio project

This project is an optimized portfolio, that was previously poorly implemented, its pagespeed ranking was below 60, some scripts took more than 1s to load.

In the section below, you can check out everything I've done to optimize it.

### What have I done to optimize this website.

#### 1. Compression and general CRP opt
- Compressed all of the images, and resized pizzeria, because its resolution was over 2k.
- Set all of the scripts of index.html (and 2048, web-perf, project-mob) to load after the page was loaded and rendered, using the async tag.
- Set print.css to load only when the page is requested by a printer, using media="print".
- Removed external request for fonts.
- Compressed css and html (removed white trailing space).
- Improved PageSpeed ranking from 45-50 to 85-92

#### 2. Style.css
- Copied all of the content from style.css, put into an ```<script>``` tag, inside html. (Personally, I don't think that's a good solution because it makes it harder to maintain a webpage when you load all of its style this way. But it was necessary, and as this webpage is static, it's probably not going to be a problem.)
- (fixed a minor bug, where the wrong fonts were loaded instead of Open Sans).
- Improved PageSpeed ranking to 91~97.
- (NEW) Added a few proprieties into the pizza style.css to improve browser rendering

#### 3. Pizza (JS opt)
- Removed tons of redundancy and unnecessary loops or wrong calls (which were supposed to use requestAnimationFrame function for example).
- Improved scrolling from 4-10FPS to 59-60FPS.
- (NEW) Merged dx function with changePizzaSizes and improved performance a lot by eliminating more unnecessary loops, resizing now takes only 0.6ms average.
- (NEW) Reduced the number of pizzas created (because some pizzas were created off the screen), now scrolling takes only 0.8ms average.

#### 4. How to keep improving
- Add cache support to the website (currently not possible because I'm using github pages, and I don't have the necessary privileges to do it).

### Getting started (These are instructions from Udacity)

#### Part 1: Optimize PageSpeed Insights score for index.html

Some useful tips to help you get started:

1. Check out the repository
1. To inspect the site on your phone, you can run a local server

  ```bash
  $> cd /path/to/your-project-folder
  $> python -m SimpleHTTPServer 8080
  ```

1. Open a browser and visit localhost:8080
1. Download and install [ngrok](https://ngrok.com/) to the top-level of your project directory to make your local server accessible remotely.

  ``` bash
  $> cd /path/to/your-project-folder
  $> ./ngrok http 8080
  ```

1. Copy the public URL ngrok gives you and try running it through PageSpeed Insights! Optional: [More on integrating ngrok, Grunt and PageSpeed.](http://www.jamescryer.com/2014/06/12/grunt-pagespeed-and-ngrok-locally-testing/)

Profile, optimize, measure... and then lather, rinse, and repeat. Good luck!

#### Part 2: Optimize Frames per Second in pizza.html

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
