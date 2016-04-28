# CSS Page Layout Code Along

## Overview

Building upon previous code alongs, in this exercise you will add column structure to your page layouts by coding along with the video provided. This will help you to review the concepts you were introduced to in the previous lessons.

## Instructions

1. Fork this repository.
2. Use Terminal to clone your forked copy.
3. Then change directory into the repository folder.
4. Code along with the provided video below and/or its supplementary reading located below the video. Code everything you see there. Feel free to stop, pause, rewind or fast forward through the content to keep pace.

<iframe width="100%" height="720" src="//www.youtube.com/embed/zZpAqtEXse0?rel=0&amp;controls=1&amp;showinfo=1" frameborder="0" allowfullscreen></iframe>

### Building Layouts

Lets start out by making a new feature branch in Terminal by typing `git checkout -b columns` and press return.

Next, open the index.html page in your code editor. Scroll down to the section with the id of "promotional" and let's create a new section beneath it with an id of "news".

```html
<section id="promotional">...</section>

<section id="news"></section>
```

Inside of this news section insert an `<h3>` and a paragraph with some placefiller text.

```html
<section id="news">
  <h3>Company News</h3>
  <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatum, inventore, vero, rerum ullam nihil sapiente tempora molestias quis ducimus opsum laborum vel. Tempore perspiciatis ea error dignissimos libero recesandae explicabo.</p>
</section>
```

What we are aiming to do here is that we will size the promotional section to take up two-thirds of the page and the news section will take up one-third. THese two sections will display side by side as columns. Below in the details section we have three divs and each of these will also become a column that spans one-third.

Let's head up to the top of this file and add some more elements. In the `<header>` at the top of the index page let's wrap the `<div id="logo">` and `<nav>` inside another `<div class="wrapper">`.

```html
<header>
  <div class="wrapper">
    <div id="logo">
      <h1>Exceptional</h1>
      <h2>Realty Group</h2>
    </div>
    <nav>
      <a href="index.html">About</a> <a href="new-properties.html">New Properties</a> <a href="real-estate-listings.html">Listings</a> <a href="market-report.html">Market Report</a> <a href="contact.html">Contact</a> <a href="http://hud.gov" target="_blank">H.U.D.</a>
    </nav>
  </div><!-- .wrapper -->
</header>
```

The "wrapper" class is going to help us to center content in a common parent element. let's add afew more wrappers. Open a wrapper div just below the closing `</header>` element. And we will close the wrapper div just before the starting `<section id="details">`.

```html
</header>

<div class="wrapper">
  <section id="featured-property">...</section>
  
  ...
  
  <section id="news">...</section>
</div><!-- .wrapper -->

<section id="details">...</section>
```

Lastly, we will add a wrapper div within the details section.

```html
<section id="details">
  <div class="wrapper">
     
     ...
     
  </div><!-- .wrapper -->
</section>
```

Don't forget to properly indent all the elements that are nested within our new wrappers. Then save the index file and open the style.css file in your code editor.

We will start by adding a comment at the bottom of our CSS file.

```css
/*////////// LAYOUT //////////*/
```

Then below create a slector for our wrapper class.

```css
/*////////// LAYOUT //////////*/

.wrapper {
  width: 960px;
  margin: 0 auto;
  background: #eee;
}
```

Here we gave it a fixed width and centered it by giving it auto margin on the left and right. I also gave it a light gray background color just for the sake of seeing the wrapper. We will end up removing this later on and put some nicer looking background styling in. Save the page and head back to the browser and refresh. You should see the wrapper centering our content.

Next lets create some classes for some columns.

```css
/*////////// LAYOUT //////////*/

.wrapper {
  width: 960px;
  margin: 0 auto;
  background: #eee;
}

.col-1 {
  /* this column will span one-third */
}

.col-2 {
  /* this column will span two-thirds */
}

.col-3 {
  /* this column will span all the entire wrapper */
}
```

...

```css
.col-1 {
  float: left;
  width: 32%;
  background: #ccc;
}

.col-2 {
  float: left;
  width: 66%;
  background: #ccc;
}

.col-3 {
 background: #ccc;
}
```

...

```css
.col-1 {
  float: left;
  width: 32%;
  background: #ccc;
}

.col-2 {
  float: left;
  width: 66%;
  background: #ccc;
}

.col-3 {
 background: #ccc;
}

[class*="col-"] {
  margin-left: 2%;
}

.first {
  margin-left: 0;
}
```

...


It's now time to version our changes using Git. To do so, in Terminal type `git add .` and press return. Then type `git commit -m "add columns and fixed header and social bar"` and press return. Then push up this feature branch `git push -u origin columns` and press return. Next merge the changes into your master branch. Type `git checkout master` and press return, then `git merge columns` and press return. Then `git push origin master` and press return.

After you finish, make sure you install Firefox if you haven't already as it is required for the screenshot tests to run. Then, type `learn` command from Terminal to run local tests (Mac) or type `learn-test` for Windows.

After all tests are passing submit a pull request on Github and move on to the next lesson!

<p data-visibility='hidden'>View <a href='https://learn.co/lessons/fe-code-along-4' title='Code Along Exercise 4'>Code Along Exercise 4</a> on Learn.co and start learning to code for free.</p>
