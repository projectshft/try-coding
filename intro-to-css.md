# Intro to CSS

## What is CSS?
CSS stands for "cascading style sheets". It's essentially the "skin" on top of our HTML structure. It's the colors, the formatting, the fonts, etc of our web pages.

For this lesson, we'll primarily look at:
- How to select HTML elements with CSS and what specificity means
- The different CSS "positions"

## 1. CSS Selectors and Specificity

To learn CSS, we're going to continue with our #durmlife project, starting with CSS Selectors.

Within CSS, there are 5 main ways to select HTML elements to style them. As we examine these selectors, we're also going to talk about their **specificity**. Specificity is the means by which browsers decide which CSS property values are the most relevant to an element and therefore will be applied. Specificity is based on the matching rules which are composed of CSS selectors of different sorts.

### Element Selectors

One way to select an HTML element in CSS is by using the element's tag name. For instance, we can style a `div` element like so:

```css
div {
  width: 50%;
}
```

An h1 element like this:

```css
h1 {
  font-weight: bold;
}
```

Or even a ul element, along with any of its children li elements, in this way:

```css
ul {
  color: red;
}
```

Element selectors are very broad as utilizing them will affect many elements on your page. This type of selector is the least specific and easily overridden.

### Class Selectors

Perhaps the most common way to select elements is by using the `class` attribute. For instance, if we had a div with the class nav-bar like so:

```html
<div class="nav-bar"></div>
```

...we could style it in CSS this way (notice how we use a `.` before the class name):

```css
.nav-bar {
  position: fixed;
}
```

Class selectors are certainly more specific than element selectors, but can be applied widely to many elements.

_Reminder_ — you can add any class, or classes, to any HTML element, or elements — and you can name those classes any name that you would like. Also, it's best to use hyphen-separated names for classes rather than camel-cased names:

```html
<h1 class="heading car">Caution!</h1>

<h3 class="car">Never eat these things!</h3>

<ul class="cool-cars">
  <li>Tesla</li>
  <li>Lamborghini</li>
  <li>McLaren</li>
  <ul></ul>
</ul>
```

### Id Selectors

Much like classes:

```html
<div id="about-me">I'm really cool.</div>
```

...we could style it in CSS this way (notice how we use a `#` before the id name):

```css
#about-me {
  font-family: sans-serif;
}
```

Since id's must be unique, they are more specific than class selectors.

### Pseudo Selectors

To give an HTML element a special state, we can use pseudo-class selectors in our CSS. For instance, we might want to style an element when a user mouses over (or hovers over) it:

```css
button:hover {
  background-color: blue;
  color: black;
  border: 1px solid black;
}
```

Or we might use a pseudo-class to style a specific child element:

```css
p:nth-child(2) {
  background: red;
}
```

Check out [this example](https://codepen.io/amhayslip/pen/OMOzyg) of using pseudo selectors. For a complete list, check [mdn here](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Pseudo-classes_and_pseudo-elements).

---

### Attribute Selectors

Attribute selectors are handy when you want to select an element that has a particular attribute value:

```css
/* All elements with the attribute "data-car"
   are given green text */
[data-car] {
  color: green;
}

/* All elements with the attribute "data-car"
   with the exact value "tesla" are given a red
   background color */
[data-car='tesla'] {
  background-color: red;
}
```

### Inline Styles

This is where you use the HTML "style" attribute to add CSS. For example:

```html
<div style="background-color: pink;"></div>
```

Inline styles are is extremely specific and should usually be avoided, mostly because they're no fun to write.

### Using !important (most specific)

Using the keyword "!important" in your CSS overrides all styles regardless. This should be used very sparingly if at all. Here is an example:

```CSS
div {
  width: 200px;
  height: 200px;
  background-color: red !important;
  border: 5px solid magenta;
}
```

### Bottom of file

Lastly, when two conflicting style rules have the same specificity, the one that's defined lower down in your CSS file takes precedence. Take a look at [this example here](https://codepen.io/amhayslip/pen/ZWEqrp). Notice that the div is blue because that is the style that is defined further down in the file.

This rule also applies across multiple files. If you link several CSS files to your HTML page the links further down the page will be more important.

Take a look here to see [this example in action](https://codepen.io/amhayslip/pen/MyWBxX). Play around with it - for example, remove the `!important`, change the order, etc.

_Note_: Combining CSS selectors also affects the specificity of a property. For example, a property with both ID and attribute selectors has more specificity than a property with just an ID selector.

---

## 2. Exercise

Use the our "#DURMLIFE" project to complete the following exercises. Write the necessary CSS inside the `css` section in Codepen. Here is the HTML you should have so far:

```html
<!DOCTYPE html>
  <nav>
    <ul>
      <li><a href="#food">Food</a></li>
      <li><a href="#drinks">Drinks</a></li>
      <li><a href="#jobs">Jobs</a></li>
      <li><a href="#apartments">Apartments</a></li>
    </ul>
  </nav>

  <section class="hero">
    <h1 class="hero-title">#DURMLIFE</h1>
  </section>
```

### Exercise 1

Give the `body` a background color of `#ddd` and a margin of 0 (this will help us reset some of the browsers default margin styles that we don't want).

```CSS
body {
  background-color: #ddd
}
```

Note: In codepen, the "`body`" is implied but hidden. It technically wraps all of our HTML above.

### Exercise 2

Give the `nav` element a background color of #087d8e.

```CSS
nav {
  background-color: #087d8e;
}
```

### Exercise 3

Give the "hero-title" a font size of 50px.

```CSS
.hero-title {
  font-size: 50px;
}
```

### Exercise 4 (on your own!)

Use a pseudo selector to make the menu items change color on hover.

---

## 3. Nav Styling

Before we move on, let's style the nav a bit. Add the following to your css:

```CSS
nav li {
  display: inline-block;
}

nav {
  background-color: #087d8e;
}

nav li a {
  line-height: 50px;
  text-decoration: none;
  color: #fff;
  font-size: 11px;
  text-transform: uppercase;
  font-weight: bold;
  padding: 0 18px;
}
```

This CSS is fairly self-explanatory, but if you don't understand any of it then "give it a Google" before calling an instructor over to help.

---

## 4. Positioning

The `position` attribute is one of the more difficult ones to understand in CSS. We'll utilize it to keep our menu fixed to the top of our viewport as we scroll down. But before we do that, let's look at the different "positions" in CSS.

### Absolute and Relative

Absolute positioning is a bit tricky to understand at first. In short, absolute positioned elements are positioned absolute in relation to their closest relatively positioned ancestor.
Click [here for an example](https://codepen.io/amhayslip/pen/ONJaJJ).

In the example, the small Green Box has `absolute` position and the large red box has `relative` position. The Red Box is an ancestor of the Green Box (in this case it's the grandparent) and it is also the closest ancestor with "relative" positioning. Therefore, the Green Box (the `absolute` positioned element) obeys the Red Box (its closest `relative` positioned ancestor) to determine its position. Finally, the Green Box's right: 0; property, places it 0 pixels away from the right side of the Red Box.

Now, remove the `position: relative` property from the `.large-box` and add it to the `.medium-box`. What happened?

What do you think happens when there is no ancestor element with `relative` positioning?

### Fixed

A "fixed" element works just like an absolutely positioned one, except its "relative parent" is the viewport. In other words, a fixed element stays fixed in its position no matter how much the page is scrolled.

Check out [this example](https://codepen.io/amhayslip/pen/aNbQOG) to see it in action. Notice how the red bar stays in its place as your scroll.

Okay, at last, let's position our nav so that is fixed to the top by changing the nav's CSS:

```CSS
nav {
  background-color: #087d8e;
  position: fixed;
  width: 100%;
  top: 0;
}
```

Also, let's center it and remove the unwanted margin:

```css
nav ul {
  margin: 0;
  text-align: center;
}
```

## 5. Hero Section

Let's get our project looking like the "finished" picture.

### Title

First, let's get our main title centered up. Change the css for your `hero-title` to look like this:

```CSS
.hero-title {
  padding-top: 300px;
  color: #fff;
  font-size: 50px;
  text-align: center;
}
```

### Background Image

For our large image, we'll use the `background-image` property. Add the following CSS to your page:

```CSS
.hero {
  background: url(https://www.projectshift.io/wp-content/uploads/2017/12/TIS4202Panorama_hdr_tonemapped2013IceFactoryATC-Scott_Faber_Photography.jpg) no-repeat center fixed;
  background-size: cover;
  height: 700px;
}
```

A background-image can have `background-repeat`, `background-attachment` and `background-position` properties. We defined all of those, but with shorthand. In other words, we didn't want our image to repeat, we want it centered and fixed. In addition, we used `background-size: cover` to be sure that the entire image is displayed.
