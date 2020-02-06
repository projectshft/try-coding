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

## Elements
How they take up space in the browser
Things float up and right
there are inline and block level elements

## Nodes, Tags and Elements

## The Most Common HTML Tags






[FOR INTRO TO CSS]
- Utilize class, id, inline and pseudo CSS selectors.
- Explain CSS specificity.
- Describe the different CSS "positions".
