# CSS Documentation

Welcome to the CSS section of Web Development Made Easy!

## Table of Contents

### Part 1: Fundamentals
- [Introduction to CSS](#introduction-to-css)
- [Adding CSS to HTML](#adding-css-to-html)
  - [Inline Styles](#inline-styles)
  - [Internal Stylesheets](#internal-stylesheets)
  - [External Stylesheets](#external-stylesheets)
- [CSS Syntax and Rules](#css-syntax-and-rules)
- [CSS Selectors](#css-selectors)
  - [Element Selectors](#element-selectors)
  - [Class Selectors](#class-selectors)
  - [ID Selectors](#id-selectors)
  - [Attribute Selectors](#attribute-selectors)
  - [Pseudo-classes](#pseudo-classes)
  - [Pseudo-elements](#pseudo-elements)
- [CSS Colors](#css-colors)
  - [Color Names, Hex, RGB, HSL](#color-names-hex-rgb-hsl)
  - [Opacity and Transparency](#opacity-and-transparency)
- [Typography](#typography)
  - [Font Properties](#font-properties)
  - [Text Styling](#text-styling)
  - [Web Fonts](#web-fonts)
- [The Box Model](#the-box-model)
  - [Content, Padding, Border, Margin](#content-padding-border-margin)
  - [Box Sizing](#box-sizing)
- [Display and Positioning](#display-and-positioning)
  - [Display Property](#display-property)
  - [Position Property](#position-property)
  - [Float and Clear](#float-and-clear)
  - [Z-Index](#z-index)

### Part 2: Advanced Topics
- [Modern Layouts](#modern-layouts)
  - [Flexbox](#flexbox)
  - [CSS Grid](#css-grid)
- [Responsive Design](#responsive-design)
- [CSS Transitions](#css-transitions)
- [CSS Animations](#css-animations)
- [CSS Transforms](#css-transforms)
- [CSS Variables (Custom Properties)](#css-variables)
- [Advanced Selectors](#advanced-selectors)
- [CSS Preprocessors](#css-preprocessors)

### Part 3: Best Practices & Tips
- [CSS Architecture](#css-architecture)
- [Performance Optimization](#performance-optimization)
- [Cross-Browser Compatibility](#cross-browser-compatibility)
- [Accessibility in CSS](#accessibility-in-css)
- [Common Mistakes to Avoid](#common-mistakes-to-avoid)
- [Modern CSS Features](#modern-css-features)
- [Tools and Resources](#tools-and-resources)

---

## Part 1: Fundamentals

### Introduction to CSS

CSS (Cascading Style Sheets) is the language used to style and layout web pages. While HTML provides the structure and content, CSS controls how that content looks and is presented to users.

**What CSS Does:**
- Controls colors, fonts, and spacing
- Defines layouts and positioning
- Creates animations and transitions
- Makes websites responsive to different screen sizes
- Separates presentation from content

**The "Cascading" in CSS:**
The "cascade" refers to how styles are applied when multiple rules target the same element. Styles cascade down from:
1. Browser default styles
2. External stylesheets
3. Internal stylesheets
4. Inline styles (highest priority)

```css
/* This is a CSS comment */
p {
    color: blue;
    font-size: 16px;
}
```

### Adding CSS to HTML

There are three ways to add CSS to your HTML documents:

#### Inline Styles

Inline styles are applied directly to HTML elements using the `style` attribute. They have the highest specificity but are generally not recommended for maintainability.

```html
<p style="color: red; font-size: 18px;">This text is red and 18px.</p>

<div style="background-color: #f0f0f0; padding: 20px; border-radius: 8px;">
    Styled container
</div>
```

**When to use:**
- Quick testing or debugging
- Dynamic styles set by JavaScript
- Email templates (where external CSS isn't supported)

**Drawbacks:**
- Hard to maintain
- Can't reuse styles
- Mixes content with presentation
- Increases HTML file size

#### Internal Stylesheets

Internal (or embedded) stylesheets are placed inside a `<style>` tag in the HTML document's `<head>` section.

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 20px;
        }
        
        h1 {
            color: #333;
            border-bottom: 2px solid #007bff;
        }
        
        .highlight {
            background-color: yellow;
            padding: 5px;
        }
    </style>
</head>
<body>
    <h1>Welcome</h1>
    <p class="highlight">Important text here.</p>
</body>
</html>
```

**When to use:**
- Single-page websites
- Page-specific styles that won't be reused
- Quick prototyping

**Drawbacks:**
- Styles can't be shared across pages
- Increases HTML file size
- Browser can't cache the CSS separately

#### External Stylesheets

External stylesheets are separate `.css` files linked to HTML documents. This is the **recommended approach** for most projects.

**styles.css:**
```css
body {
    font-family: 'Segoe UI', Tahoma, sans-serif;
    line-height: 1.6;
    color: #333;
}

.container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 20px;
}

.btn {
    display: inline-block;
    padding: 10px 20px;
    background-color: #007bff;
    color: white;
    text-decoration: none;
    border-radius: 4px;
}
```

**index.html:**
```html
<!DOCTYPE html>
<html>
<head>
    <link rel="stylesheet" href="styles.css">
    <!-- You can link multiple stylesheets -->
    <link rel="stylesheet" href="components.css">
</head>
<body>
    <div class="container">
        <a href="#" class="btn">Click Me</a>
    </div>
</body>
</html>
```

**Benefits:**
- Styles are reusable across multiple pages
- Cleaner HTML files
- Browser can cache CSS files (faster loading)
- Easier to maintain and organize
- Team members can work on CSS separately

### CSS Syntax and Rules

A CSS rule consists of a **selector** and a **declaration block**:

```css
selector {
    property: value;
    property: value;
}
```

**Anatomy of a CSS Rule:**
```css
h1 {                        /* Selector */
    color: navy;            /* Declaration (property: value) */
    font-size: 24px;        /* Another declaration */
    margin-bottom: 10px;    /* Declarations end with semicolons */
}
```

**Multiple Selectors:**
```css
/* Apply same styles to multiple selectors */
h1, h2, h3 {
    font-family: Georgia, serif;
    color: #2c3e50;
}
```

**Specificity Hierarchy:**
When multiple rules apply to the same element, specificity determines which wins:

| Selector Type | Specificity | Example |
|--------------|-------------|---------|
| Inline styles | 1000 | `style="color: red"` |
| ID selectors | 100 | `#header` |
| Class/attribute/pseudo-class | 10 | `.btn`, `[type="text"]`, `:hover` |
| Element/pseudo-element | 1 | `div`, `::before` |
| Universal selector | 0 | `*` |

```css
/* Specificity: 1 (element) */
p { color: black; }

/* Specificity: 10 (class) - wins over element */
.intro { color: blue; }

/* Specificity: 100 (ID) - wins over class */
#main-text { color: red; }

/* Specificity: 11 (element + class) */
p.intro { color: green; }
```

**The `!important` Rule:**
```css
p {
    color: red !important; /* Overrides everything (avoid using) */
}
```

### CSS Selectors

Selectors are patterns used to select the elements you want to style.

#### Element Selectors

Target elements by their tag name:

```css
/* All paragraphs */
p {
    line-height: 1.6;
}

/* All headings level 1 */
h1 {
    font-size: 2.5rem;
}

/* All links */
a {
    color: #007bff;
    text-decoration: none;
}

/* All images */
img {
    max-width: 100%;
    height: auto;
}
```

#### Class Selectors

Target elements by their class attribute (prefix with `.`):

```css
/* Single class */
.btn {
    padding: 10px 20px;
    border-radius: 4px;
    cursor: pointer;
}

/* Elements can have multiple classes */
.btn-primary {
    background-color: #007bff;
    color: white;
}

.btn-large {
    padding: 15px 30px;
    font-size: 1.2rem;
}
```

```html
<button class="btn btn-primary btn-large">Submit</button>
```

#### ID Selectors

Target a unique element by its ID (prefix with `#`):

```css
#header {
    background-color: #333;
    padding: 20px;
}

#main-content {
    max-width: 800px;
    margin: 0 auto;
}

#footer {
    border-top: 1px solid #ddd;
    padding: 40px 0;
}
```

**Note:** IDs must be unique per page. Prefer classes for reusable styles.

#### Attribute Selectors

Target elements based on their attributes:

```css
/* Has attribute */
[disabled] {
    opacity: 0.5;
    cursor: not-allowed;
}

/* Attribute equals value */
[type="text"] {
    border: 1px solid #ccc;
    padding: 8px;
}

[type="submit"] {
    background-color: green;
    color: white;
}

/* Attribute contains value */
[class*="btn"] {
    cursor: pointer;
}

/* Attribute starts with value */
[href^="https"] {
    color: green;
}

/* Attribute ends with value */
[href$=".pdf"] {
    color: red;
}

/* Attribute contains word (space-separated) */
[class~="featured"] {
    border: 2px solid gold;
}
```

#### Pseudo-classes

Target elements in a specific state (prefix with `:`):

```css
/* Link states */
a:link { color: blue; }           /* Unvisited link */
a:visited { color: purple; }      /* Visited link */
a:hover { color: red; }           /* Mouse over */
a:active { color: orange; }       /* Being clicked */
a:focus { outline: 2px solid; }   /* Keyboard focused */

/* Form states */
input:focus {
    border-color: #007bff;
    box-shadow: 0 0 0 3px rgba(0,123,255,0.25);
}

input:disabled {
    background-color: #e9ecef;
}

input:required {
    border-left: 3px solid red;
}

input:valid {
    border-color: green;
}

input:invalid {
    border-color: red;
}

/* Child selectors */
li:first-child { font-weight: bold; }
li:last-child { margin-bottom: 0; }
li:nth-child(2) { color: blue; }          /* Second item */
li:nth-child(odd) { background: #f5f5f5; } /* Odd items */
li:nth-child(even) { background: white; }  /* Even items */
li:nth-child(3n) { color: red; }           /* Every 3rd item */

/* Other useful pseudo-classes */
p:empty { display: none; }                 /* Empty elements */
:not(.special) { opacity: 0.8; }           /* Negation */
div:only-child { margin: 0; }              /* Only child */
```

#### Pseudo-elements

Target specific parts of elements (prefix with `::`):

```css
/* First letter (drop caps) */
p::first-letter {
    font-size: 3rem;
    float: left;
    line-height: 1;
    margin-right: 10px;
}

/* First line */
p::first-line {
    font-weight: bold;
}

/* Selection highlight */
::selection {
    background-color: #007bff;
    color: white;
}

/* Before and after (add content) */
.required::after {
    content: " *";
    color: red;
}

.quote::before {
    content: """;
    font-size: 2rem;
}

.quote::after {
    content: """;
    font-size: 2rem;
}

/* External link indicator */
a[href^="http"]::after {
    content: " ↗";
    font-size: 0.8em;
}

/* Placeholder text */
input::placeholder {
    color: #999;
    font-style: italic;
}
```

### CSS Colors

#### Color Names, Hex, RGB, HSL

CSS supports multiple color formats:

```css
/* Named colors (140+ available) */
.named {
    color: red;
    background: lightblue;
    border-color: darkgreen;
}

/* Hexadecimal (#RRGGBB or #RGB) */
.hex {
    color: #ff0000;          /* Red */
    background: #007bff;     /* Blue */
    border-color: #333;      /* Short for #333333 */
}

/* RGB (Red, Green, Blue: 0-255) */
.rgb {
    color: rgb(255, 0, 0);           /* Red */
    background: rgb(0, 123, 255);    /* Blue */
}

/* RGBA (RGB with Alpha/opacity: 0-1) */
.rgba {
    background: rgba(0, 0, 0, 0.5);    /* 50% transparent black */
    color: rgba(255, 255, 255, 0.9);   /* 90% opaque white */
}

/* HSL (Hue: 0-360, Saturation: 0-100%, Lightness: 0-100%) */
.hsl {
    color: hsl(0, 100%, 50%);        /* Red */
    background: hsl(210, 100%, 50%); /* Blue */
}

/* HSLA (HSL with Alpha) */
.hsla {
    background: hsla(210, 100%, 50%, 0.5); /* 50% transparent blue */
}
```

**Color Format Comparison:**

| Format | Example | Best For |
|--------|---------|----------|
| Named | `red`, `blue` | Quick prototyping |
| Hex | `#ff5733` | Most common, compact |
| RGB | `rgb(255, 87, 51)` | When you need RGB values |
| RGBA | `rgba(255, 87, 51, 0.5)` | Transparency needed |
| HSL | `hsl(14, 100%, 60%)` | Easy color adjustments |
| HSLA | `hsla(14, 100%, 60%, 0.5)` | HSL with transparency |

**Pro Tip:** HSL is great for creating color variations:
```css
:root {
    --primary-hue: 210;
    --primary: hsl(var(--primary-hue), 100%, 50%);
    --primary-light: hsl(var(--primary-hue), 100%, 70%);
    --primary-dark: hsl(var(--primary-hue), 100%, 30%);
}
```

#### Opacity and Transparency

```css
/* opacity property (affects entire element including children) */
.faded {
    opacity: 0.5; /* 50% transparent */
}

.invisible {
    opacity: 0; /* Completely invisible but still in layout */
}

/* transparent keyword */
.transparent-bg {
    background-color: transparent;
}

/* RGBA for background only (children not affected) */
.overlay {
    background-color: rgba(0, 0, 0, 0.7);
    color: white; /* Text stays fully opaque */
}

/* Modern: color-mix() for transparency */
.modern {
    background: color-mix(in srgb, blue 50%, transparent);
}
```

### Typography

#### Font Properties

```css
.text {
    /* Font family (use fallback stack) */
    font-family: 'Helvetica Neue', Arial, sans-serif;
    
    /* Font size */
    font-size: 16px;      /* Pixels */
    font-size: 1rem;      /* Relative to root (recommended) */
    font-size: 1.2em;     /* Relative to parent */
    
    /* Font weight */
    font-weight: normal;  /* Same as 400 */
    font-weight: bold;    /* Same as 700 */
    font-weight: 300;     /* Light */
    font-weight: 600;     /* Semi-bold */
    
    /* Font style */
    font-style: normal;
    font-style: italic;
    font-style: oblique;
    
    /* Line height */
    line-height: 1.5;     /* Unitless (recommended) */
    line-height: 24px;    /* Fixed */
    line-height: 150%;    /* Percentage */
    
    /* Shorthand */
    font: italic 600 16px/1.5 'Georgia', serif;
    /*    style weight size/line-height family */
}

/* Font stacks by category */
.serif {
    font-family: Georgia, 'Times New Roman', Times, serif;
}

.sans-serif {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
}

.monospace {
    font-family: 'Fira Code', 'Courier New', Consolas, monospace;
}
```

#### Text Styling

```css
.styled-text {
    /* Text alignment */
    text-align: left;
    text-align: center;
    text-align: right;
    text-align: justify;
    
    /* Text decoration */
    text-decoration: none;           /* Remove underline */
    text-decoration: underline;
    text-decoration: line-through;   /* Strikethrough */
    text-decoration: underline wavy red; /* Fancy underline */
    
    /* Text transform */
    text-transform: uppercase;
    text-transform: lowercase;
    text-transform: capitalize;      /* First Letter Of Each Word */
    
    /* Letter and word spacing */
    letter-spacing: 2px;             /* Space between letters */
    word-spacing: 5px;               /* Space between words */
    
    /* Text indent */
    text-indent: 2em;                /* First line indent */
    
    /* White space handling */
    white-space: normal;             /* Default wrapping */
    white-space: nowrap;             /* No wrapping */
    white-space: pre;                /* Preserve whitespace */
    white-space: pre-wrap;           /* Preserve but wrap */
    
    /* Text overflow */
    overflow: hidden;
    text-overflow: ellipsis;         /* Show ... when truncated */
    white-space: nowrap;
    
    /* Text shadow */
    text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
    /*          x    y    blur  color */
    
    /* Multiple shadows */
    text-shadow: 
        1px 1px 0 #fff,
        2px 2px 0 #333;
}
```

#### Web Fonts

**Google Fonts (easiest):**
```html
<head>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
</head>
```

```css
body {
    font-family: 'Roboto', sans-serif;
}
```

**@font-face (self-hosted):**
```css
@font-face {
    font-family: 'MyCustomFont';
    src: url('fonts/myfont.woff2') format('woff2'),
         url('fonts/myfont.woff') format('woff');
    font-weight: normal;
    font-style: normal;
    font-display: swap; /* Show fallback while loading */
}

body {
    font-family: 'MyCustomFont', Arial, sans-serif;
}
```

**Variable Fonts (modern):**
```css
@font-face {
    font-family: 'InterVariable';
    src: url('Inter-Variable.woff2') format('woff2');
    font-weight: 100 900; /* Range of weights */
}

.light { font-weight: 300; }
.regular { font-weight: 400; }
.bold { font-weight: 700; }
.black { font-weight: 900; }
```

### The Box Model

Every HTML element is a rectangular box. The box model describes how these boxes are sized.

#### Content, Padding, Border, Margin

```
┌─────────────────────────────────────┐
│              MARGIN                 │
│   ┌─────────────────────────────┐   │
│   │          BORDER             │   │
│   │   ┌─────────────────────┐   │   │
│   │   │      PADDING        │   │   │
│   │   │   ┌─────────────┐   │   │   │
│   │   │   │   CONTENT   │   │   │   │
│   │   │   └─────────────┘   │   │   │
│   │   └─────────────────────┘   │   │
│   └─────────────────────────────┘   │
└─────────────────────────────────────┘
```

```css
.box {
    /* Content dimensions */
    width: 300px;
    height: 200px;
    
    /* Padding (inside the border) */
    padding: 20px;                    /* All sides */
    padding: 10px 20px;               /* Vertical | Horizontal */
    padding: 10px 20px 15px;          /* Top | Horizontal | Bottom */
    padding: 10px 20px 15px 25px;     /* Top | Right | Bottom | Left */
    
    /* Individual padding */
    padding-top: 10px;
    padding-right: 20px;
    padding-bottom: 15px;
    padding-left: 25px;
    
    /* Border */
    border: 1px solid #333;           /* Shorthand */
    border-width: 2px;
    border-style: solid;              /* solid, dashed, dotted, double, etc. */
    border-color: #333;
    
    /* Individual borders */
    border-top: 3px solid red;
    border-bottom: none;
    
    /* Border radius (rounded corners) */
    border-radius: 8px;               /* All corners */
    border-radius: 50%;               /* Circle */
    border-radius: 10px 0 10px 0;     /* Diagonal rounded */
    
    /* Margin (outside the border) */
    margin: 20px;                     /* All sides */
    margin: 0 auto;                   /* Center horizontally */
    margin-top: 30px;
    margin-bottom: 30px;
    
    /* Negative margins (pull elements) */
    margin-top: -10px;
}
```

#### Box Sizing

By default, `width` and `height` only set the content size. Padding and border are added on top.

```css
/* Default behavior (content-box) */
.default-box {
    width: 300px;
    padding: 20px;
    border: 5px solid black;
    /* Total width: 300 + 40 + 10 = 350px */
}

/* Better behavior (border-box) - RECOMMENDED */
.better-box {
    box-sizing: border-box;
    width: 300px;
    padding: 20px;
    border: 5px solid black;
    /* Total width: 300px (padding and border included) */
}

/* Apply border-box globally (best practice) */
*, *::before, *::after {
    box-sizing: border-box;
}
```

### Display and Positioning

#### Display Property

Controls how an element behaves in the document flow:

```css
/* Block - takes full width, starts new line */
.block {
    display: block;
}

/* Inline - flows with text, can't set width/height */
.inline {
    display: inline;
}

/* Inline-block - flows inline but can have width/height */
.inline-block {
    display: inline-block;
    width: 100px;
    height: 100px;
}

/* None - removes from document completely */
.hidden {
    display: none;
}

/* Flex - enables flexbox layout */
.flex-container {
    display: flex;
}

/* Grid - enables grid layout */
.grid-container {
    display: grid;
}

/* Table display values */
.table { display: table; }
.table-row { display: table-row; }
.table-cell { display: table-cell; }
```

#### Position Property

Controls how an element is positioned:

```css
/* Static - default, normal document flow */
.static {
    position: static;
}

/* Relative - positioned relative to its normal position */
.relative {
    position: relative;
    top: 10px;      /* Move down 10px from normal position */
    left: 20px;     /* Move right 20px from normal position */
}

/* Absolute - positioned relative to nearest positioned ancestor */
.absolute {
    position: absolute;
    top: 0;
    right: 0;
    /* Removes element from document flow */
}

/* Fixed - positioned relative to viewport */
.fixed {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    /* Stays in place when scrolling */
}

/* Sticky - hybrid of relative and fixed */
.sticky {
    position: sticky;
    top: 0;
    /* Sticks when scrolled to that position */
}
```

**Common Pattern - Absolute inside Relative:**
```css
.parent {
    position: relative;
}

.child {
    position: absolute;
    bottom: 10px;
    right: 10px;
}
```

#### Float and Clear

Floats were used for layouts before Flexbox/Grid. Now mainly used for wrapping text around images.

```css
/* Float an image */
.float-left {
    float: left;
    margin-right: 20px;
    margin-bottom: 10px;
}

.float-right {
    float: right;
    margin-left: 20px;
}

/* Clear floats */
.clear {
    clear: both;
}

/* Clearfix (container of floated elements) */
.clearfix::after {
    content: "";
    display: table;
    clear: both;
}
```

#### Z-Index

Controls stacking order of positioned elements:

```css
.back {
    position: relative;
    z-index: 1;
}

.middle {
    position: relative;
    z-index: 10;
}

.front {
    position: relative;
    z-index: 100;
}

/* Note: z-index only works on positioned elements */
/* (relative, absolute, fixed, sticky) */

/* Negative z-index puts elements behind */
.behind {
    position: relative;
    z-index: -1;
}
```

**Stacking Context:**
Certain properties create a new stacking context (like a z-index "reset"):
- `position` with `z-index`
- `opacity` less than 1
- `transform`, `filter`, `perspective`
- `isolation: isolate`

---

## Part 2: Advanced Topics

### Modern Layouts

#### Flexbox

Flexbox (Flexible Box Layout) is a one-dimensional layout system for arranging items in rows or columns.

**Flex Container Properties:**

```css
.flex-container {
    display: flex;
    
    /* Direction of items */
    flex-direction: row;            /* Default: left to right */
    flex-direction: row-reverse;    /* Right to left */
    flex-direction: column;         /* Top to bottom */
    flex-direction: column-reverse; /* Bottom to top */
    
    /* Wrapping */
    flex-wrap: nowrap;              /* Default: single line */
    flex-wrap: wrap;                /* Wrap to new lines */
    flex-wrap: wrap-reverse;        /* Wrap upward */
    
    /* Shorthand */
    flex-flow: row wrap;
    
    /* Main axis alignment */
    justify-content: flex-start;    /* Pack to start */
    justify-content: flex-end;      /* Pack to end */
    justify-content: center;        /* Center items */
    justify-content: space-between; /* Equal space between */
    justify-content: space-around;  /* Equal space around */
    justify-content: space-evenly;  /* Perfectly even spacing */
    
    /* Cross axis alignment */
    align-items: stretch;           /* Default: fill container height */
    align-items: flex-start;        /* Align to top */
    align-items: flex-end;          /* Align to bottom */
    align-items: center;            /* Center vertically */
    align-items: baseline;          /* Align text baselines */
    
    /* Multi-line alignment */
    align-content: flex-start;
    align-content: center;
    align-content: space-between;
    
    /* Gap between items */
    gap: 20px;                      /* Row and column gap */
    row-gap: 20px;
    column-gap: 10px;
}
```

**Flex Item Properties:**

```css
.flex-item {
    /* Order (default is 0) */
    order: 1;                       /* Move to end */
    order: -1;                      /* Move to start */
    
    /* Grow to fill available space */
    flex-grow: 0;                   /* Default: don't grow */
    flex-grow: 1;                   /* Grow equally */
    flex-grow: 2;                   /* Grow twice as much */
    
    /* Shrink when not enough space */
    flex-shrink: 1;                 /* Default: shrink equally */
    flex-shrink: 0;                 /* Don't shrink */
    
    /* Base size before growing/shrinking */
    flex-basis: auto;               /* Use content/width */
    flex-basis: 200px;              /* Fixed base size */
    flex-basis: 25%;                /* Percentage */
    
    /* Shorthand (grow shrink basis) */
    flex: 1;                        /* flex: 1 1 0% */
    flex: 0 0 200px;                /* Fixed 200px, no grow/shrink */
    flex: 1 1 auto;                 /* Grow and shrink from auto size */
    
    /* Override container's align-items */
    align-self: auto;
    align-self: flex-start;
    align-self: center;
    align-self: flex-end;
}
```

**Common Flexbox Patterns:**

```css
/* Center anything */
.center-everything {
    display: flex;
    justify-content: center;
    align-items: center;
}

/* Navigation bar */
.navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

/* Equal columns */
.equal-columns {
    display: flex;
    gap: 20px;
}
.equal-columns > * {
    flex: 1;
}

/* Sticky footer layout */
.page {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
}
.page main {
    flex: 1;
}

/* Card layout with bottom button */
.card {
    display: flex;
    flex-direction: column;
}
.card-content {
    flex: 1;
}
.card-button {
    margin-top: auto;
}
```

#### CSS Grid

CSS Grid is a two-dimensional layout system for creating complex layouts with rows and columns.

**Grid Container Properties:**

```css
.grid-container {
    display: grid;
    
    /* Define columns */
    grid-template-columns: 200px 200px 200px;     /* 3 fixed columns */
    grid-template-columns: 1fr 1fr 1fr;           /* 3 equal columns */
    grid-template-columns: 1fr 2fr 1fr;           /* Middle is twice as wide */
    grid-template-columns: repeat(3, 1fr);        /* Shorthand for 3 equal */
    grid-template-columns: repeat(4, 100px);      /* 4 x 100px columns */
    
    /* Responsive columns */
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    
    /* Define rows */
    grid-template-rows: 100px 200px;              /* Fixed rows */
    grid-template-rows: auto 1fr auto;            /* Header, main, footer */
    
    /* Implicit rows (auto-generated) */
    grid-auto-rows: 150px;
    grid-auto-rows: minmax(100px, auto);
    
    /* Gap between cells */
    gap: 20px;
    row-gap: 20px;
    column-gap: 10px;
    
    /* Alignment of all items */
    justify-items: start | end | center | stretch;
    align-items: start | end | center | stretch;
    
    /* Alignment of the grid itself */
    justify-content: start | end | center | space-between | space-around;
    align-content: start | end | center | space-between | space-around;
}
```

**Grid Item Properties:**

```css
.grid-item {
    /* Span columns */
    grid-column: 1 / 3;             /* Start at 1, end at 3 */
    grid-column: 1 / span 2;        /* Start at 1, span 2 columns */
    grid-column: span 2;            /* Span 2 from auto position */
    
    /* Span rows */
    grid-row: 1 / 3;
    grid-row: span 2;
    
    /* Shorthand */
    grid-area: 1 / 1 / 3 / 3;       /* row-start / col-start / row-end / col-end */
    
    /* Self alignment */
    justify-self: start | end | center | stretch;
    align-self: start | end | center | stretch;
}
```

**Grid Template Areas:**

```css
.layout {
    display: grid;
    grid-template-columns: 200px 1fr 200px;
    grid-template-rows: auto 1fr auto;
    grid-template-areas:
        "header header header"
        "sidebar main aside"
        "footer footer footer";
    min-height: 100vh;
}

.header { grid-area: header; }
.sidebar { grid-area: sidebar; }
.main { grid-area: main; }
.aside { grid-area: aside; }
.footer { grid-area: footer; }
```

**Responsive Grid Layouts:**

```css
/* Auto-responsive cards */
.card-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 20px;
}

/* Change layout at breakpoints */
.dashboard {
    display: grid;
    gap: 20px;
    grid-template-columns: 1fr;
}

@media (min-width: 768px) {
    .dashboard {
        grid-template-columns: 250px 1fr;
    }
}

@media (min-width: 1200px) {
    .dashboard {
        grid-template-columns: 250px 1fr 300px;
    }
}
```

### Responsive Design

#### Media Queries

Media queries apply styles based on device characteristics:

```css
/* Max-width (desktop-first) */
@media (max-width: 768px) {
    .container {
        padding: 10px;
    }
}

/* Min-width (mobile-first - recommended) */
@media (min-width: 768px) {
    .container {
        max-width: 750px;
    }
}

@media (min-width: 992px) {
    .container {
        max-width: 970px;
    }
}

@media (min-width: 1200px) {
    .container {
        max-width: 1170px;
    }
}

/* Combining conditions */
@media (min-width: 768px) and (max-width: 1023px) {
    /* Tablet only */
}

/* Orientation */
@media (orientation: landscape) {
    .hero {
        height: 100vh;
    }
}

/* Hover capability (touch vs mouse) */
@media (hover: hover) {
    .button:hover {
        background: blue;
    }
}

/* Prefers reduced motion */
@media (prefers-reduced-motion: reduce) {
    * {
        animation: none !important;
        transition: none !important;
    }
}

/* Dark mode */
@media (prefers-color-scheme: dark) {
    body {
        background: #1a1a1a;
        color: #ffffff;
    }
}

/* Print styles */
@media print {
    .no-print {
        display: none;
    }
}
```

#### Mobile-First Approach

Start with mobile styles, then add complexity for larger screens:

```css
/* Base styles (mobile) */
.nav {
    display: flex;
    flex-direction: column;
}

.nav-item {
    padding: 15px;
    border-bottom: 1px solid #ddd;
}

/* Tablet and up */
@media (min-width: 768px) {
    .nav {
        flex-direction: row;
        justify-content: center;
    }
    
    .nav-item {
        border-bottom: none;
        padding: 10px 20px;
    }
}

/* Desktop */
@media (min-width: 1024px) {
    .nav {
        justify-content: flex-end;
    }
}
```

#### Responsive Units

```css
.responsive {
    /* Viewport units */
    width: 100vw;           /* 100% of viewport width */
    height: 100vh;          /* 100% of viewport height */
    font-size: 5vw;         /* 5% of viewport width */
    padding: 2vmin;         /* 2% of smaller dimension */
    margin: 2vmax;          /* 2% of larger dimension */
    
    /* Relative units */
    font-size: 1rem;        /* Relative to root font-size (16px default) */
    padding: 1.5em;         /* Relative to element's font-size */
    width: 50%;             /* Relative to parent */
    
    /* Modern viewport units (account for mobile browser UI) */
    height: 100dvh;         /* Dynamic viewport height */
    height: 100svh;         /* Small viewport height */
    height: 100lvh;         /* Large viewport height */
}

/* clamp() for responsive values */
.clamp-example {
    /* clamp(minimum, preferred, maximum) */
    font-size: clamp(1rem, 2.5vw, 2rem);
    width: clamp(300px, 50%, 800px);
    padding: clamp(10px, 3vw, 40px);
}

/* min() and max() */
.minmax-example {
    width: min(100%, 1200px);          /* Smaller of the two */
    height: max(300px, 50vh);          /* Larger of the two */
    padding: min(5vw, 50px);
}
```

#### Fluid Typography

```css
/* Scale typography with viewport */
html {
    font-size: clamp(14px, 1vw + 12px, 18px);
}

h1 {
    font-size: clamp(2rem, 5vw, 4rem);
}

h2 {
    font-size: clamp(1.5rem, 4vw, 3rem);
}

/* Fluid spacing */
.section {
    padding: clamp(2rem, 5vw, 5rem) 0;
}

.container {
    padding-inline: clamp(1rem, 5vw, 3rem);
}
```

### CSS Transitions

#### Transition Properties

Transitions animate changes smoothly:

```css
.button {
    background-color: blue;
    color: white;
    padding: 10px 20px;
    
    /* Individual properties */
    transition-property: background-color, transform;
    transition-duration: 0.3s;
    transition-timing-function: ease;
    transition-delay: 0s;
    
    /* Shorthand */
    transition: background-color 0.3s ease;
    
    /* Multiple transitions */
    transition: 
        background-color 0.3s ease,
        transform 0.2s ease-out,
        box-shadow 0.3s ease;
    
    /* All properties */
    transition: all 0.3s ease;
}

.button:hover {
    background-color: darkblue;
    transform: scale(1.05);
    box-shadow: 0 4px 15px rgba(0,0,0,0.3);
}
```

#### Timing Functions

```css
.timing {
    /* Keywords */
    transition-timing-function: linear;       /* Constant speed */
    transition-timing-function: ease;         /* Slow start and end */
    transition-timing-function: ease-in;      /* Slow start */
    transition-timing-function: ease-out;     /* Slow end */
    transition-timing-function: ease-in-out;  /* Slow start and end */
    
    /* Custom cubic-bezier */
    transition-timing-function: cubic-bezier(0.68, -0.55, 0.27, 1.55); /* Bounce */
    
    /* Steps (for sprite animations) */
    transition-timing-function: steps(4, end);
}
```

### CSS Animations

#### Keyframes

Define animation stages with `@keyframes`:

```css
/* Simple animation */
@keyframes fadeIn {
    from {
        opacity: 0;
    }
    to {
        opacity: 1;
    }
}

/* Multiple steps */
@keyframes bounce {
    0%, 100% {
        transform: translateY(0);
    }
    50% {
        transform: translateY(-20px);
    }
}

/* Complex animation */
@keyframes slideInRotate {
    0% {
        opacity: 0;
        transform: translateX(-100px) rotate(-180deg);
    }
    60% {
        transform: translateX(20px) rotate(10deg);
    }
    100% {
        opacity: 1;
        transform: translateX(0) rotate(0);
    }
}
```

#### Animation Properties

```css
.animated {
    /* Individual properties */
    animation-name: fadeIn;
    animation-duration: 1s;
    animation-timing-function: ease-out;
    animation-delay: 0.5s;
    animation-iteration-count: 1;           /* or 'infinite' */
    animation-direction: normal;            /* normal, reverse, alternate */
    animation-fill-mode: forwards;          /* none, forwards, backwards, both */
    animation-play-state: running;          /* running, paused */
    
    /* Shorthand */
    animation: fadeIn 1s ease-out 0.5s 1 normal forwards;
    
    /* Multiple animations */
    animation: 
        fadeIn 1s ease-out,
        slideUp 0.5s ease-out 0.3s;
}

/* Common animations */
@keyframes pulse {
    0%, 100% { transform: scale(1); }
    50% { transform: scale(1.05); }
}

@keyframes shake {
    0%, 100% { transform: translateX(0); }
    25% { transform: translateX(-5px); }
    75% { transform: translateX(5px); }
}

@keyframes spin {
    from { transform: rotate(0deg); }
    to { transform: rotate(360deg); }
}

.loading {
    animation: spin 1s linear infinite;
}
```

#### Performance Considerations

```css
/* Use transform and opacity for smooth animations */
.good-animation {
    /* These are GPU-accelerated */
    transition: transform 0.3s, opacity 0.3s;
}

.good-animation:hover {
    transform: scale(1.1);
    opacity: 0.9;
}

/* Avoid animating these (cause repaints) */
.bad-animation {
    /* These are expensive */
    transition: width 0.3s, height 0.3s, left 0.3s, top 0.3s;
}

/* Use will-change sparingly */
.optimized {
    will-change: transform, opacity;
}
```

### CSS Transforms

#### 2D Transforms

```css
.transform-2d {
    /* Translate (move) */
    transform: translateX(50px);
    transform: translateY(30px);
    transform: translate(50px, 30px);
    transform: translate(-50%, -50%);      /* Center trick */
    
    /* Scale */
    transform: scaleX(1.5);
    transform: scaleY(0.5);
    transform: scale(1.5);                  /* Both axes */
    transform: scale(1.5, 0.5);             /* X, Y */
    
    /* Rotate */
    transform: rotate(45deg);
    transform: rotate(-90deg);
    transform: rotate(0.5turn);
    
    /* Skew */
    transform: skewX(15deg);
    transform: skewY(10deg);
    transform: skew(15deg, 10deg);
    
    /* Multiple transforms */
    transform: translate(50px, 50px) rotate(45deg) scale(1.2);
    
    /* Transform origin */
    transform-origin: center center;        /* Default */
    transform-origin: top left;
    transform-origin: 100% 100%;
    transform-origin: 50px 50px;
}

/* Centering with transform */
.center-absolute {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}
```

#### 3D Transforms

```css
/* Enable 3D space */
.container-3d {
    perspective: 1000px;                    /* Distance from viewer */
    perspective-origin: center center;
}

.transform-3d {
    /* Rotate in 3D */
    transform: rotateX(45deg);              /* Tilt forward/back */
    transform: rotateY(45deg);              /* Turn left/right */
    transform: rotateZ(45deg);              /* Same as 2D rotate */
    transform: rotate3d(1, 1, 0, 45deg);    /* Custom axis */
    
    /* Translate in 3D */
    transform: translateZ(100px);           /* Move toward viewer */
    transform: translate3d(50px, 50px, 100px);
    
    /* Scale in 3D */
    transform: scaleZ(2);
    transform: scale3d(1, 1, 2);
    
    /* Preserve 3D for children */
    transform-style: preserve-3d;
    
    /* Hide back face */
    backface-visibility: hidden;
}

/* Card flip effect */
.card-flip {
    perspective: 1000px;
}

.card-inner {
    transition: transform 0.6s;
    transform-style: preserve-3d;
}

.card-flip:hover .card-inner {
    transform: rotateY(180deg);
}

.card-front, .card-back {
    backface-visibility: hidden;
    position: absolute;
    width: 100%;
    height: 100%;
}

.card-back {
    transform: rotateY(180deg);
}
```

### CSS Variables

CSS Custom Properties (variables) enable dynamic, maintainable styling.

#### Defining Variables

```css
/* Global variables (on :root) */
:root {
    /* Colors */
    --color-primary: #007bff;
    --color-secondary: #6c757d;
    --color-success: #28a745;
    --color-danger: #dc3545;
    --color-text: #333333;
    --color-background: #ffffff;
    
    /* Typography */
    --font-family: 'Segoe UI', Tahoma, sans-serif;
    --font-size-base: 16px;
    --font-size-lg: 1.25rem;
    --font-size-sm: 0.875rem;
    --line-height: 1.5;
    
    /* Spacing */
    --spacing-xs: 0.25rem;
    --spacing-sm: 0.5rem;
    --spacing-md: 1rem;
    --spacing-lg: 1.5rem;
    --spacing-xl: 3rem;
    
    /* Other */
    --border-radius: 4px;
    --shadow: 0 2px 4px rgba(0,0,0,0.1);
    --transition: 0.3s ease;
}

/* Component-scoped variables */
.card {
    --card-padding: 1.5rem;
    --card-bg: white;
    --card-border: 1px solid #ddd;
}
```

#### Using Variables

```css
.button {
    background-color: var(--color-primary);
    color: var(--color-background);
    padding: var(--spacing-sm) var(--spacing-md);
    border-radius: var(--border-radius);
    font-family: var(--font-family);
    transition: all var(--transition);
}

/* Fallback value */
.element {
    color: var(--undefined-variable, #333);
    padding: var(--spacing-md, 1rem);
}

/* Variables in calc() */
.container {
    max-width: calc(var(--spacing-xl) * 20);
    padding: calc(var(--spacing-md) * 2);
}
```

#### Theming with Variables

```css
/* Default (light) theme */
:root {
    --bg-color: #ffffff;
    --text-color: #333333;
    --border-color: #dddddd;
    --primary: #007bff;
}

/* Dark theme */
[data-theme="dark"] {
    --bg-color: #1a1a2e;
    --text-color: #eaeaea;
    --border-color: #444444;
    --primary: #4da3ff;
}

/* Auto dark mode */
@media (prefers-color-scheme: dark) {
    :root {
        --bg-color: #1a1a2e;
        --text-color: #eaeaea;
        --border-color: #444444;
        --primary: #4da3ff;
    }
}

/* Use the variables */
body {
    background-color: var(--bg-color);
    color: var(--text-color);
}

.card {
    border: 1px solid var(--border-color);
}

.btn-primary {
    background-color: var(--primary);
}
```

### Advanced Selectors

#### Combinators

```css
/* Descendant (space) - any nested element */
article p {
    line-height: 1.8;
}

/* Child (>) - direct children only */
ul > li {
    list-style: disc;
}

/* Adjacent sibling (+) - immediately after */
h2 + p {
    font-size: 1.2rem;
    margin-top: 0;
}

/* General sibling (~) - any sibling after */
h2 ~ p {
    margin-left: 20px;
}

/* Combining combinators */
.sidebar > ul > li > a {
    color: inherit;
}
```

#### :not(), :is(), :where()

```css
/* :not() - negation */
button:not(:disabled) {
    cursor: pointer;
}

a:not([href^="http"]) {
    /* Internal links */
    color: blue;
}

p:not(:first-child):not(:last-child) {
    margin: 1rem 0;
}

/* :is() - matches any selector in list (takes highest specificity) */
:is(h1, h2, h3, h4, h5, h6) {
    font-family: Georgia, serif;
}

article :is(header, footer) p {
    font-size: 0.9rem;
}

/* :where() - same as :is() but zero specificity */
:where(h1, h2, h3) {
    margin-top: 2rem;
}

/* Easy to override */
h1 {
    margin-top: 0; /* This wins */
}
```

#### :has() Selector

The "parent selector" - style elements based on their children:

```css
/* Card with image gets different padding */
.card:has(img) {
    padding-top: 0;
}

/* Form group with invalid input */
.form-group:has(input:invalid) {
    border-color: red;
}

/* Section with no paragraphs */
section:not(:has(p)) {
    padding: 1rem;
}

/* Navigation with dropdown */
nav:has(.dropdown:hover) {
    background: #333;
}

/* Figure with figcaption */
figure:has(figcaption) img {
    margin-bottom: 0;
}
```

### CSS Preprocessors

#### SASS/SCSS

SASS (Syntactically Awesome Style Sheets) extends CSS with programming features.

```scss
// Variables (SCSS syntax)
$primary-color: #007bff;
$font-stack: 'Helvetica Neue', sans-serif;
$border-radius: 4px;
$spacing: 8px;

// Nesting
.navbar {
    background: #333;
    padding: $spacing * 2;
    
    ul {
        display: flex;
        list-style: none;
        
        li {
            margin: 0 $spacing;
            
            a {
                color: white;
                text-decoration: none;
                
                &:hover {
                    color: $primary-color;
                }
            }
        }
    }
}

// Mixins (reusable blocks)
@mixin flex-center {
    display: flex;
    justify-content: center;
    align-items: center;
}

@mixin button($bg-color) {
    background-color: $bg-color;
    color: white;
    padding: $spacing $spacing * 2;
    border: none;
    border-radius: $border-radius;
    cursor: pointer;
    
    &:hover {
        background-color: darken($bg-color, 10%);
    }
}

.btn-primary {
    @include button($primary-color);
}

.centered-container {
    @include flex-center;
    min-height: 100vh;
}

// Extend (inheritance)
%message-shared {
    padding: 10px;
    border-radius: $border-radius;
    margin-bottom: 10px;
}

.success {
    @extend %message-shared;
    background: green;
}

.error {
    @extend %message-shared;
    background: red;
}

// Functions
@function calculate-width($columns, $total: 12) {
    @return percentage($columns / $total);
}

.col-6 {
    width: calculate-width(6); // 50%
}

// Conditionals and loops
@for $i from 1 through 12 {
    .col-#{$i} {
        width: calculate-width($i);
    }
}

@each $name, $color in (primary: blue, secondary: gray, danger: red) {
    .text-#{$name} {
        color: $color;
    }
}
```

---

## Part 3: Best Practices & Tips

### CSS Architecture

#### BEM Methodology

BEM (Block Element Modifier) is a naming convention that makes CSS more maintainable:

```css
/* Block: standalone component */
.card { }
.navbar { }
.button { }

/* Element: part of a block (double underscore) */
.card__header { }
.card__body { }
.card__footer { }
.navbar__logo { }
.navbar__menu { }

/* Modifier: variation of block/element (double hyphen) */
.card--featured { }
.card--compact { }
.button--primary { }
.button--large { }
.button--disabled { }

/* Combined example */
.card { 
    border: 1px solid #ddd;
    border-radius: 8px;
}

.card--featured {
    border-color: gold;
    box-shadow: 0 4px 15px rgba(0,0,0,0.1);
}

.card__header {
    padding: 1rem;
    border-bottom: 1px solid #ddd;
}

.card__title {
    margin: 0;
    font-size: 1.25rem;
}

.card__body {
    padding: 1rem;
}

.card__footer {
    padding: 1rem;
    background: #f5f5f5;
}
```

```html
<article class="card card--featured">
    <header class="card__header">
        <h2 class="card__title">Card Title</h2>
    </header>
    <div class="card__body">
        <p>Card content...</p>
    </div>
    <footer class="card__footer">
        <button class="button button--primary">Action</button>
    </footer>
</article>
```

#### SMACSS

SMACSS (Scalable and Modular Architecture for CSS) organizes styles into categories:

```css
/* 1. Base - defaults for elements */
html, body {
    margin: 0;
    padding: 0;
}

a {
    color: #007bff;
}

/* 2. Layout - major sections (prefixed with l-) */
.l-header {
    position: fixed;
    top: 0;
    width: 100%;
}

.l-sidebar {
    width: 250px;
    float: left;
}

.l-main {
    margin-left: 250px;
}

/* 3. Module - reusable components */
.nav { }
.card { }
.btn { }

/* 4. State - temporary states (prefixed with is-) */
.is-active { }
.is-hidden { }
.is-loading { }
.is-collapsed { }

.nav-item.is-active {
    font-weight: bold;
    border-bottom: 2px solid #007bff;
}

.sidebar.is-collapsed {
    width: 60px;
}

/* 5. Theme - visual styling */
.theme-dark { }
.theme-light { }
```

#### Atomic CSS

Atomic CSS uses single-purpose utility classes:

```css
/* Spacing utilities */
.m-0 { margin: 0; }
.m-1 { margin: 0.25rem; }
.m-2 { margin: 0.5rem; }
.m-3 { margin: 1rem; }
.m-4 { margin: 1.5rem; }

.mt-1 { margin-top: 0.25rem; }
.mr-1 { margin-right: 0.25rem; }
.mb-1 { margin-bottom: 0.25rem; }
.ml-1 { margin-left: 0.25rem; }
.mx-1 { margin-left: 0.25rem; margin-right: 0.25rem; }
.my-1 { margin-top: 0.25rem; margin-bottom: 0.25rem; }

/* Same pattern for padding: p-0, pt-1, px-2, etc. */

/* Display utilities */
.d-none { display: none; }
.d-block { display: block; }
.d-flex { display: flex; }
.d-grid { display: grid; }

/* Flexbox utilities */
.flex-row { flex-direction: row; }
.flex-column { flex-direction: column; }
.justify-center { justify-content: center; }
.justify-between { justify-content: space-between; }
.align-center { align-items: center; }
.flex-wrap { flex-wrap: wrap; }
.gap-1 { gap: 0.25rem; }
.gap-2 { gap: 0.5rem; }

/* Text utilities */
.text-center { text-align: center; }
.text-left { text-align: left; }
.text-right { text-align: right; }
.font-bold { font-weight: bold; }
.text-sm { font-size: 0.875rem; }
.text-lg { font-size: 1.25rem; }

/* Color utilities */
.text-primary { color: var(--primary); }
.bg-primary { background-color: var(--primary); }
.text-white { color: white; }
.bg-white { background-color: white; }

/* Width utilities */
.w-full { width: 100%; }
.w-auto { width: auto; }
.max-w-lg { max-width: 800px; }

/* Visibility */
.visible { visibility: visible; }
.invisible { visibility: hidden; }
.opacity-0 { opacity: 0; }
.opacity-50 { opacity: 0.5; }
.opacity-100 { opacity: 1; }
```

```html
<!-- Usage -->
<div class="d-flex justify-between align-center p-3 bg-white">
    <h1 class="m-0 text-lg font-bold">Title</h1>
    <button class="px-3 py-2 bg-primary text-white">Click</button>
</div>
```

**Popular Atomic CSS Frameworks:** Tailwind CSS, Tachyons, Basscss

### Performance Optimization

#### CSS Minification

Remove whitespace, comments, and unnecessary characters:

```css
/* Before minification */
.button {
    display: inline-block;
    padding: 10px 20px;
    background-color: #007bff;
    color: white;
    border-radius: 4px;
}

/* After minification */
.button{display:inline-block;padding:10px 20px;background-color:#007bff;color:#fff;border-radius:4px}
```

**Tools:**
- Build tools: Webpack, Vite, Parcel (automatic)
- Online: cssnano, clean-css
- CLI: `csso`, `cleancss`

#### Critical CSS

Inline above-the-fold CSS for faster first paint:

```html
<head>
    <!-- Critical CSS inlined -->
    <style>
        /* Only styles needed for initial viewport */
        body { margin: 0; font-family: sans-serif; }
        .header { background: #333; color: white; padding: 1rem; }
        .hero { height: 100vh; display: flex; align-items: center; }
    </style>
    
    <!-- Full CSS loaded async -->
    <link rel="preload" href="styles.css" as="style" onload="this.onload=null;this.rel='stylesheet'">
    <noscript><link rel="stylesheet" href="styles.css"></noscript>
</head>
```

**Tools:** Critical, Penthouse, Critters (webpack plugin)

#### Reducing Reflows and Repaints

**Expensive operations (cause reflow):**
- Changing `width`, `height`, `padding`, `margin`
- Changing `top`, `left`, `right`, `bottom`
- Reading layout properties (offsetHeight, scrollTop)
- Adding/removing DOM elements

**Cheap operations (GPU-accelerated):**
- `transform`
- `opacity`
- `filter`

```css
/* Bad - causes reflow */
.animate-bad {
    transition: left 0.3s, top 0.3s, width 0.3s;
}
.animate-bad:hover {
    left: 100px;
    top: 50px;
    width: 200px;
}

/* Good - GPU accelerated */
.animate-good {
    transition: transform 0.3s, opacity 0.3s;
}
.animate-good:hover {
    transform: translate(100px, 50px) scale(1.2);
    opacity: 0.8;
}
```

**Batch DOM reads and writes:**
```javascript
// Bad - forces multiple reflows
elements.forEach(el => {
    const height = el.offsetHeight; // Read
    el.style.height = height + 10 + 'px'; // Write
});

// Good - batch reads, then writes
const heights = elements.map(el => el.offsetHeight);
elements.forEach((el, i) => {
    el.style.height = heights[i] + 10 + 'px';
});
```

#### Will-Change Property

Hints to browser about upcoming changes:

```css
/* Use sparingly - has memory cost */
.animated-element {
    will-change: transform, opacity;
}

/* Remove after animation */
.animated-element.animation-done {
    will-change: auto;
}

/* Better: add will-change on hover/focus */
.button {
    transition: transform 0.2s;
}
.button:hover {
    will-change: transform;
}
.button:active {
    transform: scale(0.95);
}
```

**Don't overuse:** 
```css
/* BAD - wastes resources */
* {
    will-change: transform;
}
```

### Cross-Browser Compatibility

#### Vendor Prefixes

Add prefixes for experimental features (use Autoprefixer in production):

```css
.element {
    /* Flexbox (older browsers) */
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    
    /* User select */
    -webkit-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
    
    /* Backdrop filter */
    -webkit-backdrop-filter: blur(10px);
    backdrop-filter: blur(10px);
    
    /* Appearance */
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
}

/* Keyframes */
@-webkit-keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
}
@keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
}
```

**Autoprefixer** (recommended) - add to build process:
```javascript
// postcss.config.js
module.exports = {
    plugins: [
        require('autoprefixer')
    ]
}
```

#### CSS Resets and Normalizers

**Reset CSS** - removes all default styles:
```css
/* Basic reset */
*, *::before, *::after {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

html {
    font-size: 16px;
    -webkit-text-size-adjust: 100%;
}

body {
    min-height: 100vh;
    line-height: 1.5;
}

img, picture, video, canvas, svg {
    display: block;
    max-width: 100%;
}

input, button, textarea, select {
    font: inherit;
}

h1, h2, h3, h4, h5, h6, p {
    overflow-wrap: break-word;
}
```

**Normalize.css** - preserves useful defaults, fixes inconsistencies:
```html
<link rel="stylesheet" href="https://unpkg.com/normalize.css">
```

**Modern Reset (Josh Comeau's):**
```css
*, *::before, *::after {
    box-sizing: border-box;
}

* {
    margin: 0;
}

body {
    line-height: 1.5;
    -webkit-font-smoothing: antialiased;
}

img, picture, video, canvas, svg {
    display: block;
    max-width: 100%;
}

input, button, textarea, select {
    font: inherit;
}

p, h1, h2, h3, h4, h5, h6 {
    overflow-wrap: break-word;
}

#root, #__next {
    isolation: isolate;
}
```

### Accessibility in CSS

#### Focus Styles

Never remove focus outlines without providing alternatives:

```css
/* BAD - removes accessibility */
*:focus {
    outline: none;
}

/* GOOD - custom focus styles */
:focus {
    outline: 2px solid #007bff;
    outline-offset: 2px;
}

/* Focus visible - only show for keyboard users */
:focus:not(:focus-visible) {
    outline: none;
}

:focus-visible {
    outline: 2px solid #007bff;
    outline-offset: 2px;
}

/* Custom focus ring */
.button:focus-visible {
    outline: none;
    box-shadow: 0 0 0 3px rgba(0, 123, 255, 0.5);
}

/* Skip link */
.skip-link {
    position: absolute;
    top: -40px;
    left: 0;
    padding: 8px;
    background: #000;
    color: #fff;
    z-index: 1000;
}

.skip-link:focus {
    top: 0;
}
```

#### Color Contrast

Ensure sufficient contrast ratios:

```css
/* WCAG AA requirements:
   - Normal text: 4.5:1 minimum
   - Large text (18pt+): 3:1 minimum
   - UI components: 3:1 minimum
*/

/* Good contrast */
.good-contrast {
    background: #ffffff;
    color: #333333;  /* 12.6:1 ratio */
}

/* Poor contrast - avoid */
.poor-contrast {
    background: #ffffff;
    color: #aaaaaa;  /* 2.3:1 ratio - FAILS */
}

/* High contrast mode support */
@media (prefers-contrast: high) {
    :root {
        --text-color: #000000;
        --bg-color: #ffffff;
        --border-color: #000000;
    }
    
    .button {
        border: 2px solid currentColor;
    }
}

/* Forced colors mode (Windows High Contrast) */
@media (forced-colors: active) {
    .button {
        border: 2px solid ButtonText;
    }
    
    .icon {
        forced-color-adjust: none;
    }
}
```

**Tools:** WebAIM Contrast Checker, Chrome DevTools

#### Screen Reader Friendly CSS

```css
/* Visually hidden but accessible to screen readers */
.sr-only {
    position: absolute;
    width: 1px;
    height: 1px;
    padding: 0;
    margin: -1px;
    overflow: hidden;
    clip: rect(0, 0, 0, 0);
    white-space: nowrap;
    border: 0;
}

/* Skip when focused (for skip links) */
.sr-only-focusable:focus {
    position: static;
    width: auto;
    height: auto;
    overflow: visible;
    clip: auto;
    white-space: normal;
}

/* Hide from screen readers (decorative) */
.decorative {
    aria-hidden: true;
}

/* Don't use display:none for content that should be read */
/* BAD - hidden from everyone */
.hidden-wrong {
    display: none;
}

/* GOOD - visible to screen readers */
.hidden-visually {
    position: absolute;
    clip: rect(0, 0, 0, 0);
}

/* Respect reduced motion preference */
@media (prefers-reduced-motion: reduce) {
    *, *::before, *::after {
        animation-duration: 0.01ms !important;
        animation-iteration-count: 1 !important;
        transition-duration: 0.01ms !important;
        scroll-behavior: auto !important;
    }
}
```

### Common Mistakes to Avoid

**1. Using IDs for styling**
```css
/* Avoid - too specific, hard to override */
#header { }

/* Prefer classes */
.header { }
```

**2. Over-qualifying selectors**
```css
/* Avoid - unnecessarily specific */
div.container ul.nav li.nav-item a.nav-link { }

/* Better */
.nav-link { }
```

**3. Using !important**
```css
/* Avoid except for utilities */
.text-red {
    color: red !important;  /* Only OK for utilities */
}

/* Don't use to fix specificity issues */
.button {
    background: blue !important;  /* Bad practice */
}
```

**4. Magic numbers**
```css
/* Avoid unexplained numbers */
.element {
    margin-top: 37px;  /* Why 37? */
}

/* Better - use variables or explain */
.element {
    margin-top: calc(var(--header-height) + var(--spacing-md));
}
```

**5. Styling with element selectors**
```css
/* Avoid - affects all divs */
div {
    margin: 10px;
}

/* Use classes */
.card {
    margin: 10px;
}
```

**6. Not using shorthand properly**
```css
/* Know what shorthand resets */
.element {
    margin: 10px;  /* Resets ALL margins */
    margin-left: 20px;  /* Then overrides left */
}

/* Sometimes longhand is clearer */
.element {
    margin-block: 10px;
    margin-inline: 20px;
}
```

**7. Forgetting box-sizing**
```css
/* Always include this reset */
*, *::before, *::after {
    box-sizing: border-box;
}
```

**8. Z-index wars**
```css
/* Avoid arbitrary large numbers */
.modal {
    z-index: 999999;  /* Bad */
}

/* Use a scale system */
:root {
    --z-dropdown: 100;
    --z-sticky: 200;
    --z-modal: 300;
    --z-tooltip: 400;
}

.modal {
    z-index: var(--z-modal);
}
```

### Modern CSS Features

#### Container Queries

Style based on container size, not viewport:

```css
/* Define a container */
.card-container {
    container-type: inline-size;
    container-name: card;
}

/* Query the container */
@container card (min-width: 400px) {
    .card {
        display: flex;
        gap: 1rem;
    }
    
    .card-image {
        width: 40%;
    }
}

@container card (min-width: 600px) {
    .card-title {
        font-size: 1.5rem;
    }
}

/* Shorthand */
.wrapper {
    container: sidebar / inline-size;
}

/* Container query units */
.element {
    font-size: 5cqi;   /* 5% of container inline size */
    padding: 2cqb;     /* 2% of container block size */
    width: 50cqw;      /* 50% of container width */
}
```

#### Aspect Ratio

Maintain proportions without padding hacks:

```css
/* Fixed aspect ratio */
.video-container {
    aspect-ratio: 16 / 9;
    width: 100%;
}

.square {
    aspect-ratio: 1;  /* Same as 1 / 1 */
}

.portrait {
    aspect-ratio: 3 / 4;
}

/* With object-fit for images */
.thumbnail {
    aspect-ratio: 1;
    width: 100px;
    object-fit: cover;
}

/* Responsive images maintaining ratio */
img {
    aspect-ratio: attr(width) / attr(height);
    width: 100%;
    height: auto;
}
```

#### Logical Properties

Write CSS that works for all writing directions (LTR/RTL):

```css
/* Physical properties (old way) */
.physical {
    margin-left: 20px;
    padding-right: 10px;
    border-top: 1px solid;
    text-align: left;
}

/* Logical properties (new way) */
.logical {
    margin-inline-start: 20px;   /* Left in LTR, Right in RTL */
    padding-inline-end: 10px;    /* Right in LTR, Left in RTL */
    border-block-start: 1px solid;  /* Top in horizontal writing */
    text-align: start;
}

/* Logical property mapping */
.element {
    /* Block = vertical axis (top/bottom in horizontal) */
    margin-block: 1rem;           /* margin-top + margin-bottom */
    margin-block-start: 1rem;     /* margin-top */
    margin-block-end: 1rem;       /* margin-bottom */
    
    /* Inline = horizontal axis (left/right in horizontal) */
    margin-inline: 1rem;          /* margin-left + margin-right */
    margin-inline-start: 1rem;    /* margin-left in LTR */
    margin-inline-end: 1rem;      /* margin-right in LTR */
    
    /* Sizing */
    inline-size: 100%;            /* width in horizontal */
    block-size: 50vh;             /* height in horizontal */
    max-inline-size: 800px;       /* max-width */
    
    /* Positioning */
    inset: 0;                     /* top, right, bottom, left: 0 */
    inset-block: 10px;            /* top + bottom */
    inset-inline: 20px;           /* left + right */
    inset-inline-start: 0;        /* left in LTR */
    
    /* Border radius */
    border-start-start-radius: 8px;  /* top-left in LTR */
    border-end-end-radius: 8px;      /* bottom-right in LTR */
}
```

### Tools and Resources

**Browser DevTools:**
- Inspect and edit CSS live
- View computed styles
- Debug layouts with Grid/Flexbox inspectors
- Test responsive designs
- Audit accessibility

**CSS Frameworks:**
- **Tailwind CSS** - Utility-first framework
- **Bootstrap** - Component library
- **Bulma** - Modern Flexbox framework
- **Foundation** - Professional framework

**Build Tools:**
- **PostCSS** - Transform CSS with plugins
- **Autoprefixer** - Add vendor prefixes
- **cssnano** - Minify CSS
- **PurgeCSS** - Remove unused CSS

**Online Tools:**
- [Can I Use](https://caniuse.com/) - Browser support tables
- [CSS Tricks](https://css-tricks.com/) - Tutorials and guides
- [Flexbox Froggy](https://flexboxfroggy.com/) - Learn Flexbox
- [Grid Garden](https://cssgridgarden.com/) - Learn CSS Grid
- [Cubic Bezier](https://cubic-bezier.com/) - Easing function generator
- [Clippy](https://bennettfeely.com/clippy/) - Clip-path generator
- [CSS Gradient](https://cssgradient.io/) - Gradient generator
- [Shadows Brumm](https://shadows.brumm.af/) - Shadow generator
- [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/)

**Documentation:**
- [MDN CSS Reference](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [W3Schools CSS Tutorial](https://www.w3schools.com/css/)
- [CSS Specifications](https://www.w3.org/Style/CSS/)

**Learning Resources:**
- [freeCodeCamp](https://www.freecodecamp.org/)
- [Codecademy CSS Course](https://www.codecademy.com/learn/learn-css)
- [Kevin Powell (YouTube)](https://www.youtube.com/@KevinPowell)
- [Wes Bos CSS Grid Course](https://cssgrid.io/)
- [Josh Comeau's CSS Blog](https://www.joshwcomeau.com/)
