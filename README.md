## Website Performance Optimization portfolio project
## How to Run
- Download this file at https://github.com/TiCl4/Website-Optimization-P4-
- Unzip the file
- Run index.html on your web browser for part 1
- Run pizza.html in views folder on your web browser for part 2

--- *** Optimization Steps *** ---
#### Part 1: Optimize PageSpeed Insights score for index.html
- Added async in <script async src="http://www.google-analytics.com/analytics.js"></script>
- Added media="print" in <link href="css/print.css" rel="stylesheet" media="print">
- Resized pizzeria on http://resizeimage.net/
- Optimized all image files in img and images
- Load google fonts via <script defer async src="https://fonts.googleapis.com/css?family=Open+Sans:400,700"></script>, added defer and async to remove render blocking.
- Minified index.html with (https://github.com/jonschlinkert/gulp-htmlmin)
- Minified style.css with gulp-clean-css although it does not change the score
- Moved style.css content to index.html and commentted out <link href="css/style.css" rel="stylesheet">
- Minified index.html with http://kangax.github.io/html-minifier/

- Changed querySelector to getElementById on lines 409, 412, 415, 427
- Set randomPizzaContainer =  document.getElementsByClassName('randomPizzaContainer') and pull it out of the loop
- Stored length of class randomPizzaContainer in a variable to save time instead of looping over class group on line 452
- var pizzasDiv = document.getElementById("randomPizzas") is pulled out of the loop to avoid looping over on line 472
- Changed to querySelectorAll to getElementsByClassName on line 505
- var scrollTop = document.documentElement.scrollTop || document.body.scrollTop is pulled out of the loop since it causes running over for nothing
- Declare var phase and len=items.length to avoid looping over on line 508
- Changed to getElementById instead of querySelector on line 542

#### Part 2: Optimize Frames per Second in pizza.html
- Moved style.css content to pizza.html in a style tag
- Moved bootstrap-grid.css content to pizza.html in different style tag
- Minified pizza.html with http://kangax.github.io/html-minifier/
