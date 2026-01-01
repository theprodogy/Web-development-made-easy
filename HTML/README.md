# HTML Documentation

Welcome to the HTML section of Web Development Made Easy!

## Table of Contents

### Part 1: Fundamentals
- [Introduction to HTML](#introduction-to-html)
- [Setting Up Your Environment](#setting-up-your-environment)
- [HTML Document Structure](#html-document-structure)
- [Essential HTML Tags](#essential-html-tags)
  - [Headings and Paragraphs](#headings-and-paragraphs)
  - [Links and Images](#links-and-images)
  - [Lists (Ordered & Unordered)](#lists-ordered--unordered)
  - [Tables](#tables)
- [HTML Attributes](#html-attributes)
- [Block vs Inline Elements](#block-vs-inline-elements)
- [HTML Forms Basics](#html-forms-basics)
  - [Input Types](#input-types)
  - [Form Validation](#form-validation)
  - [Buttons and Submissions](#buttons-and-submissions)

### Part 2: Advanced Topics
- [Semantic HTML](#semantic-html)
  - [Why Semantic HTML Matters](#why-semantic-html-matters)
  - [Semantic Tags (header, nav, main, article, section, aside, footer)](#semantic-tags)
  - [Accessibility Benefits](#accessibility-benefits)
- [HTML5 Features](#html5-features)
  - [Audio and Video Elements](#audio-and-video-elements)
  - [Canvas and SVG](#canvas-and-svg)
  - [Local Storage and Session Storage](#local-storage-and-session-storage)
  - [Geolocation API](#geolocation-api)
- [Meta Tags and SEO](#meta-tags-and-seo)
  - [Essential Meta Tags](#essential-meta-tags)
  - [Open Graph Tags](#open-graph-tags)
  - [Twitter Cards](#twitter-cards)
- [Accessibility (ARIA)](#accessibility-aria)
  - [ARIA Roles](#aria-roles)
  - [ARIA Labels and Descriptions](#aria-labels-and-descriptions)
  - [Keyboard Navigation](#keyboard-navigation)
- [Performance Optimization](#performance-optimization)
  - [Lazy Loading Images](#lazy-loading-images)
  - [Preloading Resources](#preloading-resources)
  - [Minimizing HTML Size](#minimizing-html-size)

### Part 3: Best Practices & Tips
- [Code Organization](#code-organization)
- [Naming Conventions](#naming-conventions)
- [Cross-Browser Compatibility](#cross-browser-compatibility)
- [Responsive HTML](#responsive-html)
- [Common Mistakes to Avoid](#common-mistakes-to-avoid)
- [Tools and Validators](#tools-and-validators)
- [Resources and Further Learning](#resources-and-further-learning)

---

## Part 1: Fundamentals

### Introduction to HTML

HTML (HyperText Markup Language) is the standard markup language used to create and structure content on the web. It forms the backbone of every website you visit, defining the structure and meaning of web content.

**What HTML Does:**
- Defines the structure of web pages (headings, paragraphs, lists, etc.)
- Embeds media like images, videos, and audio
- Creates links between web pages
- Provides forms for user input
- Gives meaning to content through semantic elements

**Key Concepts:**
- HTML uses **elements** (also called tags) to wrap content
- Elements are written with angle brackets: `<tagname>content</tagname>`
- Most elements have opening and closing tags
- Some elements are self-closing: `<img />`, `<br />`, `<hr />`

```html
<!-- This is an HTML comment -->
<p>This is a paragraph element with text content.</p>
```

### Setting Up Your Environment

To start writing HTML, you need minimal setup:

**1. Text Editor**
Choose a code editor. Popular options include:
- **VS Code** (recommended) - Free, powerful, great extensions
- **Sublime Text** - Fast and lightweight
- **Atom** - Customizable, open-source
- **Notepad++** - Simple, Windows-only

**2. Web Browser**
Any modern browser works for viewing HTML:
- Chrome (recommended for DevTools)
- Firefox
- Edge
- Safari

**3. Create Your First File**
1. Open your text editor
2. Create a new file
3. Save it with a `.html` extension (e.g., `index.html`)
4. Open it in your browser by double-clicking the file

**Pro Tip:** In VS Code, use the Live Server extension to automatically refresh your browser when you save changes.

### HTML Document Structure

Every HTML document follows a standard structure:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Page Title</title>
</head>
<body>
    <!-- Your content goes here -->
</body>
</html>
```

**Breakdown:**

| Element | Purpose |
|---------|---------|
| `<!DOCTYPE html>` | Declares this is an HTML5 document |
| `<html>` | Root element containing all HTML content |
| `lang="en"` | Specifies the page language (helps screen readers) |
| `<head>` | Contains metadata, not displayed on page |
| `<meta charset>` | Sets character encoding (UTF-8 supports all characters) |
| `<meta viewport>` | Makes page responsive on mobile devices |
| `<title>` | Sets the browser tab title |
| `<body>` | Contains all visible page content |

### Essential HTML Tags

#### Headings and Paragraphs

HTML has six heading levels, from `<h1>` (most important) to `<h6>` (least important):

```html
<h1>Main Title (use once per page)</h1>
<h2>Section Heading</h2>
<h3>Subsection Heading</h3>
<h4>Sub-subsection</h4>
<h5>Minor Heading</h5>
<h6>Smallest Heading</h6>

<p>This is a paragraph. Paragraphs are block-level elements that 
automatically add space before and after themselves.</p>

<p>Another paragraph. Each paragraph starts on a new line.</p>
```

**Best Practices:**
- Use only one `<h1>` per page
- Don't skip heading levels (don't go from `<h2>` to `<h4>`)
- Use headings for structure, not just for making text big

#### Links and Images

**Links (Anchor Tags):**
```html
<!-- External link -->
<a href="https://google.com">Visit Google</a>

<!-- Internal link (same website) -->
<a href="/about.html">About Us</a>

<!-- Open in new tab -->
<a href="https://example.com" target="_blank" rel="noopener noreferrer">
    External Link (New Tab)
</a>

<!-- Link to email -->
<a href="mailto:contact@example.com">Email Us</a>

<!-- Link to section on same page -->
<a href="#section-id">Jump to Section</a>
```

**Images:**
```html
<!-- Basic image -->
<img src="photo.jpg" alt="Description of the image">

<!-- Image with dimensions -->
<img src="photo.jpg" alt="Description" width="600" height="400">

<!-- Image from URL -->
<img src="https://example.com/image.png" alt="Remote image">
```

**Important:** Always include the `alt` attribute for accessibility. It describes the image for screen readers and displays if the image fails to load.

#### Lists (Ordered & Unordered)

```html
<!-- Unordered list (bullet points) -->
<ul>
    <li>First item</li>
    <li>Second item</li>
    <li>Third item</li>
</ul>

<!-- Ordered list (numbered) -->
<ol>
    <li>Step one</li>
    <li>Step two</li>
    <li>Step three</li>
</ol>

<!-- Nested lists -->
<ul>
    <li>Main item
        <ul>
            <li>Sub-item 1</li>
            <li>Sub-item 2</li>
        </ul>
    </li>
</ul>

<!-- Description list (term + definition) -->
<dl>
    <dt>HTML</dt>
    <dd>HyperText Markup Language</dd>
    <dt>CSS</dt>
    <dd>Cascading Style Sheets</dd>
</dl>
```

#### Tables

```html
<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Age</th>
            <th>City</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Alice</td>
            <td>25</td>
            <td>New York</td>
        </tr>
        <tr>
            <td>Bob</td>
            <td>30</td>
            <td>Los Angeles</td>
        </tr>
    </tbody>
</table>
```

**Table Elements:**
- `<table>` - Container for the table
- `<thead>` - Table header section
- `<tbody>` - Table body section
- `<tr>` - Table row
- `<th>` - Header cell (bold, centered by default)
- `<td>` - Data cell

**Spanning Cells:**
```html
<td colspan="2">Spans 2 columns</td>
<td rowspan="3">Spans 3 rows</td>
```

### HTML Attributes

Attributes provide additional information about elements. They're always placed in the opening tag.

```html
<element attribute="value">Content</element>
```

**Common Global Attributes:**

| Attribute | Purpose | Example |
|-----------|---------|---------|
| `id` | Unique identifier | `<div id="header">` |
| `class` | CSS class name(s) | `<p class="intro highlight">` |
| `style` | Inline CSS styles | `<p style="color: red;">` |
| `title` | Tooltip text on hover | `<abbr title="HyperText">HT</abbr>` |
| `hidden` | Hides the element | `<div hidden>` |
| `data-*` | Custom data attributes | `<div data-user-id="123">` |
| `lang` | Language of content | `<p lang="fr">Bonjour</p>` |

**Boolean Attributes:**
Some attributes don't need a value—their presence means "true":
```html
<input type="text" disabled>
<input type="checkbox" checked>
<video autoplay muted>
```

### Block vs Inline Elements

**Block Elements:**
- Start on a new line
- Take full width available
- Can contain other block and inline elements

```html
<!-- Block elements -->
<div>Generic container</div>
<p>Paragraph</p>
<h1>Heading</h1>
<ul>List</ul>
<section>Section</section>
<article>Article</article>
<header>Header</header>
<footer>Footer</footer>
```

**Inline Elements:**
- Don't start on a new line
- Only take necessary width
- Should only contain data or other inline elements

```html
<!-- Inline elements -->
<span>Generic inline container</span>
<a href="#">Link</a>
<strong>Bold text</strong>
<em>Italic text</em>
<img src="image.jpg">
<code>Code snippet</code>
<br> <!-- Line break -->
```

**Visual Example:**
```html
<p>This is a paragraph with <strong>bold</strong> and <em>italic</em> text.</p>
```

### HTML Forms Basics

Forms collect user input and send it to a server.

```html
<form action="/submit" method="POST">
    <label for="name">Name:</label>
    <input type="text" id="name" name="name" required>
    
    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required>
    
    <button type="submit">Submit</button>
</form>
```

**Form Attributes:**
- `action` - URL where form data is sent
- `method` - HTTP method (GET or POST)
- `enctype` - Encoding type (needed for file uploads)

#### Input Types

HTML5 provides many input types:

```html
<!-- Text inputs -->
<input type="text" placeholder="Enter text">
<input type="password" placeholder="Enter password">
<input type="email" placeholder="email@example.com">
<input type="tel" placeholder="Phone number">
<input type="url" placeholder="https://example.com">
<input type="search" placeholder="Search...">

<!-- Number inputs -->
<input type="number" min="0" max="100" step="1">
<input type="range" min="0" max="100">

<!-- Date/Time inputs -->
<input type="date">
<input type="time">
<input type="datetime-local">
<input type="month">
<input type="week">

<!-- Selection inputs -->
<input type="checkbox" id="agree">
<input type="radio" name="choice" value="a">
<input type="color">
<input type="file" accept="image/*">

<!-- Other -->
<input type="hidden" name="token" value="abc123">
<textarea rows="4" cols="50">Multi-line text</textarea>

<!-- Dropdown select -->
<select name="country">
    <option value="">Choose...</option>
    <option value="us">United States</option>
    <option value="uk">United Kingdom</option>
</select>
```

#### Form Validation

HTML5 provides built-in validation:

```html
<!-- Required field -->
<input type="text" required>

<!-- Min/max length -->
<input type="text" minlength="3" maxlength="20">

<!-- Pattern (regex) -->
<input type="text" pattern="[A-Za-z]{3,}" title="At least 3 letters">

<!-- Number range -->
<input type="number" min="1" max="100">

<!-- Email validation (automatic) -->
<input type="email" required>

<!-- URL validation (automatic) -->
<input type="url" required>
```

**Validation Attributes:**
| Attribute | Purpose |
|-----------|---------|
| `required` | Field must be filled |
| `minlength` | Minimum character count |
| `maxlength` | Maximum character count |
| `min` / `max` | Number/date range |
| `pattern` | Regex pattern to match |
| `step` | Increment for numbers |

#### Buttons and Submissions

```html
<!-- Submit button (submits the form) -->
<button type="submit">Submit</button>
<input type="submit" value="Submit">

<!-- Reset button (clears the form) -->
<button type="reset">Reset</button>
<input type="reset" value="Reset">

<!-- Regular button (no default behavior) -->
<button type="button" onclick="doSomething()">Click Me</button>

<!-- Image button -->
<input type="image" src="submit.png" alt="Submit">
```

---

## Part 2: Advanced Topics

### Semantic HTML

#### Why Semantic HTML Matters

Semantic HTML uses meaningful tags that describe their content, rather than generic `<div>` and `<span>` elements.

**Benefits:**
1. **Accessibility** - Screen readers understand the page structure
2. **SEO** - Search engines better understand your content
3. **Maintainability** - Code is easier to read and maintain
4. **Consistency** - Standard structure across websites

**Non-Semantic vs Semantic:**
```html
<!-- Non-semantic (avoid this) -->
<div class="header">
    <div class="nav">...</div>
</div>
<div class="main-content">...</div>
<div class="footer">...</div>

<!-- Semantic (use this!) -->
<header>
    <nav>...</nav>
</header>
<main>...</main>
<footer>...</footer>
```

#### Semantic Tags

```html
<header>
    <!-- Introductory content, usually contains nav, logo, search -->
    <nav>
        <!-- Navigation links -->
        <ul>
            <li><a href="/">Home</a></li>
            <li><a href="/about">About</a></li>
        </ul>
    </nav>
</header>

<main>
    <!-- Main content of the page (only one per page) -->
    
    <article>
        <!-- Self-contained content (blog post, news article) -->
        <h2>Article Title</h2>
        <p>Article content...</p>
    </article>
    
    <section>
        <!-- Thematic grouping of content -->
        <h2>Section Title</h2>
        <p>Section content...</p>
    </section>
    
    <aside>
        <!-- Sidebar content, related but not essential -->
        <h3>Related Posts</h3>
    </aside>
</main>

<footer>
    <!-- Footer content: copyright, links, contact info -->
    <p>&copy; 2025 My Website</p>
</footer>
```

**Other Semantic Elements:**
- `<figure>` / `<figcaption>` - Image with caption
- `<time>` - Date/time content
- `<mark>` - Highlighted text
- `<address>` - Contact information
- `<details>` / `<summary>` - Collapsible content

#### Accessibility Benefits

Semantic HTML significantly improves accessibility:

```html
<!-- Screen readers announce this as a navigation region -->
<nav aria-label="Main navigation">
    <ul>
        <li><a href="/">Home</a></li>
    </ul>
</nav>

<!-- Figure with proper caption -->
<figure>
    <img src="chart.png" alt="Sales chart showing 50% growth">
    <figcaption>Figure 1: Quarterly sales data</figcaption>
</figure>

<!-- Time that machines can understand -->
<time datetime="2025-12-31">December 31, 2025</time>
```

### HTML5 Features

#### Audio and Video Elements

```html
<!-- Audio -->
<audio controls>
    <source src="audio.mp3" type="audio/mpeg">
    <source src="audio.ogg" type="audio/ogg">
    Your browser doesn't support audio.
</audio>

<!-- Audio with attributes -->
<audio controls autoplay loop muted preload="auto">
    <source src="music.mp3" type="audio/mpeg">
</audio>

<!-- Video -->
<video controls width="640" height="360">
    <source src="video.mp4" type="video/mp4">
    <source src="video.webm" type="video/webm">
    Your browser doesn't support video.
</video>

<!-- Video with poster image -->
<video controls poster="thumbnail.jpg">
    <source src="video.mp4" type="video/mp4">
</video>

<!-- Video with subtitles -->
<video controls>
    <source src="video.mp4" type="video/mp4">
    <track src="subtitles.vtt" kind="subtitles" srclang="en" label="English">
</video>
```

**Common Attributes:**
| Attribute | Purpose |
|-----------|---------|
| `controls` | Show play/pause buttons |
| `autoplay` | Start playing automatically |
| `loop` | Repeat when finished |
| `muted` | Start muted |
| `poster` | Image shown before playing (video) |
| `preload` | How much to preload (none, metadata, auto) |

#### Canvas and SVG

**Canvas** - For drawing graphics with JavaScript:
```html
<canvas id="myCanvas" width="400" height="300">
    Your browser doesn't support canvas.
</canvas>

<script>
    const canvas = document.getElementById('myCanvas');
    const ctx = canvas.getContext('2d');
    ctx.fillStyle = 'blue';
    ctx.fillRect(10, 10, 100, 50);
</script>
```

**SVG** - Scalable Vector Graphics (XML-based):
```html
<svg width="100" height="100">
    <circle cx="50" cy="50" r="40" fill="red" />
    <rect x="10" y="10" width="30" height="30" fill="blue" />
</svg>

<!-- External SVG file -->
<img src="icon.svg" alt="Icon">

<!-- Inline SVG (allows CSS/JS manipulation) -->
<svg viewBox="0 0 24 24" class="icon">
    <path d="M12 2L2 7l10 5 10-5-10-5z"/>
</svg>
```

**When to use which:**
- **Canvas**: Games, charts, image editing, real-time graphics
- **SVG**: Icons, logos, illustrations, graphics that need to scale

#### Local Storage and Session Storage

These are JavaScript APIs, but they're part of HTML5:

```html
<script>
// Local Storage - persists even after browser closes
localStorage.setItem('username', 'John');
const user = localStorage.getItem('username');
localStorage.removeItem('username');
localStorage.clear(); // Remove all items

// Session Storage - cleared when tab closes
sessionStorage.setItem('tempData', 'value');
const temp = sessionStorage.getItem('tempData');
</script>
```

**Key Differences:**
| Feature | localStorage | sessionStorage |
|---------|-------------|----------------|
| Persistence | Until manually cleared | Until tab closes |
| Scope | Shared across tabs | Per tab only |
| Size limit | ~5-10 MB | ~5-10 MB |

#### Geolocation API

```html
<script>
if ('geolocation' in navigator) {
    navigator.geolocation.getCurrentPosition(
        (position) => {
            console.log('Latitude:', position.coords.latitude);
            console.log('Longitude:', position.coords.longitude);
        },
        (error) => {
            console.error('Error:', error.message);
        }
    );
}
</script>
```

**Note:** Requires user permission and HTTPS.

### Meta Tags and SEO

#### Essential Meta Tags

```html
<head>
    <!-- Character encoding (always first) -->
    <meta charset="UTF-8">
    
    <!-- Responsive viewport -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <!-- Page description (shows in search results) -->
    <meta name="description" content="Learn web development easily with our guides.">
    
    <!-- Keywords (less important now) -->
    <meta name="keywords" content="HTML, CSS, JavaScript, web development">
    
    <!-- Author -->
    <meta name="author" content="Your Name">
    
    <!-- Prevent search indexing (use carefully) -->
    <meta name="robots" content="noindex, nofollow">
    
    <!-- Page title (crucial for SEO) -->
    <title>Learn Web Development | Your Site Name</title>
    
    <!-- Canonical URL (prevents duplicate content issues) -->
    <link rel="canonical" href="https://yoursite.com/page">
    
    <!-- Favicon -->
    <link rel="icon" type="image/png" href="/favicon.png">
</head>
```

#### Open Graph Tags

Open Graph tags control how your page appears when shared on Facebook, LinkedIn, etc.:

```html
<meta property="og:title" content="Article Title">
<meta property="og:description" content="Brief description of the page.">
<meta property="og:image" content="https://yoursite.com/image.jpg">
<meta property="og:url" content="https://yoursite.com/page">
<meta property="og:type" content="website">
<meta property="og:site_name" content="Your Site Name">
```

**Image Recommendations:**
- Minimum size: 1200 x 630 pixels
- Aspect ratio: 1.91:1
- Format: JPG or PNG

#### Twitter Cards

Control appearance on Twitter/X:

```html
<!-- Summary card -->
<meta name="twitter:card" content="summary">

<!-- Large image card -->
<meta name="twitter:card" content="summary_large_image">

<meta name="twitter:title" content="Article Title">
<meta name="twitter:description" content="Brief description">
<meta name="twitter:image" content="https://yoursite.com/image.jpg">
<meta name="twitter:site" content="@yourusername">
```

### Accessibility (ARIA)

ARIA (Accessible Rich Internet Applications) enhances accessibility for dynamic content.

#### ARIA Roles

Roles define what an element is or does:

```html
<!-- Landmark roles (often already implied by semantic HTML) -->
<div role="banner">Header content</div>
<div role="navigation">Nav links</div>
<div role="main">Main content</div>
<div role="contentinfo">Footer</div>

<!-- Widget roles -->
<div role="button" tabindex="0">Clickable div</div>
<div role="alert">Important message!</div>
<div role="dialog" aria-modal="true">Modal content</div>
<div role="tablist">
    <button role="tab">Tab 1</button>
</div>
```

**Tip:** Prefer semantic HTML over ARIA when possible. `<button>` is better than `<div role="button">`.

#### ARIA Labels and Descriptions

```html
<!-- Label (accessible name) -->
<button aria-label="Close dialog">×</button>

<!-- Labelledby (references another element's text) -->
<h2 id="modal-title">Confirm Action</h2>
<div role="dialog" aria-labelledby="modal-title">...</div>

<!-- Describedby (additional description) -->
<input 
    type="password" 
    aria-describedby="password-help"
>
<p id="password-help">Password must be 8+ characters.</p>

<!-- Live regions (announce changes) -->
<div aria-live="polite">Status updates appear here</div>
<div aria-live="assertive">Urgent announcements</div>

<!-- Hidden from screen readers -->
<span aria-hidden="true">👍</span> Like
```

#### Keyboard Navigation

Ensure all interactive elements are keyboard accessible:

```html
<!-- Focusable elements (automatic) -->
<a href="#">Link</a>
<button>Button</button>
<input type="text">

<!-- Make custom elements focusable -->
<div role="button" tabindex="0" onkeydown="handleKey(event)">
    Custom Button
</div>

<!-- Remove from tab order but keep focusable programmatically -->
<button tabindex="-1">Skip this</button>

<!-- Tab order (avoid unless necessary) -->
<input tabindex="1"> <!-- First -->
<input tabindex="2"> <!-- Second -->
<input tabindex="3"> <!-- Third -->
```

**Best Practices:**
- All interactive elements should be focusable
- Visible focus indicators (don't remove `outline` in CSS)
- Logical tab order (follows visual layout)
- Support Enter/Space for buttons

### Performance Optimization

#### Lazy Loading Images

```html
<!-- Native lazy loading (modern browsers) -->
<img src="photo.jpg" alt="Description" loading="lazy">

<!-- Eager loading (for above-the-fold images) -->
<img src="hero.jpg" alt="Hero image" loading="eager">

<!-- Lazy loading with dimensions (prevents layout shift) -->
<img 
    src="photo.jpg" 
    alt="Description" 
    loading="lazy"
    width="800"
    height="600"
>

<!-- Lazy load iframes too -->
<iframe src="video.html" loading="lazy"></iframe>
```

#### Preloading Resources

```html
<head>
    <!-- Preload critical resources -->
    <link rel="preload" href="critical.css" as="style">
    <link rel="preload" href="hero.jpg" as="image">
    <link rel="preload" href="font.woff2" as="font" crossorigin>
    
    <!-- Prefetch (for next page) -->
    <link rel="prefetch" href="/next-page.html">
    
    <!-- Preconnect to external domains -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="dns-prefetch" href="https://analytics.example.com">
</head>
```

**When to use:**
- `preload` - Resources needed immediately for current page
- `prefetch` - Resources likely needed for next navigation
- `preconnect` - Establish early connection to important domains

#### Minimizing HTML Size

1. **Remove unnecessary whitespace** (build tools do this automatically)
2. **Use semantic HTML** (less `<div>` nesting)
3. **Remove comments in production**
4. **Use short but meaningful class names**
5. **Avoid inline styles** (use external CSS)

```html
<!-- Avoid deep nesting -->
<!-- Bad -->
<div class="wrapper">
    <div class="container">
        <div class="content">
            <p>Text</p>
        </div>
    </div>
</div>

<!-- Better -->
<main class="content">
    <p>Text</p>
</main>
```

---

## Part 3: Best Practices & Tips

### Code Organization

- **Consistent indentation** - Use 2 or 4 spaces consistently
- **Logical ordering** - Head elements, then body content in reading order
- **Group related elements** - Keep related code together
- **Comment sections** - Use comments to mark major sections

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <!-- Meta tags -->
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <!-- SEO -->
    <title>Page Title</title>
    <meta name="description" content="Description">
    
    <!-- Styles -->
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <!-- Header -->
    <header>...</header>
    
    <!-- Main content -->
    <main>...</main>
    
    <!-- Footer -->
    <footer>...</footer>
    
    <!-- Scripts (at end of body) -->
    <script src="app.js"></script>
</body>
</html>
```

### Naming Conventions

**IDs and Classes:**
- Use lowercase letters
- Use hyphens to separate words: `main-navigation`
- Be descriptive but concise
- IDs should be unique; classes can be reused

```html
<!-- Good naming -->
<nav class="main-nav">
<div class="card-container">
<button class="btn btn-primary">

<!-- Avoid -->
<nav class="Nav1">
<div class="container2">
<button class="blue">
```

**Common conventions:**
- **BEM (Block Element Modifier)**: `block__element--modifier`
- **Utility classes**: `text-center`, `mt-4`

### Cross-Browser Compatibility

1. **Use standard HTML5** - Avoid deprecated elements
2. **Test in multiple browsers** - Chrome, Firefox, Safari, Edge
3. **Use feature detection** - Don't assume features exist
4. **Include fallbacks** - Provide alternatives for unsupported features

```html
<!-- Provide multiple video formats -->
<video controls>
    <source src="video.mp4" type="video/mp4">
    <source src="video.webm" type="video/webm">
    <p>Your browser doesn't support video. <a href="video.mp4">Download it</a>.</p>
</video>

<!-- Picture element for responsive images -->
<picture>
    <source srcset="image.webp" type="image/webp">
    <source srcset="image.jpg" type="image/jpeg">
    <img src="image.jpg" alt="Description">
</picture>
```

### Responsive HTML

```html
<!-- Responsive images -->
<img 
    src="small.jpg"
    srcset="small.jpg 480w, medium.jpg 800w, large.jpg 1200w"
    sizes="(max-width: 600px) 480px, (max-width: 1000px) 800px, 1200px"
    alt="Responsive image"
>

<!-- Picture element for art direction -->
<picture>
    <source media="(min-width: 800px)" srcset="desktop.jpg">
    <source media="(min-width: 400px)" srcset="tablet.jpg">
    <img src="mobile.jpg" alt="Description">
</picture>

<!-- Responsive video embed -->
<div style="position: relative; padding-bottom: 56.25%; height: 0;">
    <iframe 
        src="https://youtube.com/embed/VIDEO_ID"
        style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"
        allowfullscreen>
    </iframe>
</div>
```

### Common Mistakes to Avoid

1. **Missing `alt` attributes on images**
   ```html
   <!-- Bad --> <img src="photo.jpg">
   <!-- Good --> <img src="photo.jpg" alt="Team photo at conference">
   ```

2. **Using `<br>` for spacing**
   ```html
   <!-- Bad --> Text<br><br><br>More text
   <!-- Good --> Use CSS margin/padding instead
   ```

3. **Skipping heading levels**
   ```html
   <!-- Bad --> <h1>Title</h1> <h4>Section</h4>
   <!-- Good --> <h1>Title</h1> <h2>Section</h2>
   ```

4. **Not closing tags properly**
   ```html
   <!-- Bad --> <p>Paragraph<p>Another
   <!-- Good --> <p>Paragraph</p><p>Another</p>
   ```

5. **Using deprecated elements**
   ```html
   <!-- Bad --> <center>, <font>, <marquee>
   <!-- Good --> Use CSS for styling
   ```

6. **Missing viewport meta tag** (page won't be responsive)

7. **Not using labels with form inputs**
   ```html
   <!-- Bad --> <input type="text" placeholder="Name">
   <!-- Good --> <label for="name">Name:</label><input id="name" type="text">
   ```

### Tools and Validators

- **[W3C Markup Validator](https://validator.w3.org/)** - Check HTML validity
- **[WAVE](https://wave.webaim.org/)** - Accessibility checker
- **[Lighthouse](https://developers.google.com/web/tools/lighthouse)** - Performance & accessibility
- **Browser DevTools** - Inspect and debug HTML
- **[Can I Use](https://caniuse.com/)** - Check browser support
- **[HTML5 Outliner](https://gsnedders.html5.org/outliner/)** - Check document outline

### Resources and Further Learning

**Documentation:**
- [MDN Web Docs - HTML](https://developer.mozilla.org/en-US/docs/Web/HTML)
- [W3Schools HTML Tutorial](https://www.w3schools.com/html/)
- [HTML Living Standard](https://html.spec.whatwg.org/)

**Interactive Learning:**
- [freeCodeCamp](https://www.freecodecamp.org/)
- [Codecademy HTML Course](https://www.codecademy.com/learn/learn-html)
- [Frontend Mentor](https://www.frontendmentor.io/)

**Accessibility:**
- [WebAIM](https://webaim.org/)
- [A11y Project](https://www.a11yproject.com/)
- [WCAG Guidelines](https://www.w3.org/WAI/standards-guidelines/wcag/)
