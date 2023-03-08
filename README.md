# Intro to Flexbox & CSS Grid

![Layout](https://i.imgur.com/qsSi07H.png)
## Lesson Overview


In the past decade, we have entered what is known as the "Mobile first paradigm" of styling. Front End developers have to create sites that look good on many different sized devices, with smaller, Mobile screens taking up a massive share of our screen time.  Having a font size of 36px and a margin of 50px might look great on your Macbook screen in development, but how is it going to look on your Apple Watch when the page is deployed? To meet this need, we as programmers needed a way to create *responsive* styling, which would auto-change and position itself based on the size of the screen. 


Enter Flex and Grid, two modern CSS frameworks that will allow us to use logic and math to style and position our websites, so that they look good on a small phone, a massive HD monitor, and everywhere in between. 


In this lesson, we'll learn how to use Flexbox and Grid to align elements in our web pages.  They both have different use cases and each are very valuable to any front end developer. You may not be able to master them in the course of one night. But as you continue to build up and work with projects over the coming weeks, you will see the usage and the power of these two incredible peices of code.



## Objectives
  - Describe the Use Case of Flexbox & CSS Grid
  - Use Flexbox for One-Dimensional Layout
  - Use CSS Grid for Two-Dimensional Layout

## Getting Started
  - `Fork` and `Clone` this repository
  - `cd` into the repository
  - Use the command `code .` to open in VS Code

## Lesson Instructions

### Setup

Lets continue working with our previous HTML and CSS files. For this lesson, we'll be working specifically with our buttons in the Container div

### Intro to Flexbox & CSS Grid

The capabilities of Flexbox & CSS Grid complement each other. You can use both side-by-side, and even nest them within one another.

To best understand Flexbox & CSS Grid, it's important to remember what CSS stands for - **Cascading Style Sheets**. Understanding how the different sections of your web page relate to each other is critical to understanding how the CSS you write will affect it.

CSS operates on a parent/child structure with the outermost sections of a page affecting the innermost (like Russian Dolls).

![Dolls](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fmedia1.tenor.com%2Fimages%2Ff704a0c2b662a51397d6a6a8058d88a3%2Ftenor.gif%3Fitemid%3D7433508&f=1&nofb=1)

The difference between Flexbox and CSS Grid is how they are designed to lay out their *children*:

![Compare](https://i.imgur.com/2ie45ct.png)

## Flexbox

### Why Use Flexbox?

Flexbox excels at assisting devs with the following tasks:
  - Vertically centering content & elements within a container element
  - Spacing child elements within a container uniformly
  - Making the height of child elements laid out in columns the same even though they have a different amount of content.

### Flexbox Fundamentals

We use the CSS `display: flex;` declaration to make an element a **flex container**, for example:

  ```css
  section {
    display: flex;
  }
  ```

  The above would make all `<section>` elements **flex containers** and all direct children would become **flex items**.

Let's open a new tab in our browser and briefly review what has become the [de facto guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/).

### Your First Flexbox


**Which element needs to be our flex container?**

Next, let's make the `<div class="container">` a Flexbox:

  ```css
  .container {
    display: flex;
  }
  ```


Remember, we use the . to target a class!


Refresh, and we can make the following observations:
  - The **flex items** are laid out horizontally in a **row** - this is the default layout of a **flex container**.
  - The `<button>` elements have become **flex items** and no longer behave as block elements - their width has collapsed to that of their content and they are willing to sit side-by-side other elements.


### Your First Flexbox Continued...

A **flex container** has a `flex-direction` property that defines the direction of its **main axis**.

There are four values:
  - `row` - the default
  - `row-reverse`
  - `column`
  - `column-reverse`

Let's check them out by adding a `flex-direction` to the `<nav>`.

In addition to the concept of a **main axis**, a **flex container** has a **cross axis** which represents the opposite direction of its **main axis**.

For example, if the `flex-direction` is set to `row` (the default), the:
  - **main axis** is **horizontal**
  - **cross axis** is **vertical**

If the `flex-direction` is set to `column`, they flip:
  - **main axis** is **vertical**
  - **cross axis** is **horizontal**

The concepts of **main axis** & **cross axis** come into play when it comes to sizing and layout properties, such as:
  - `justify-content`: Controls alignment for the **main axis**
  - `align-items`: Controls alignment for the **cross axis**

With the following alignment properties set:

  ```css
  .container {
    display: flex;
    flex-direction: row; /* default */
    justify-content: flex-start; /* default */

  }
  ```

This bar's not looking too bad...

Lets see what happens if we change some things around. Lets make the direction be a Column, and then into a row-reverse. When might we use this on the web?


justify-content is a very powerful tool, lets change flex-start to flex-end and see how it looks. 

Thats great, but we want to take Flex into the 2020's and really show off its skill with responsive coding

Lets right click on our HTML page and inspect the file. From there we can change its resolution and see how Flex will auto resize based off the screens dimensions


Three Justify-content values with amazing power are "space-evenly", "space-between", and "space-between". Lets plug them in one at a time, see how they differ, and what they do when the screen is resized.


Flex has a massive amount of power in it, and is something you will be required to use in all of your projects through this class. As with so much, we don't expect you to have a mastery of it right now, but as we continuue moving forward in the material, you will see why it is such a powerful tool. 


### Review Questions - Flexbox

**1. When an element has a CSS property of `display: flex;`, that element becomes a flex _______________.**

**2. When an element has a CSS property of `display: flex;`, its direct children become flex _______________.**

**3. What value is the default for the `flex-direction` property?**

**4. Is it `justify-content` or `align-items` that controls the alignment along the _cross axis_?**

## CSS Grid

### Why use CSS Grid?

**CSS Grid** is a great option when you have:
  1.  A page layout like this (or as complex as you'd like):

![Grid](https://i.imgur.com/tkBPUd0.png)

  2.  Any other "components" that would benefit from a grid-type layout such as a "profile card". In other words, CSS Grid doesn't have to apply to the whole page - it can be useful for laying out smaller "components" as well.

### CSS Grid Fundamentals

Unlike Flexbox, **CSS Grid** lays out its **grid items** in **two-dimensions**.

**CSS Grids** have the concept of the following:
  - **Tracks**
  - **Cells**
  - **Areas**
  - **Gaps**

Let's examine a diagram to visualize these components...

![Grid Example](https://i.imgur.com/yNTGxhx.png)

### CSS Grid Fundamentals

As you might expect, there are plenty of CSS Grid-related properties and values.

Here's the [CSS Grid equivalent of that Flexbox guide we used earlier](https://css-tricks.com/snippets/css/complete-guide-grid/).

Let's open it up in a new tab and take a peek.

### Your First CSS Grid

To try out CSS Grid, we'll continue to work in VSCode to layout this UI:

![Grid](https://i.imgur.com/gUpQxPC.png)

The following CSS turns the `<body>` element into a **grid container**:

  ```css
  body {
    display: grid;
    height: 100vh;
    margin: 0;
    font-family: Helvetica;
  }
  ```

Using `height: 100vh;` will make the `<body>` fill the height of the browser window so that the `<footer>` is at the bottom.

Let's add the additional HTML required by the UI:

  ```html
  <body>
    <nav>
      <section>
        <div>HOME</div>
        <div>ABOUT</div>
        <div>WIDGETS</div>
      </section>
      <div>LOG OUT</div>
    </nav>
    <aside>SIDE BAR</aside>
    <main>MAIN CONTENT</main>
    <footer>FOOTER</footer>
</body>
  ```

Now for a touch of styling...

Let's change the color of the elements we just added so that we can more easily see them:

  ```css
  aside {
    background-color: #fae00c;
  }

  main {
    background-color: #226afa;
  }

  footer {
    background-color: #63d629;
  }
  ```
One more stylistic touch. What if we want to center the text in those elements both horizontally and vertically?

Wanting to center/center content is so common, let's create a class that will make any element with that class a Flexbox:

  ```css
  .flex-ctr {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  ```

With the class defined - **go ahead and add it to the `<aside>`, `<main>` & `<footer>` elements.**

Using Chrome DevTools to explore the page's elements, we can make the following observations:
  - A **CSS Grid** has a single column by default.
  - Each **grid item** (direct child) was placed its own row by default.

Now let's define the columns and rows necessary to layout our page as desired. Go back and look at the UI we want to layout and answer these questions:
  - **How many columns will we need to define?**
  - **How many rows?**

Okay, let's define those column and rows:

  ```css
  body {
    display: grid;
    grid-template-columns: 1fr 4fr;
    grid-template-rows: 50px 1fr 30px;
    ...
  ```

The `fr` unit is used by CSS Grid to represent a _fraction_ of the available space. So in our layout, the first column will be 1/5th the width of the window.

Refreshing the page shows that we've made a mess. But notice how each **grid item** is simply being placed in each cell across the columns from left to right. This is the default behavior.

However, we need both the `<nav>` and the `<footer>` to span two columns each...

There are a couple of ways to make **grid items** cover rectangular grid **areas**.

One way is by defining `grid-template-areas` on the grid container; then using the `grid-area` property on the **grid item**.

**However, in this lesson, we'll look at another option...**

The `grid-column` CSS property determines which **grid lines** a **grid item** starts and ends on.

For example:

  ```css
  nav,
  footer {
    grid-column: 1 / 3;
  }
  ```

The lines are numbered starting with 1 (not zero).

We will use `span x` to specify how many columns we want to span. Add this to your CSS:

  ```css
  nav,
  footer {
    grid-column: span 2;
  }
  ```

Unsurprisingly, there's a `grid-row` property as well.

Both `grid-column` & `grid-row` are shorthand for `grid-column-start` & `grid-column-end`, and `grid-row-start` & `grid-row-end`, respectively.

The last thing we'll look at in regards to CSS Grid are grid **gaps** which specify the size of the **grid lines**.

Update the CSS of the `<body>` (grid container) to the following:

  ```css
  body {
    display: grid;
    grid-template-columns: 1fr 4fr;
    grid-template-rows: 50px 1fr 30px;
    grid-gap: 5px;  /* specifies width of grid lines */
    ...
  ```

Note that the grid gaps cannot be styled - it is literally ***anti-style***.

## Lesson Recap
We learned all about how to use Flexbox and CSS Grid when trying to lay out our web pages.  These are extremely useful tools for any Front End Developer and allow us to really achieve dynamic and engaging layouts!

## Resources
  - [MDN - Flexbox](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox)
  - [MDN - Grid Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)
  - [CSS Tricks - Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
  - [CSS Tricks - Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)
  - [Flexbox Froggy](https://flexboxfroggy.com/)
  - [Grid Garden](https://cssgridgarden.com/)

### FUN GAMES TO LEARN FLEXBOX 
   - [Flexbox Zombies](https://mastery.games/flexboxzombies/)
   - [Flexbox Defense](http://www.flexboxdefense.com/)
   
