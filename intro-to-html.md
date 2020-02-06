# Intro to HTML

## Lesson Overview

By the end of this lesson a student should be able to...

- Define what HTML is and what it's purpose is
- Talk about the difference between HTML "nodes", "tags", and "elements".
- Distinguish between "block" and "inline" elements.
- Utilize from memory some of the most common HTML tags.

## Setup
For simplicity sake, we're going to be using [codepen.io](codepen.io). Navigate there now and click "Create", then "New Pen".

Notice that we have 3 different text windows and screen to show the results below:

![img](https://www.projectshift.io/wp-content/uploads/2018/09/Screen-Shot-2018-09-17-at-3.01.36-PM.png)

Inside these text windows we can write HTML, CSS and JavaScript and see the results (as we would in a browser), in the window at the bottom. Let's give it a shot.

Inside the HTML window write:

```html
<h1>Hello World!</h1>
```

And you should see:

![img](https://www.projectshift.io/wp-content/uploads/2018/09/Screen-Shot-2018-09-17-at-3.03.01-PM.png)

Great! We've just written some HTML. While we're here, let's write some CSS and JavaScript.


Now in the CSS window write:

```css
h1 {
  color: red;
}
```

And you should see:

![img](https://www.projectshift.io/wp-content/uploads/2018/09/Screen-Shot-2018-09-17-at-3.05.39-PM.png)

And finally in the JavaScript window write:

```js
alert('hello world')
```

And you should see:

![img](https://www.projectshift.io/wp-content/uploads/2018/09/Screen-Shot-2018-09-17-at-3.06.42-PM.png)

Cool! You can erase everything you have so far and we'll dive into some basics on HTML.

## What is HTML?
The dictionary says that HTML stands for, "Hypertext Markup Language, a standardized system for tagging text files to achieve font, color, graphic, and hyperlink effects on World Wide Web pages."

What?

Essentially, as we said, HTML is the bones and content of a webpage. Every HTML element has some default CSS properties. HTML elements are represented by boxes and the flow down a page from top to bottom, and left to right depending on specifics.

For example, the following HTML created the following image:

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <title>My Website</title>
  </head>

  <body>
    <h1>This is my website</h1>
    <p>This is some text about my website.</p>
    <p>Below is a list of links in my website:</p>
    <ul>
      <li><a href="about-me">About Me</a></li>
      <li><a href="contact-me">Contact Me</a></li>
      <li><a href="portfolio">Portflio</a></li>
    </ul>
  </body>

</html>
```

![img](https://www.projectshift.io/wp-content/uploads/2019/11/Screen-Shot-2019-11-04-at-3.24.14-PM.png)

With that code alone, we have the basics structures of a simple website. But let's dive a little deeper into learning what all of those characters above actually mean and do.

---

## 1. Defining HTML

HTML is made of "tags", which create "elements". The following example is a "paragraph" element made up of an "opening tag" and a "closing tag":

![p](https://www.projectshift.io/wp-content/uploads/2017/12/Screen-Shot-2016-02-25-at-1.18.12-PM.png)
![p1](https://www.projectshift.io/wp-content/uploads/2017/12/Screen-Shot-2016-02-25-at-1.18.29-PM.png)

When we put the tags together with some text in the middle, we get our element:

```html
<p>Hey I'm a paragraph!</p>
```

---

## 2. Structure

How we organize our HTML and its hierarchy depends on the format of our page. In essence, different HTML tags create HTML elements and these HTML elements have certain default CSS styles that represent how they look and behave. These HTML elements are represented by "boxes" (we'll review the CSS Box Model soon).

![box](https://www.projectshift.io/wp-content/uploads/2017/12/Screen-Shot-2016-02-25-at-1.29.36-PM.png)

This above image is represented by the code below:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title></title>
  </head>
  <body>
    <h1>This is the Main Heading</h1>
    <p>
      This text might be an introduction to the rest of the page. And if the
      page is a long one it might be split up into several sub-headings.
    </p>

    <h2>This is a Sub-Heading</h2>
    <p>
      Many long articles have sub-headings to help you follow the structure of
      what is being written. There may even be sub-sub-headings (or lower-level
      headings).
    </p>

    <h2>Another Sub-Heading</h2>
    <p>Here you can see another sub-heading.</p>
  </body>
</html>
```

We would say that there are two main default `display` properties of all HTML elements.

**_Block Level Element_**: In the example above, we have only block-level elements. A block-level element takes up the entire width of its parent.

**_Inline Element_**: Other elements are by default, "inline". From MDN, "An inline element does not start on a new line and only takes up as much width as necessary". An example of an inline element is the `<span></span>`. A `span` will only be as wide as the text inside of it. For example:

```html
<p>
  Hello, I want this text <span style="font-weight: bold;">to be bold</span>
</p>
```

Will look like this:

Hello, I want this text **to be bold**.

Notice that `to be bold` doesn't start on a new line.

---

## 3. HTML Attributes

Also from MDN, "Elements in HTML have attributes; these are additional values that configure the elements or adjust their behavior in various ways to meet the criteria the users want."

![attr](https://www.projectshift.io/wp-content/uploads/2017/12/Screen-Shot-2016-02-25-at-2.30.38-PM.png)

This should mostly be review, but let's look at some common attributes.

### `class` and `id`

Any HTML element can be given a `class` or `id` for the sake of helping us select the element in the future with CSS or JavaScript.

```html
<div class="container"></div>

<div id="top-section"></div>

<div class="container" id="bottom-section"></div>
```

The rules of HTML dictate that many elements on the page can have the same `class`. But `id`'s must be unique - in other words no two elements on the same page can have the same `id`.

### `src` and `href`

Some attributes are specific to certain elements. For example, an `img` element requires a `src` and an `a` element requires an `href`:

```html
<img
  src="https://www.bitcoin.com/wp-content/uploads/2017/06/usebitcoin-4096x2253.jpg"
/>
```

```html
<a href="http://www.google.com">Click here to Google!</a>
```

---

## 4. The Most Common HTML Tags

Today we'll start building a simple website using common HTML. It will be called "#DURMLIFE" and will be all about Durham.

![durm](https://www.projectshift.io/wp-content/uploads/2017/12/Screen-Shot-2017-12-12-at-8.26.33-AM.png)

### Setup

Make sure your codepen is blank.

The first thing we want to build is our top navigation. For that, we can use a `nav` element. A nav works like any other "div" (generic divider element), but it's used specifically for the page's navigation. Why we'd use this over a normal `div` is a question of semantics. Add a `nav` now:

```html
  <nav></nav>
```

Now inside of our `nav`, we'll add our menu. We'll use an unordered-list for this:

```html
<nav>
  <ul>
    <li><a href="#food">Food</a></li>
    <li><a href="#drinks">Drinks</a></li>
    <li><a href="#jobs">Jobs</a></li>
    <li><a href="#apartments">Apartments</a></li>
  </ul>
</nav>
```

Let's pause and make sure we understand what's going on so far.

### Sections

We'll add some style later. Let's move on. Below the "nav" we see a large area with our title and a cool background image. This is a significant "section" of our page, so we'll use a `section` tag. The section tag also works just like any ordinary "div", but is more specific in its use.

Add the following HTML below your `nav` as a sibling:

```html
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

## Review
Okay, let's review a few concepts before we move on to CSS:

- What is the purpose of HTML?
- What does HTML stand for?
- What is the difference between and HTML "tag", "element" and "attribute"?
