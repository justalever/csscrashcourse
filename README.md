# CSS Crash Course

by Andy Leverenz of [web-crunch.com](https://web-crunch.com)

Find the source code linked here:



### Table of Contents

1. [What's in this course](#Whats-in-this-course)
2. [What is CSS?](#What-is-CSS?)
3. [Why you might learn CSS](#Why-you-might-learn-CSS)
4. [Tools used to author CSS](#Tools-used-to-author-CSS)
5. [The building blocks of a CSS file](#The-building-blocks-of-a-CSS-file)
6. [CSS syntax](#CSS-syntax)
7. [How does CSS actually work?](#How-does-CSS-actually-work?)
8. [Understanding how CSS is applied](#Understanding-how-CSS-is-applied)
9. [What is a selector?](#What-is-a-selector?)
10. [What is the CSS box model?](#What-is-the-CSS-box-model?)
11. [Understanding block and inline box display](#Understanding-block-and-inline-box-display)
12. [Cascade](#Cascade)
13. [Specificity](#Specificity)
14. [Inheritance](#Inheritance)
15. [Values and units](#Values-and-units)
16. [Color](#Color)
17. [Browser inconsistencies](#Browser-inconsistencies)
18. [Next steps](#Next-steps)

# What's in this course

The CSS Crash Course is a continuation of my [HTML Crash Course](https://web-crunch.com/posts/html-crash-course) that aims at giving you a summarized view of what CSS is, how it's used, and why it's important to learn as a developer or designer.

This course is for **absolute beginners**. You don't need to know a thing about CSS to learn something new. I recommend familiarizing yourself with HTML prior to taking this course so you can understand how CSS depends on HTML directly.

The current core version of CSS is known as CSS3 which is what we'll be leveraging in this course. I'll expose you to both foundational features and more advanced features you can use as you become more comforatble with the language.

### What we will be building

We'll be creating a resume website using HTML taken from my [HTML Crash Course](https://web-crunch.com/posts/html-crash-course). The HTML Crash course gives us the foundation HTML markup that we can leverage to make a more professional looking resume website with CSS.

The first section of this course will be primarily lecture-driven which will help you understand the foundational concepts of the language before diving in to actually coding something.

The final section is actually putting CSS to work. Use the video screenscast during this section as your guide to build alongside me.

### Learning takes time

The old saying goes, "Rome wasn't built in a day". This also applies to anything you want to learn. In order to get better at writing CSS you need to practice using it over and over again. Use real-world projects and fun side projects as a means to further your knowledge. Learning by doing is how developers/designers hone in on their craft.

## Check out my more comprehensive HTML + CSS course

Learn HTML & CSS from the ground up by building real-world projects with me as your guide. Learn more at [hellohtmlcss.com](https://hellohtmlcss.com)

![Hello HTML & CSS](https://f001.backblazeb2.com/file/webcrunch/hellohtmlcss-promo.jpg)


# What is CSS?

CSS – (Cascading Style Sheets) is a rule-based language at its core. You define some rules usually in groups that get applied to specific HTML elements on a web page. These elements are targeted as the web page renders.

Aside from general styling like color, size, and shape, CSS has more advanced capabilties that allow you to animate, define dynamic properties known as CSS variables, and manipulate many elements at once.

CSS is not a programming language. You can't do conditional rendering with it but you can perform some math-based calculations for values and units.

CSS is used on virtually every website in existance. You don't need CSS but it helps increase the user experience ten-fold. Making a website easy to read and easy to use should be a primary goal.

# Why you might learn CSS

- Do more at your job and become a more valuable employee
- Allow you to earn side income by building websites or applications that in return generate money somehow.
- Really understand no-code tools and how they are coding things behind the scenes so you don't have to.
- Build your own website, business, or brand online.
- Have a foundational understanding of the language before moving on to something more advanced.


# Tools used to author CSS

CSS comes for free in your browser of choice. Coding CSS typically takes place in a code editor with syntax highlighting. What you use doesn't really matter so long as it enables you to code however you prefer.

Common browers:

- [Google Chrome](https://www.google.com/chrome/)
- [Apple Safari](https://www.apple.com/safari/)
- [Firefox](https://www.mozilla.org/en-US/firefox/new/) - My personal favorite
- [Microsoft Edge](https://www.microsoft.com/en-us/edge)


Popular Code Editors:

- [Visual Studio Code](https://code.visualstudio.com/)
- [Sublime Text 3](https://www.sublimetext.com/)
- [Atom](https://atom.io/)
- Virutally anything with syntax highlighting

# The building blocks of a CSS file

All CSS files have a `.css` extension. You might see some with `.scss` or `.sass`. These are more advanced versions of CSS that are used outside of the scope of the course.

Just know that `.scss` and `.sass` files need to be compiled. Ultimately they get output as `.css` files. `.css` files can run in the browser without any compilation.

A CSS file can contain various selectors that target HTML elements directly. What order you author your code matters thanks to the cascade effect of CSS.

Styles can cascade (inherit from other styles) based on their authored hierarchy and specificity.


# CSS Syntax

**Syntax** – The style the code is written. Every code language shares similar glyphs for its own version of syntax though each tend to have unique characteristics that seperate each from one another.

- A CSS **selector** can be a HTML class, HTML ID, HTML attribute, or the name of the HTML element itself. Selectors prepend curly braces which is where the rules are applied to style the element(s) in mention. Here are some examples:

```css
/* HTML classes are targeted with a period prepending the class name */
.class {
  color: red;
}

/* IDs are targeted using the # sign */
#id {
  font-size: 16px;
}

/* You can combine named HTML elements with attributes for more advanced targeting */
input[type="text"] {
  background-color: white;
  border: 1px solid #dddddd;
}

/* Target all <p> tags by naming them explicitly */
p {
  margin-top: 10px;
  margin-bottom: 10px;
}
```

Every property and value requires a semi-colon at the end of each line `;`. This signifies the end of the declaration.

There is no limit to the amount of properties and values you can apply to a given selector.

# 7. How does CSS actually work?

![How CSS actually works](https://f001.backblazeb2.com/file/webcrunch/how-css-works.png)

_source: [MDN](https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps/How_CSS_works)_


**DOM** - Document Object Model
The DOM creates HTML document nodes of which we can style with CSS.

1. The browser loads the HTML (e.g. receives it from the network).
2. It converts the HTML into a DOM (Document Object Model). The DOM represents the document in the computer's memory.
3. The browser then fetches most of the resources that are linked to by the HTML document, such as embedded images and videos ... and linked CSS!
4. The browser parses the fetched CSS, and sorts the different rules by their selector types into different "buckets", e.g. element, class, ID, and so on. Based on the selectors it finds, it works out which rules should be applied to which nodes in the DOM, and attaches style to them as required (this intermediate step is called a render tree).

5. The render tree is laid out in the structure it should appear in after the rules have been applied to it.

6. The visual display of the page is shown on the screen (this stage is called painting).

# Understanding how CSS is applied

The browser will parse the HTML and create a DOM from it, then parse the CSS. Since the only rule available in the CSS has a span selector, the browser will be able to sort the CSS quickly. That will apply that rule to each one of the three `<span>`s, then paint the final visual representation to the screen.

![How CSS gets applied](https://f001.backblazeb2.com/file/webcrunch/how-css-gets-applied.png)

# What is a selector?

A selector is part of a CSS rule that targets what HTML element it will be applying styles to. A selector can target on element or many elements at the same time.

**Type, class, and ID selectors**

```css
h1 { }, .box { }, #header { }
```

**Attribute selectors**

```css
input[type=“text”] { }, a[href=“https://google.com”] { }
```

**Pseudo-classes and pseudo-elements**

```css
a:hover { }, p::first-line { }
```
**Combinators**

```css
ul > li
```

# What is the CSS box model?

![CSS box model](https://f001.backblazeb2.com/file/webcrunch/css-box-model.png)

**Content box:** The area where your content is displayed, which can be sized using properties like width and height.

**Padding box:** The padding sits around the content as white space; its size can be controlled using padding and related properties.

**Border box (most popular):** The border box wraps the content and any padding. Its size and style can be controlled using border and related properties.

**Margin box:** The margin is the outermost layer, wrapping the content, padding and border as whitespace between this box and other elements. Its size can be controlled using margin and related properties.

**Standard box:** All padding and margin are added to the content boxes existing width and height


# Understanding block and inline box display

 **Inline**
 - Only take their own width. Width and height properties ignored.
 - Don’t break to a new line
 - Stack horizontally if duplicated
 - Examples (`<span></span>`, `<em></em>`)

 **Block**
 - Take up entire width of line. Width and height properties respected.
 - Breaks to a new line every time
 - Stacks vertically if duplicated
 - Examples (`<div></div>`, `<h1></h1>`, `<p></p>`)

# Cascade

The order of rules matter. The last rule being applied takes precedence when using the same selector.

```css
h1 {
  color: red;
}

h1 {
  color: blue;
}
```

```html
<h1>This heading will be blue not red</h1>
```

# Specificity

```css
.main-heading {
  color: red;
}

h1 {
  color: blue;
}
```

```html
<h1 class="main-heading">This heading is red not blue</h1>
```

# Inheritance

Some CSS property values set on parent elements are inherited by their child elements, and some aren’t.

The width property won’t inherit to a parent’s children for example making each child have a width of an equal amount.


```css
body {
  color: blue;
}

span {
  color: black;
}
```

```html
<body>
  <p>The body text will default to the blue color until it encounters the <span>span tag which will be black</span> due to the DOM inheritance pattern.</p>

  <p>The span element is techincally a sibing of the body element in HTML</p>
</body>
```


# Values and units

**Absolute length units** – generally considered to always be the same size

```
cm, mm, in, pc, pt, px
```

**Relative length units** – relative to something else, perhaps the size of the parent element's font, or the size of the browser viewport

```
em, rem, vh, vw, lh, ex
```

**Percentages**  – always set relative to some other value. (i.e. Parent’s width)

```
50%, 100%, 22.5%
```

# Color
Lots of options with HEX and RGB being the most common.

**Keywords**

```css
black, white, aliceblue, azure, beige
```

**Hexidecimal RGB**

```css
#000000, #ffffff, #02798b
```

**RGB/RGBA (Red, Green, Blue / Red, Green, Blue, Alpha)**

```css
rgb(0, 0, 0), rgba(255, 255, 255, 0.5)
```

**HSL/HSLA (Hue, Saturation, Lightness/ Hue, Saturation, Lightness, Alpha)**

```css
hsl(174, 77%, 31%), hsla(174, 77%, 31%, 0.5)
```

# Browser inconsistencies

- Some browsers handle styles differently than others. (i.e. color, fonts, general support for new CSS features)

- If a browser is parsing your CSS rules, and encounters a property or value that it doesn't recognize, it ignores it and moves on to the next declaration.

- The previous point is actually a feature. This allows you to incorporate new CSS features before they are widely supported so long as you incorporate fallbacks.

# Next steps

The last portion of this course is to actually put CSS to work and start writing it. We'll be styling a multiple page resume website with a vast array of HTML elements to consider. I'll guide you on your journey as well as share some best practices for writing more readable code that many developers call the _standard_. Along the way I'll share some of my own opinions on naming conventions, organization, and more advanced CSS.

### CSS frameworks

When we complete the resume site I'll go over some popular CSS frameworks that exist today to make the process of authoring websites a little more consistent and faster to build. The are pros and cons to any approach so we'll go over those briefly.


### Check out my course (shamless plug!)

Learn HTML & CSS from the ground up by building real-world projects with me as your guide. Learn more at [hellohtmlcss.com](https://hellohtmlcss.com)

![Hello HTML & CSS](https://f001.backblazeb2.com/file/webcrunch/hellohtmlcss-promo.jpg)
