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

HTML (HyperText Markup Language) is the standard markup language for creating web pages. It's the backbone of every website you visit, providing structure and meaning to web content. HTML uses "markup" to annotate text, images, and other content for display in a web browser.

**Key Concepts:**
- HTML is not a programming language—it's a markup language that defines the structure of your content
- HTML consists of elements that tell the browser how to display content
- Modern HTML (HTML5) includes semantic elements that improve accessibility and SEO
- HTML works alongside CSS (for styling) and JavaScript (for functionality)

**Why Learn HTML?**
- Foundation of web development
- Required for any web-based career
- Easy to learn and immediately useful
- Enables you to create and understand web content

### Setting Up Your Environment

To start writing HTML, you need minimal setup:

**Text Editor Options:**
- **VS Code** (Recommended): Free, powerful, with great HTML support
- **Sublime Text**: Lightweight and fast
- **Atom**: Open-source and customizable
- **Notepad++**: Simple Windows option

**Browser for Testing:**
- Chrome (with DevTools)
- Firefox (with Developer Edition)
- Safari (for Mac users)
- Edge (Chromium-based)

**Basic Setup Steps:**
1. Install a text editor
2. Create a folder for your projects
3. Create an HTML file (e.g., `index.html`)
4. Open it in your browser to see results

**Useful Extensions (for VS Code):**
- Live Server: Auto-refresh browser on save
- HTML Snippets: Quick HTML code templates
- Auto Rename Tag: Sync HTML tag edits
- Prettier: Code formatting

### HTML Document Structure

Every HTML document follows a standard structure:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My First Web Page</title>
</head>
<body>
    <h1>Welcome to My Website</h1>
    <p>This is my first paragraph.</p>
</body>
</html>
```

**Breaking It Down:**

- `<!DOCTYPE html>`: Declares this is an HTML5 document
- `<html>`: Root element that wraps all content
- `<head>`: Contains metadata (not visible on page)
- `<meta charset="UTF-8">`: Sets character encoding
- `<meta name="viewport">`: Makes page responsive on mobile
- `<title>`: Appears in browser tab
- `<body>`: Contains all visible content

**Important Notes:**
- Always include DOCTYPE
- Set language with `lang` attribute
- Include viewport meta tag for mobile responsiveness
- Use proper indentation for readability

### Essential HTML Tags

#### Headings and Paragraphs

**Headings** (`<h1>` to `<h6>`):
```html
<h1>Main Heading</h1>
<h2>Subheading</h2>
<h3>Sub-subheading</h3>
<h4>Fourth Level</h4>
<h5>Fifth Level</h5>
<h6>Sixth Level</h6>
```

- `<h1>` is most important (typically one per page)
- Use headings hierarchically
- Don't skip levels (don't jump from h1 to h3)
- Headings help SEO and accessibility

**Paragraphs** (`<p>`):
```html
<p>This is a paragraph of text. It will automatically wrap based on the browser width.</p>
<p>Each paragraph tag creates a new block of text with spacing.</p>
```

**Text Formatting:**
```html
<strong>Bold text (important)</strong>
<b>Bold text (stylistic)</b>
<em>Italic text (emphasis)</em>
<i>Italic text (stylistic)</i>
<mark>Highlighted text</mark>
<small>Smaller text</small>
<del>Deleted text</del>
<ins>Inserted text</ins>
<sub>Subscript</sub>
<sup>Superscript</sup>
```

#### Links and Images

**Links** (`<a>`):
```html
<!-- External link -->
<a href="https://www.example.com">Visit Example</a>

<!-- Internal link -->
<a href="/about.html">About Page</a>

<!-- Link to section -->
<a href="#contact">Jump to Contact</a>

<!-- Open in new tab -->
<a href="https://www.example.com" target="_blank" rel="noopener noreferrer">External Site</a>

<!-- Email link -->
<a href="mailto:info@example.com">Email Us</a>

<!-- Phone link -->
<a href="tel:+1234567890">Call Us</a>
```

**Images** (`<img>`):
```html
<!-- Basic image -->
<img src="image.jpg" alt="Description of image">

<!-- Image with size -->
<img src="photo.jpg" alt="Photo" width="500" height="300">

<!-- Responsive image -->
<img src="image.jpg" alt="Description" style="max-width: 100%; height: auto;">
```

**Image Best Practices:**
- Always include `alt` text for accessibility
- Use descriptive filenames
- Optimize image size for web
- Consider using WebP format for better compression

#### Lists (Ordered & Unordered)

**Unordered Lists** (bullet points):
```html
<ul>
    <li>First item</li>
    <li>Second item</li>
    <li>Third item</li>
</ul>
```

**Ordered Lists** (numbered):
```html
<ol>
    <li>Step one</li>
    <li>Step two</li>
    <li>Step three</li>
</ol>
```

**Nested Lists:**
```html
<ul>
    <li>Main item
        <ul>
            <li>Sub-item 1</li>
            <li>Sub-item 2</li>
        </ul>
    </li>
    <li>Another main item</li>
</ul>
```

**Description Lists:**
```html
<dl>
    <dt>Term</dt>
    <dd>Definition of the term</dd>
    <dt>Another term</dt>
    <dd>Its definition</dd>
</dl>
```

#### Tables

**Basic Table Structure:**
```html
<table>
    <thead>
        <tr>
            <th>Header 1</th>
            <th>Header 2</th>
            <th>Header 3</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Row 1, Cell 1</td>
            <td>Row 1, Cell 2</td>
            <td>Row 1, Cell 3</td>
        </tr>
        <tr>
            <td>Row 2, Cell 1</td>
            <td>Row 2, Cell 2</td>
            <td>Row 2, Cell 3</td>
        </tr>
    </tbody>
</table>
```

**Table with Caption:**
```html
<table>
    <caption>Monthly Sales Report</caption>
    <thead>
        <tr>
            <th>Month</th>
            <th>Sales</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>January</td>
            <td>$10,000</td>
        </tr>
    </tbody>
</table>
```

**Spanning Cells:**
```html
<table>
    <tr>
        <td colspan="2">Spans 2 columns</td>
    </tr>
    <tr>
        <td rowspan="2">Spans 2 rows</td>
        <td>Normal cell</td>
    </tr>
</table>
```

### HTML Attributes

Attributes provide additional information about HTML elements:

**Common Global Attributes:**

```html
<!-- id: Unique identifier -->
<div id="header">Header content</div>

<!-- class: Classification for styling -->
<p class="highlight important">Text</p>

<!-- style: Inline CSS -->
<span style="color: red;">Red text</span>

<!-- title: Tooltip text -->
<abbr title="HyperText Markup Language">HTML</abbr>

<!-- data-*: Custom data attributes -->
<div data-user-id="123" data-role="admin">User info</div>

<!-- hidden: Hide element -->
<p hidden>This won't display</p>

<!-- contenteditable: Make editable -->
<div contenteditable="true">Edit this text</div>

<!-- draggable: Enable drag/drop -->
<img src="image.jpg" draggable="true" alt="Draggable">
```

**Link-Specific Attributes:**
```html
<a href="url" target="_blank" rel="noopener" download>Link</a>
```

**Image Attributes:**
```html
<img src="image.jpg" alt="Description" width="500" height="300" loading="lazy">
```

### Block vs Inline Elements

**Block Elements:**
- Take up full width available
- Start on a new line
- Can contain other block and inline elements

Examples:
```html
<div>Division (generic container)</div>
<p>Paragraph</p>
<h1>Heading</h1>
<ul><li>List</li></ul>
<section>Section</section>
<article>Article</article>
<header>Header</header>
<footer>Footer</footer>
```

**Inline Elements:**
- Take up only necessary width
- Don't start on new line
- Can only contain other inline elements

Examples:
```html
<span>Span (generic inline)</span>
<a href="#">Link</a>
<strong>Bold</strong>
<em>Italic</em>
<img src="pic.jpg" alt="Image">
<code>Code snippet</code>
```

**Visual Difference:**
```html
<!-- Block elements stack vertically -->
<div>First div</div>
<div>Second div</div>
<!-- Result: Two boxes stacked -->

<!-- Inline elements flow horizontally -->
<span>First span</span>
<span>Second span</span>
<!-- Result: Text flows on same line -->
```

### HTML Forms Basics

Forms collect user input:

**Basic Form Structure:**
```html
<form action="/submit" method="POST">
    <label for="name">Name:</label>
    <input type="text" id="name" name="name" required>
    
    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required>
    
    <button type="submit">Submit</button>
</form>
```

#### Input Types

**Text Inputs:**
```html
<!-- Basic text -->
<input type="text" name="username" placeholder="Enter username">

<!-- Email (with validation) -->
<input type="email" name="email" placeholder="email@example.com">

<!-- Password (hidden characters) -->
<input type="password" name="password">

<!-- Number -->
<input type="number" name="age" min="0" max="120">

<!-- Tel (telephone) -->
<input type="tel" name="phone" pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}">

<!-- URL -->
<input type="url" name="website" placeholder="https://example.com">

<!-- Search -->
<input type="search" name="query">

<!-- Date -->
<input type="date" name="birthday">

<!-- Time -->
<input type="time" name="appointment">

<!-- Color picker -->
<input type="color" name="favcolor">

<!-- File upload -->
<input type="file" name="document" accept=".pdf,.doc">

<!-- Range slider -->
<input type="range" name="volume" min="0" max="100">
```

**Selection Inputs:**
```html
<!-- Radio buttons (single choice) -->
<input type="radio" id="male" name="gender" value="male">
<label for="male">Male</label>
<input type="radio" id="female" name="gender" value="female">
<label for="female">Female</label>

<!-- Checkboxes (multiple choice) -->
<input type="checkbox" id="subscribe" name="subscribe" value="yes">
<label for="subscribe">Subscribe to newsletter</label>

<!-- Dropdown select -->
<select name="country">
    <option value="">Select country</option>
    <option value="us">United States</option>
    <option value="uk">United Kingdom</option>
    <option value="ca">Canada</option>
</select>

<!-- Multi-select -->
<select name="interests" multiple>
    <option value="sports">Sports</option>
    <option value="music">Music</option>
    <option value="art">Art</option>
</select>

<!-- Textarea (multi-line) -->
<textarea name="message" rows="4" cols="50" placeholder="Your message"></textarea>
```

#### Form Validation

**HTML5 Validation Attributes:**
```html
<!-- Required field -->
<input type="text" name="username" required>

<!-- Minimum/Maximum length -->
<input type="text" name="password" minlength="8" maxlength="20" required>

<!-- Pattern matching -->
<input type="text" name="zipcode" pattern="[0-9]{5}" title="5-digit zip code">

<!-- Min/Max values (numbers) -->
<input type="number" name="age" min="18" max="100">

<!-- Email validation (automatic) -->
<input type="email" name="email" required>

<!-- URL validation (automatic) -->
<input type="url" name="website">
```

**Complete Form Example:**
```html
<form action="/register" method="POST" novalidate>
    <fieldset>
        <legend>User Registration</legend>
        
        <label for="username">Username *</label>
        <input type="text" id="username" name="username" required minlength="3">
        
        <label for="email">Email *</label>
        <input type="email" id="email" name="email" required>
        
        <label for="password">Password *</label>
        <input type="password" id="password" name="password" required minlength="8">
        
        <label for="age">Age</label>
        <input type="number" id="age" name="age" min="13" max="120">
        
        <label>
            <input type="checkbox" name="terms" required>
            I agree to terms and conditions *
        </label>
        
        <button type="submit">Register</button>
        <button type="reset">Clear Form</button>
    </fieldset>
</form>
```

#### Buttons and Submissions

**Button Types:**
```html
<!-- Submit button (submits form) -->
<button type="submit">Submit Form</button>

<!-- Reset button (clears form) -->
<button type="reset">Reset Form</button>

<!-- Regular button (no default action) -->
<button type="button" onclick="alert('Clicked')">Click Me</button>

<!-- Image button -->
<input type="image" src="submit.png" alt="Submit">

<!-- Disabled button -->
<button type="submit" disabled>Can't Click</button>
```

---

## Part 2: Advanced Topics

### Semantic HTML

#### Why Semantic HTML Matters

Semantic HTML uses elements that clearly describe their meaning to both browsers and developers:

**Benefits:**
- **Accessibility**: Screen readers can navigate better
- **SEO**: Search engines understand content structure
- **Maintainability**: Code is easier to read and update
- **Consistency**: Standard meaning across all browsers

**Non-Semantic vs Semantic:**
```html
<!-- Non-semantic (unclear purpose) -->
<div id="header">
    <div class="nav">
        <div class="nav-item">Home</div>
    </div>
</div>

<!-- Semantic (clear purpose) -->
<header>
    <nav>
        <a href="/">Home</a>
    </nav>
</header>
```

#### Semantic Tags

**Page Structure Elements:**

```html
<!-- Header: Top section of page/section -->
<header>
    <h1>Website Title</h1>
    <nav>
        <a href="/">Home</a>
        <a href="/about">About</a>
    </nav>
</header>

<!-- Nav: Navigation links -->
<nav>
    <ul>
        <li><a href="/">Home</a></li>
        <li><a href="/products">Products</a></li>
        <li><a href="/contact">Contact</a></li>
    </ul>
</nav>

<!-- Main: Primary content (one per page) -->
<main>
    <h1>Welcome</h1>
    <p>Main content goes here</p>
</main>

<!-- Article: Self-contained content -->
<article>
    <h2>Blog Post Title</h2>
    <p>Post content...</p>
    <footer>Published on <time datetime="2024-01-01">January 1, 2024</time></footer>
</article>

<!-- Section: Thematic grouping -->
<section>
    <h2>About Us</h2>
    <p>Company information...</p>
</section>

<!-- Aside: Tangentially related content -->
<aside>
    <h3>Related Links</h3>
    <ul>
        <li><a href="#">Resource 1</a></li>
    </ul>
</aside>

<!-- Footer: Bottom section -->
<footer>
    <p>&copy; 2024 Company Name</p>
    <address>
        Contact: <a href="mailto:info@example.com">info@example.com</a>
    </address>
</footer>
```

**Complete Page Example:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Semantic HTML Example</title>
</head>
<body>
    <header>
        <h1>My Blog</h1>
        <nav>
            <a href="/">Home</a>
            <a href="/archive">Archive</a>
        </nav>
    </header>
    
    <main>
        <article>
            <header>
                <h2>Article Title</h2>
                <p>By <span>Author Name</span> on <time>Jan 1, 2024</time></p>
            </header>
            <section>
                <h3>Introduction</h3>
                <p>Article content...</p>
            </section>
            <section>
                <h3>Main Points</h3>
                <p>More content...</p>
            </section>
        </article>
        
        <aside>
            <h3>Related Posts</h3>
            <ul>
                <li><a href="#">Post 1</a></li>
                <li><a href="#">Post 2</a></li>
            </ul>
        </aside>
    </main>
    
    <footer>
        <p>&copy; 2024 My Blog</p>
    </footer>
</body>
</html>
```

#### Accessibility Benefits

Semantic HTML dramatically improves accessibility:

**Key Benefits:**
- Screen readers can identify page regions
- Keyboard navigation works better
- Content structure is logical
- Skip navigation becomes possible

**Other Semantic Elements:**
```html
<!-- Figure with caption -->
<figure>
    <img src="chart.jpg" alt="Sales chart">
    <figcaption>Q4 Sales Performance</figcaption>
</figure>

<!-- Time/Date -->
<p>Published <time datetime="2024-01-15T10:00">January 15, 2024 at 10am</time></p>

<!-- Mark (highlight) -->
<p>Search results for <mark>HTML</mark></p>

<!-- Details/Summary (collapsible) -->
<details>
    <summary>Click to expand</summary>
    <p>Hidden content here</p>
</details>

<!-- Progress -->
<progress value="70" max="100">70%</progress>

<!-- Meter -->
<meter value="0.6" min="0" max="1">60%</meter>
```

### HTML5 Features

#### Audio and Video Elements

**Audio Element:**
```html
<audio controls>
    <source src="audio.mp3" type="audio/mpeg">
    <source src="audio.ogg" type="audio/ogg">
    Your browser doesn't support audio.
</audio>

<!-- With autoplay and loop -->
<audio controls autoplay loop muted>
    <source src="music.mp3" type="audio/mpeg">
</audio>
```

**Video Element:**
```html
<video controls width="640" height="360">
    <source src="video.mp4" type="video/mp4">
    <source src="video.webm" type="video/webm">
    <track src="subtitles.vtt" kind="subtitles" srclang="en" label="English">
    Your browser doesn't support video.
</video>

<!-- With poster image -->
<video controls poster="thumbnail.jpg" width="100%">
    <source src="video.mp4" type="video/mp4">
</video>
```

**Attributes:**
- `controls`: Show play/pause controls
- `autoplay`: Start automatically (often blocked by browsers)
- `loop`: Repeat continuously
- `muted`: Start muted
- `preload`: How to load (`auto`, `metadata`, `none`)

#### Canvas and SVG

**Canvas** (Raster Graphics):
```html
<canvas id="myCanvas" width="500" height="300"></canvas>
<script>
    const canvas = document.getElementById('myCanvas');
    const ctx = canvas.getContext('2d');
    
    // Draw rectangle
    ctx.fillStyle = 'blue';
    ctx.fillRect(50, 50, 200, 100);
    
    // Draw circle
    ctx.beginPath();
    ctx.arc(300, 150, 50, 0, 2 * Math.PI);
    ctx.fillStyle = 'red';
    ctx.fill();
</script>
```

**SVG** (Vector Graphics):
```html
<svg width="500" height="300">
    <!-- Rectangle -->
    <rect x="50" y="50" width="200" height="100" fill="blue"/>
    
    <!-- Circle -->
    <circle cx="300" cy="150" r="50" fill="red"/>
    
    <!-- Line -->
    <line x1="0" y1="0" x2="500" y2="300" stroke="black" stroke-width="2"/>
    
    <!-- Text -->
    <text x="250" y="150" font-size="20" fill="white">SVG Text</text>
</svg>
```

**When to Use:**
- **Canvas**: Dynamic graphics, games, image manipulation
- **SVG**: Logos, icons, charts, scalable graphics

#### Local Storage and Session Storage

**Local Storage** (persists after browser close):
```html
<script>
    // Store data
    localStorage.setItem('username', 'JohnDoe');
    localStorage.setItem('theme', 'dark');
    
    // Retrieve data
    const username = localStorage.getItem('username');
    console.log(username); // 'JohnDoe'
    
    // Remove item
    localStorage.removeItem('theme');
    
    // Clear all
    localStorage.clear();
    
    // Store objects (must stringify)
    const user = {name: 'John', age: 30};
    localStorage.setItem('user', JSON.stringify(user));
    const storedUser = JSON.parse(localStorage.getItem('user'));
</script>
```

**Session Storage** (clears when tab closes):
```html
<script>
    // Same API as localStorage
    sessionStorage.setItem('tempData', 'value');
    const temp = sessionStorage.getItem('tempData');
    sessionStorage.removeItem('tempData');
    sessionStorage.clear();
</script>
```

**Practical Example:**
```html
<script>
    // Save form data as user types
    document.getElementById('myForm').addEventListener('input', (e) => {
        localStorage.setItem(e.target.name, e.target.value);
    });
    
    // Restore form data on page load
    window.addEventListener('load', () => {
        document.querySelectorAll('input').forEach(input => {
            const saved = localStorage.getItem(input.name);
            if (saved) input.value = saved;
        });
    });
</script>
```

#### Geolocation API

```html
<button onclick="getLocation()">Get My Location</button>
<p id="location"></p>

<script>
    function getLocation() {
        if (navigator.geolocation) {
            navigator.geolocation.getCurrentPosition(showPosition, showError);
        } else {
            document.getElementById('location').textContent = 
                'Geolocation not supported';
        }
    }
    
    function showPosition(position) {
        const lat = position.coords.latitude;
        const lon = position.coords.longitude;
        document.getElementById('location').textContent = 
            `Latitude: ${lat}, Longitude: ${lon}`;
    }
    
    function showError(error) {
        const messages = {
            1: 'Permission denied',
            2: 'Position unavailable',
            3: 'Timeout'
        };
        document.getElementById('location').textContent = 
            messages[error.code];
    }
    
    // Watch position (continuous updates)
    const watchId = navigator.geolocation.watchPosition(showPosition);
    // Stop watching: navigator.geolocation.clearWatch(watchId);
</script>
```

### Meta Tags and SEO

#### Essential Meta Tags

```html
<head>
    <!-- Character encoding -->
    <meta charset="UTF-8">
    
    <!-- Viewport for responsive design -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <!-- Page description (SEO) -->
    <meta name="description" content="Learn web development easily with comprehensive tutorials on HTML, CSS, JavaScript and more.">
    
    <!-- Keywords (less important now) -->
    <meta name="keywords" content="web development, HTML, CSS, JavaScript, tutorial">
    
    <!-- Author -->
    <meta name="author" content="Your Name">
    
    <!-- Robots (search engine instructions) -->
    <meta name="robots" content="index, follow">
    
    <!-- Refresh/redirect -->
    <meta http-equiv="refresh" content="30">
    
    <!-- Theme color (mobile browsers) -->
    <meta name="theme-color" content="#4285f4">
    
    <!-- Page title -->
    <title>Your Page Title - Keep it under 60 characters</title>
    
    <!-- Favicon -->
    <link rel="icon" href="/favicon.ico">
    <link rel="apple-touch-icon" href="/apple-touch-icon.png">
</head>
```

#### Open Graph Tags

Used by Facebook, LinkedIn, and other social platforms:

```html
<head>
    <!-- Basic Open Graph -->
    <meta property="og:title" content="Your Page Title">
    <meta property="og:description" content="Description of your page">
    <meta property="og:image" content="https://example.com/image.jpg">
    <meta property="og:url" content="https://example.com/page">
    <meta property="og:type" content="website">
    <meta property="og:site_name" content="Your Site Name">
    
    <!-- Optional -->
    <meta property="og:locale" content="en_US">
    <meta property="og:video" content="https://example.com/video.mp4">
    
    <!-- For articles -->
    <meta property="article:published_time" content="2024-01-01T10:00:00Z">
    <meta property="article:author" content="Author Name">
    <meta property="article:section" content="Technology">
    <meta property="article:tag" content="HTML, Web Development">
</head>
```

#### Twitter Cards

```html
<head>
    <!-- Twitter Card -->
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:site" content="@yourusername">
    <meta name="twitter:creator" content="@authorusername">
    <meta name="twitter:title" content="Your Page Title">
    <meta name="twitter:description" content="Page description">
    <meta name="twitter:image" content="https://example.com/image.jpg">
    
    <!-- Card types: summary, summary_large_image, app, player -->
</head>
```

**Complete SEO-Optimized Head:**
```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <title>Web Development Made Easy | Learn HTML, CSS, JavaScript</title>
    <meta name="description" content="Comprehensive web development tutorials covering HTML, CSS, JavaScript, and Figma. From fundamentals to advanced techniques.">
    
    <!-- Open Graph -->
    <meta property="og:title" content="Web Development Made Easy">
    <meta property="og:description" content="Learn web development with easy-to-follow tutorials">
    <meta property="og:image" content="https://example.com/share-image.jpg">
    <meta property="og:url" content="https://example.com">
    
    <!-- Twitter -->
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:title" content="Web Development Made Easy">
    <meta name="twitter:description" content="Learn web development">
    <meta name="twitter:image" content="https://example.com/share-image.jpg">
    
    <!-- Favicon -->
    <link rel="icon" href="/favicon.ico">
    
    <!-- Canonical URL -->
    <link rel="canonical" href="https://example.com/page">
</head>
```

### Accessibility (ARIA)

ARIA (Accessible Rich Internet Applications) makes web content more accessible:

#### ARIA Roles

```html
<!-- Landmark roles -->
<div role="banner">Site header</div>
<div role="navigation">Menu</div>
<div role="main">Main content</div>
<div role="complementary">Sidebar</div>
<div role="contentinfo">Footer</div>
<div role="search">Search form</div>

<!-- Widget roles -->
<div role="button" tabindex="0">Clickable div</div>
<div role="tab">Tab item</div>
<div role="tabpanel">Tab content</div>
<div role="dialog">Modal dialog</div>
<div role="alert">Alert message</div>
<div role="tooltip">Tooltip</div>

<!-- Use semantic HTML instead when possible -->
<button>Better than role="button"</button>
<nav>Better than role="navigation"</nav>
```

#### ARIA Labels and Descriptions

```html
<!-- aria-label: Accessible name -->
<button aria-label="Close dialog">×</button>
<div aria-label="Progress indicator" role="progressbar"></div>

<!-- aria-labelledby: Reference another element -->
<h2 id="dialog-title">Confirmation</h2>
<div role="dialog" aria-labelledby="dialog-title">
    <p>Are you sure?</p>
</div>

<!-- aria-describedby: Additional description -->
<input type="password" 
       aria-describedby="password-hint">
<span id="password-hint">
    Must be at least 8 characters
</span>

<!-- aria-hidden: Hide from screen readers -->
<span aria-hidden="true">★</span>
<span class="sr-only">Rating: 4 out of 5</span>

<!-- aria-live: Announce dynamic changes -->
<div aria-live="polite">Status message will be announced</div>
<div aria-live="assertive">Urgent notification</div>

<!-- aria-expanded: For collapsible content -->
<button aria-expanded="false" aria-controls="menu">
    Menu
</button>
<ul id="menu" hidden>
    <li>Item 1</li>
</ul>

<!-- aria-pressed: For toggle buttons -->
<button aria-pressed="false">Toggle</button>

<!-- aria-required: For required fields -->
<input type="text" aria-required="true">

<!-- aria-invalid: For validation errors -->
<input type="email" aria-invalid="true" aria-describedby="email-error">
<span id="email-error">Please enter a valid email</span>
```

#### Keyboard Navigation

Make interactive elements keyboard accessible:

```html
<!-- Tabindex values -->
<!-- tabindex="0": Included in natural tab order -->
<div tabindex="0" role="button">Keyboard accessible</div>

<!-- tabindex="-1": Programmatically focusable only -->
<div tabindex="-1">Can be focused via JavaScript</div>

<!-- tabindex="1+" : Avoid! Disrupts natural order -->

<!-- Skip to main content link -->
<a href="#main-content" class="skip-link">Skip to main content</a>
<main id="main-content">
    <!-- Content -->
</main>

<!-- Keyboard event handling -->
<div role="button" 
     tabindex="0"
     onclick="handleClick()"
     onkeydown="handleKeyboard(event)">
    Custom Button
</div>

<script>
function handleKeyboard(event) {
    // Activate on Enter or Space
    if (event.key === 'Enter' || event.key === ' ') {
        event.preventDefault();
        handleClick();
    }
}
</script>

<!-- Focus management -->
<script>
// Move focus to element
document.getElementById('dialog').focus();

// Focus trap for modals
const modal = document.getElementById('modal');
const focusableElements = modal.querySelectorAll(
    'button, [href], input, select, textarea, [tabindex]:not([tabindex="-1"])'
);
const firstElement = focusableElements[0];
const lastElement = focusableElements[focusableElements.length - 1];

modal.addEventListener('keydown', (e) => {
    if (e.key === 'Tab') {
        if (e.shiftKey && document.activeElement === firstElement) {
            e.preventDefault();
            lastElement.focus();
        } else if (!e.shiftKey && document.activeElement === lastElement) {
            e.preventDefault();
            firstElement.focus();
        }
    }
});
</script>
```

### Performance Optimization

#### Lazy Loading Images

```html
<!-- Native lazy loading -->
<img src="image.jpg" alt="Description" loading="lazy">

<!-- Works for iframes too -->
<iframe src="video.html" loading="lazy"></iframe>

<!-- Combine with responsive images -->
<img src="small.jpg"
     srcset="small.jpg 500w,
             medium.jpg 1000w,
             large.jpg 2000w"
     sizes="(max-width: 600px) 100vw,
            (max-width: 1200px) 50vw,
            33vw"
     loading="lazy"
     alt="Responsive image">

<!-- Placeholder technique -->
<img src="tiny-placeholder.jpg"
     data-src="full-image.jpg"
     class="lazy"
     alt="Description">

<script>
// Intersection Observer for lazy loading
const lazyImages = document.querySelectorAll('.lazy');
const imageObserver = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
        if (entry.isIntersecting) {
            const img = entry.target;
            img.src = img.dataset.src;
            img.classList.remove('lazy');
            imageObserver.unobserve(img);
        }
    });
});

lazyImages.forEach(img => imageObserver.observe(img));
</script>
```

#### Preloading Resources

```html
<head>
    <!-- Preload critical resources -->
    <link rel="preload" href="critical.css" as="style">
    <link rel="preload" href="hero-image.jpg" as="image">
    <link rel="preload" href="font.woff2" as="font" type="font/woff2" crossorigin>
    
    <!-- Prefetch resources for next page -->
    <link rel="prefetch" href="next-page.html">
    <link rel="prefetch" href="next-image.jpg">
    
    <!-- DNS prefetch -->
    <link rel="dns-prefetch" href="https://api.example.com">
    
    <!-- Preconnect (DNS + TCP + TLS) -->
    <link rel="preconnect" href="https://cdn.example.com">
    
    <!-- Prerender entire page -->
    <link rel="prerender" href="next-page.html">
</head>
```

**Resource Priorities:**
```html
<!-- High priority -->
<link rel="preload" href="critical.css" as="style" importance="high">

<!-- Low priority -->
<img src="optional.jpg" importance="low" alt="Optional">

<!-- Auto (default) -->
<img src="normal.jpg" importance="auto" alt="Normal">
```

#### Minimizing HTML Size

**Techniques:**

1. **Minification** - Remove whitespace and comments
2. **Compression** - Enable GZIP/Brotli on server
3. **Reduce DOM complexity** - Fewer elements load faster
4. **Inline critical CSS** - Above-the-fold styles in `<head>`
5. **Defer non-critical resources** - Load scripts after content

```html
<!-- Before minification -->
<div class="container">
    <h1>Title</h1>
    <p>
        This is a paragraph with
        multiple lines.
    </p>
</div>

<!-- After minification -->
<div class="container"><h1>Title</h1><p>This is a paragraph with multiple lines.</p></div>

<!-- Defer scripts -->
<script src="non-critical.js" defer></script>

<!-- Async scripts (doesn't block) -->
<script src="analytics.js" async></script>

<!-- Module scripts (automatically deferred) -->
<script type="module" src="app.js"></script>
```

**Inline Critical CSS:**
```html
<head>
    <style>
        /* Critical above-the-fold styles */
        body { margin: 0; font-family: sans-serif; }
        .hero { background: blue; height: 100vh; }
    </style>
    
    <!-- Load full stylesheet asynchronously -->
    <link rel="preload" href="styles.css" as="style" onload="this.onload=null;this.rel='stylesheet'">
    <noscript><link rel="stylesheet" href="styles.css"></noscript>
</head>
```

---

## Part 3: Best Practices & Tips

### Code Organization

**File Structure:**
```
project/
├── index.html
├── about.html
├── contact.html
├── css/
│   ├── main.css
│   └── responsive.css
├── js/
│   ├── main.js
│   └── utils.js
├── images/
│   ├── logo.png
│   └── hero.jpg
└── assets/
    ├── fonts/
    └── icons/
```

**HTML Organization:**
```html
<!-- Use comments to mark sections -->
<!DOCTYPE html>
<html lang="en">
<head>
    <!-- Meta Tags -->
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <!-- Title & Description -->
    <title>Page Title</title>
    
    <!-- Stylesheets -->
    <link rel="stylesheet" href="css/main.css">
</head>
<body>
    <!-- Header -->
    <header>
        <!-- Navigation -->
        <nav>
            <!-- Menu items -->
        </nav>
    </header>
    
    <!-- Main Content -->
    <main>
        <!-- Hero Section -->
        <section class="hero">
        </section>
        
        <!-- Features Section -->
        <section class="features">
        </section>
    </main>
    
    <!-- Footer -->
    <footer>
    </footer>
    
    <!-- Scripts -->
    <script src="js/main.js"></script>
</body>
</html>
```

**Keep It DRY (Don't Repeat Yourself):**
- Use templates or includes for repeated sections
- Create reusable components
- Extract common patterns

### Naming Conventions

**BEM (Block Element Modifier):**
```html
<!-- Block -->
<div class="card">
    <!-- Element -->
    <h2 class="card__title">Title</h2>
    <p class="card__content">Content</p>
    <!-- Modifier -->
    <button class="card__button card__button--primary">Click</button>
</div>
```

**Best Practices:**
- Use lowercase with hyphens: `class="my-class"`
- Be descriptive: `class="user-profile"` not `class="up"`
- Use semantic names: `class="primary-button"` not `class="blue-button"`
- IDs should be unique: `id="main-header"`
- Use data attributes for JS: `data-user-id="123"`

**Bad:**
```html
<div class="BlueBox" id="div1">
    <span class="txt">Text</span>
</div>
```

**Good:**
```html
<div class="info-box info-box--highlighted" id="user-profile">
    <span class="info-box__text">Text</span>
</div>
```

### Cross-Browser Compatibility

**Key Considerations:**

1. **Use Standard HTML5** - Avoid deprecated tags
2. **Test in Multiple Browsers** - Chrome, Firefox, Safari, Edge
3. **Provide Fallbacks** - For unsupported features
4. **Use Polyfills** - For older browsers
5. **Validate Your HTML** - Use W3C Validator

**Vendor Prefixes (mostly in CSS now):**
```html
<!-- No longer needed in HTML5 -->
<!-- HTML5 elements work in all modern browsers -->
```

**Feature Detection:**
```html
<script>
// Check if feature is supported
if ('geolocation' in navigator) {
    // Use geolocation
} else {
    // Provide fallback
}

if (typeof localStorage !== 'undefined') {
    // Use localStorage
} else {
    // Use cookies
}
</script>
```

**Graceful Degradation:**
```html
<!-- Video with fallback -->
<video controls>
    <source src="video.mp4" type="video/mp4">
    <source src="video.webm" type="video/webm">
    <p>Your browser doesn't support video. <a href="video.mp4">Download instead</a>.</p>
</video>

<!-- Canvas with fallback -->
<canvas id="chart">
    <img src="chart-fallback.png" alt="Sales Chart">
</canvas>
```

### Responsive HTML

**Mobile-First Approach:**
```html
<head>
    <!-- Essential viewport meta -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>

<!-- Responsive images -->
<picture>
    <source media="(min-width: 1200px)" srcset="large.jpg">
    <source media="(min-width: 768px)" srcset="medium.jpg">
    <img src="small.jpg" alt="Responsive image">
</picture>

<!-- Srcset for different resolutions -->
<img src="image.jpg"
     srcset="image-1x.jpg 1x,
             image-2x.jpg 2x,
             image-3x.jpg 3x"
     alt="High-DPI image">

<!-- Responsive tables -->
<div class="table-responsive">
    <table>
        <!-- Table content -->
    </table>
</div>
```

**Touch-Friendly Elements:**
```html
<!-- Minimum 44x44px touch target -->
<button style="min-width: 44px; min-height: 44px;">Tap Me</button>

<!-- Telephone links -->
<a href="tel:+1234567890">Call Us</a>

<!-- SMS links -->
<a href="sms:+1234567890">Text Us</a>
```

### Common Mistakes to Avoid

1. **Missing Alt Text on Images**
```html
<!-- Bad -->
<img src="photo.jpg">

<!-- Good -->
<img src="photo.jpg" alt="Team photo from company retreat">
```

2. **Inline Styles (use CSS instead)**
```html
<!-- Bad -->
<p style="color: red; font-size: 20px;">Text</p>

<!-- Good -->
<p class="warning">Text</p>
```

3. **Non-Semantic Markup**
```html
<!-- Bad -->
<div class="header">
    <div class="nav">

<!-- Good -->
<header>
    <nav>
```

4. **Missing Form Labels**
```html
<!-- Bad -->
<input type="text" name="email">

<!-- Good -->
<label for="email">Email:</label>
<input type="text" id="email" name="email">
```

5. **Using Deprecated Tags**
```html
<!-- Bad -->
<center><font color="red">Text</font></center>
<marquee>Scrolling text</marquee>

<!-- Good -->
<p class="centered text-red">Text</p>
```

6. **Not Closing Tags**
```html
<!-- Bad -->
<p>Paragraph 1
<p>Paragraph 2

<!-- Good -->
<p>Paragraph 1</p>
<p>Paragraph 2</p>
```

7. **Incorrect Nesting**
```html
<!-- Bad -->
<b><i>Bold and italic</b></i>

<!-- Good -->
<b><i>Bold and italic</i></b>
```

### Tools and Validators

**HTML Validators:**
- **W3C Markup Validator**: https://validator.w3.org/
- **HTML5 Validator**: https://html5.validator.nu/
- Check for syntax errors and best practices

**Browser DevTools:**
- **Chrome DevTools** (F12)
- **Firefox Developer Tools** (F12)
- Inspect HTML structure
- Debug layout issues
- Test responsive design

**Accessibility Testing:**
- **WAVE**: https://wave.webaim.org/
- **axe DevTools**: Browser extension
- **Lighthouse**: Built into Chrome DevTools
- Test keyboard navigation manually

**Code Editors with HTML Support:**
- **VS Code**: Extensions like HTMLHint, Live Server
- **Sublime Text**: HTML-CSS-JS Prettify
- **WebStorm**: Built-in validation

**Online Tools:**
- **CodePen**: https://codepen.io/ - Test HTML/CSS/JS
- **JSFiddle**: https://jsfiddle.net/ - Share code snippets
- **Can I Use**: https://caniuse.com/ - Browser compatibility

### Resources and Further Learning

**Official Documentation:**
- **MDN Web Docs**: https://developer.mozilla.org/en-US/docs/Web/HTML
- **W3C HTML Spec**: https://html.spec.whatwg.org/
- **W3Schools**: https://www.w3schools.com/html/

**Interactive Learning:**
- **freeCodeCamp**: HTML and CSS certification
- **Codecademy**: HTML course
- **Scrimba**: Interactive HTML tutorials
- **Frontend Mentor**: Practice projects

**Books:**
- "HTML and CSS: Design and Build Websites" by Jon Duckett
- "Learning Web Design" by Jennifer Robbins
- "HTML5 Pocket Reference" by Jennifer Robbins

**Communities:**
- **Stack Overflow**: Ask questions
- **Reddit r/webdev**: Web development community
- **Dev.to**: Articles and tutorials
- **CSS-Tricks**: Tips and techniques

**YouTube Channels:**
- Traversy Media
- Web Dev Simplified
- The Net Ninja
- Kevin Powell

**Best Practices Guides:**
- **HTML Best Practices**: https://github.com/hail2u/html-best-practices
- **Google HTML/CSS Style Guide**: https://google.github.io/styleguide/htmlcssguide.html
- **Accessibility Guidelines**: https://www.w3.org/WAI/WCAG21/quickref/

**Keep Learning:**
- Build real projects
- Contribute to open source
- Stay updated with web standards
- Practice regularly
- Review and refactor your code

---

**Congratulations!** You now have a comprehensive guide to HTML from fundamentals to advanced topics. Keep practicing and building projects to solidify your knowledge.
