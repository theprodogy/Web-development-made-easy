# Figma Documentation

Welcome to the Figma section of Web Development Made Easy!

## Table of Contents

### Part 1: Fundamentals
- [Introduction to Figma](#introduction-to-figma)
- [Getting Started](#getting-started)
  - [Creating an Account](#creating-an-account)
  - [Understanding the Interface](#understanding-the-interface)
  - [Files and Projects](#files-and-projects)
- [Basic Tools](#basic-tools)
  - [Frame Tool](#frame-tool)
  - [Shape Tools](#shape-tools)
  - [Text Tool](#text-tool)
  - [Selection Tools](#selection-tools)
- [Working with Layers](#working-with-layers)
  - [Layer Panel](#layer-panel)
  - [Organizing Layers](#organizing-layers)
  - [Naming Conventions](#naming-conventions)
- [Properties Panel](#properties-panel)
  - [Position and Size](#position-and-size)
  - [Constraints](#constraints)
  - [Alignment and Distribution](#alignment-and-distribution)
- [Colors and Fills](#colors-and-fills)
  - [Solid Colors](#solid-colors)
  - [Gradients](#gradients)
  - [Images](#images)
- [Strokes and Effects](#strokes-and-effects)
  - [Stroke Properties](#stroke-properties)
  - [Drop Shadows](#drop-shadows)
  - [Blur Effects](#blur-effects)
- [Typography Basics](#typography-basics)
  - [Font Selection](#font-selection)
  - [Text Properties](#text-properties)
  - [Text Styles](#text-styles)

### Part 2: Advanced Topics
- [Components](#components)
  - [Creating Components](#creating-components)
  - [Component Instances](#component-instances)
  - [Overriding Properties](#overriding-properties)
  - [Component Variants](#component-variants)
  - [Boolean Properties](#boolean-properties)
- [Auto Layout](#auto-layout)
  - [Setting Up Auto Layout](#setting-up-auto-layout)
  - [Spacing and Padding](#spacing-and-padding)
  - [Direction and Alignment](#direction-and-alignment)
  - [Responsive Resizing](#responsive-resizing)
  - [Nested Auto Layouts](#nested-auto-layouts)
- [Prototyping](#prototyping)
  - [Creating Interactions](#creating-interactions)
  - [Transitions and Animations](#transitions-and-animations)
  - [Overlays](#overlays)
  - [Smart Animate](#smart-animate)
  - [Device Frames](#device-frames)
  - [Presenting Prototypes](#presenting-prototypes)
- [Design Systems](#design-systems)
  - [Color Styles](#color-styles)
  - [Text Styles](#text-styles-advanced)
  - [Effect Styles](#effect-styles)
  - [Grid Styles](#grid-styles)
  - [Building a Component Library](#building-a-component-library)
- [Advanced Layout Techniques](#advanced-layout-techniques)
  - [Layout Grids](#layout-grids)
  - [Constraints and Resizing](#constraints-and-resizing)
  - [Responsive Design](#responsive-design)
  - [Breakpoints](#breakpoints)
- [Plugins and Integrations](#plugins-and-integrations)
  - [Essential Figma Plugins](#essential-figma-plugins)
  - [Content Generation](#content-generation)
  - [Accessibility Plugins](#accessibility-plugins)
  - [Export Plugins](#export-plugins)
- [Collaboration Features](#collaboration-features)
  - [Commenting](#commenting)
  - [Sharing and Permissions](#sharing-and-permissions)
  - [Version History](#version-history)
  - [Branching](#branching)
  - [Team Libraries](#team-libraries)
- [Developer Handoff](#developer-handoff)
  - [Inspect Mode](#inspect-mode)
  - [Exporting Assets](#exporting-assets)
  - [Code Generation](#code-generation)
  - [CSS Properties](#css-properties)

### Part 3: Best Practices & Tips
- [Design Workflow](#design-workflow)
  - [Starting a New Project](#starting-a-new-project)
  - [Design Process](#design-process)
  - [Iteration and Feedback](#iteration-and-feedback)
- [Organization Best Practices](#organization-best-practices)
  - [File Structure](#file-structure)
  - [Page Organization](#page-organization)
  - [Naming Conventions](#naming-conventions-best-practices)
- [Component Best Practices](#component-best-practices)
  - [When to Create Components](#when-to-create-components)
  - [Component Architecture](#component-architecture)
  - [Variant Strategy](#variant-strategy)
- [Performance Tips](#performance-tips)
  - [Optimizing Large Files](#optimizing-large-files)
  - [Managing Complex Components](#managing-complex-components)
  - [Using Instances Wisely](#using-instances-wisely)
- [Accessibility in Design](#accessibility-in-design)
  - [Color Contrast](#color-contrast)
  - [Text Readability](#text-readability)
  - [Keyboard Navigation](#keyboard-navigation)
  - [Inclusive Design](#inclusive-design)
- [Design-to-Development Bridge](#design-to-development-bridge)
  - [Understanding Developer Needs](#understanding-developer-needs)
  - [Design Tokens](#design-tokens)
  - [Responsive Considerations](#responsive-considerations)
  - [Design Documentation](#design-documentation)
- [Common Mistakes to Avoid](#common-mistakes-to-avoid)
- [Keyboard Shortcuts](#keyboard-shortcuts)
- [Resources and Learning](#resources-and-learning)

---

## Part 1: Fundamentals

### Introduction to Figma

Figma is a cloud-based design and prototyping tool that has revolutionized the way designers and developers collaborate. Unlike traditional design software, Figma runs entirely in your web browser, making it accessible from any device with an internet connection.

**Why Figma?**

- **Real-time Collaboration**: Multiple people can work on the same file simultaneously, seeing each other's cursors and changes in real-time
- **Cloud-based**: No file syncing issues, automatic saving, accessible from anywhere
- **Cross-platform**: Works on Windows, Mac, Linux, and even Chromebooks
- **Free Tier**: Generous free plan for individuals and small teams
- **Developer-friendly**: Built-in tools for design handoff and CSS generation
- **Prototyping**: Create interactive prototypes without leaving the app
- **Design Systems**: Build and maintain scalable component libraries

**Who Uses Figma?**

- **UI/UX Designers**: Create interfaces, wireframes, and prototypes
- **Web Developers**: Understand designs, extract assets, and get CSS values
- **Product Managers**: Review designs, leave feedback, and track progress
- **Marketing Teams**: Create social media graphics and presentations
- **Anyone**: Who needs to collaborate on visual content

### Getting Started

#### Creating an Account

1. **Visit figma.com** and click "Sign up"
2. **Choose your method**:
   - Sign up with Google (fastest)
   - Sign up with email
3. **Select your role** (Designer, Developer, etc.) - this helps customize your experience
4. **Choose a plan**:
   - **Starter (Free)**: 3 Figma files, 3 FigJam files, unlimited personal files
   - **Professional**: Unlimited files, team libraries, advanced features
   - **Organization**: Enterprise features, SSO, admin controls

**Desktop App vs Browser**

While Figma works entirely in the browser, there's also a desktop app:
- **Browser**: No installation, works anywhere, always up-to-date
- **Desktop App**: Feels more native, works offline (with limitations), better performance for large files

Download the desktop app from figma.com/downloads if preferred.

#### Understanding the Interface

```
┌─────────────────────────────────────────────────────────────────┐
│  Menu Bar        │        Tab Bar (open files)                  │
├──────┬───────────┴──────────────────────────────────────┬───────┤
│      │                                                   │       │
│      │                                                   │ Design│
│Layers│              Canvas                               │ Panel │
│Panel │              (your workspace)                     │       │
│      │                                                   │Prototype│
│      │                                                   │ Panel │
│      │                                                   │       │
│      │                                                   │Inspect│
│      │                                                   │ Panel │
├──────┴───────────────────────────────────────────────────┴───────┤
│                    Toolbar (at top)                              │
└─────────────────────────────────────────────────────────────────┘
```

**Key Interface Elements:**

- **Toolbar** (top): Access to tools - Move, Frame, Shape, Pen, Text, etc.
- **Layers Panel** (left): Shows all objects in your file, organized hierarchically
- **Canvas** (center): Your main workspace where you create designs
- **Design Panel** (right): Properties of selected objects - size, color, effects
- **Prototype Panel** (right tab): Create interactions and flows
- **Inspect Panel** (right tab): View CSS code and measurements

**Navigating the Canvas:**

- **Zoom**: Scroll wheel or `Ctrl/Cmd + scroll`
- **Pan**: Hold `Space` and drag, or use scroll wheel + `Shift`
- **Zoom to fit**: `Shift + 1`
- **Zoom to selection**: `Shift + 2`
- **Zoom to 100%**: `Ctrl/Cmd + 0`

#### Files and Projects

**File Types:**

- **Figma Design Files** (.fig): For UI/UX design work
- **FigJam Files** (.jam): For brainstorming and collaboration

**Organization Structure:**

```
Team
├── Project 1
│   ├── Design File 1
│   ├── Design File 2
│   └── FigJam Brainstorm
├── Project 2
│   └── ...
└── Drafts (personal files)
```

**Creating Files:**

1. Click the **+** button or `Ctrl/Cmd + N`
2. Choose "Design file" or "FigJam file"
3. File opens in a new tab

**Organizing with Pages:**

Each file can have multiple pages (like tabs within a file):
- Click **+** next to "Page 1" in the Layers panel
- Use pages for: Wireframes, Components, Designs, Archive
- Rename pages by double-clicking

### Basic Tools

#### Frame Tool

The Frame tool (`F`) is fundamental in Figma. Frames are containers for your designs - think of them as artboards or screens.

**Creating Frames:**

1. Press `F` or select Frame from toolbar
2. **Click and drag** to draw a custom frame, OR
3. **Choose a preset** from the right panel (iPhone, Desktop, etc.)

**Common Frame Presets:**

| Device | Size |
|--------|------|
| iPhone 14 Pro | 393 × 852 |
| iPhone 14 Pro Max | 430 × 932 |
| iPad Pro 11" | 834 × 1194 |
| Desktop | 1440 × 900 |
| MacBook Pro 14" | 1512 × 982 |

**Frame Properties:**

- **Clip content**: Hide elements that extend beyond the frame
- **Background**: Set a fill color for the frame
- **Auto Layout**: Make frames dynamically resize (covered later)
- **Constraints**: Control how children resize when frame resizes

**Frame vs Group:**

| Feature | Frame | Group |
|---------|-------|-------|
| Has own size | Yes | No (based on children) |
| Can clip content | Yes | No |
| Background color | Yes | No |
| Auto Layout | Yes | No |
| Constraints | Yes | Limited |

**Use Frames for**: Screens, cards, buttons, any container
**Use Groups for**: Temporarily grouping objects for moving

#### Shape Tools

Access shape tools with these shortcuts:

| Shape | Shortcut |
|-------|----------|
| Rectangle | `R` |
| Ellipse (Circle) | `O` |
| Line | `L` |
| Polygon | (no shortcut) |
| Star | (no shortcut) |

**Creating Shapes:**

- **Click and drag** to draw
- **Hold `Shift`** for perfect squares/circles
- **Hold `Alt/Option`** to draw from center

**Rectangle Properties:**

- **Corner Radius**: Round corners individually or all at once
- **Independent Corners**: Click the icon to set each corner separately
- **Smoothing**: Creates iOS-style "squircle" corners

**Ellipse Properties:**

- **Arc**: Create pie charts or partial circles
- **Sweep**: Adjust the angle of the arc

**Boolean Operations** (combine shapes):

Select multiple shapes, then:
- **Union**: Combine into one shape
- **Subtract**: Cut one from another
- **Intersect**: Keep only overlapping area
- **Exclude**: Keep non-overlapping areas

#### Text Tool

Press `T` to activate the Text tool.

**Creating Text:**

- **Click once**: Creates text that expands horizontally (auto-width)
- **Click and drag**: Creates text box with fixed width (auto-height)

**Text Box Types:**

| Type | Behavior |
|------|----------|
| Auto Width | Box grows horizontally as you type |
| Auto Height | Fixed width, grows vertically |
| Fixed Size | Set width and height, text may overflow |

**Basic Text Properties:**

- **Font Family**: Choose from Google Fonts or local fonts
- **Font Weight**: Regular, Medium, Bold, etc.
- **Size**: In pixels
- **Line Height**: Auto, pixels, or percentage
- **Letter Spacing**: Adjust character spacing
- **Paragraph Spacing**: Space between paragraphs

**Text Alignment:**

- **Horizontal**: Left, Center, Right, Justify
- **Vertical**: Top, Middle, Bottom

#### Selection Tools

**Move Tool (V):**

- Click to select objects
- Drag to move selected objects
- Double-click to enter groups/frames

**Scale Tool (K):**

- Scales objects proportionally
- Also scales strokes and effects

**Selection Methods:**

- **Click**: Select single object
- **Shift + Click**: Add/remove from selection
- **Click and drag**: Marquee selection
- **Ctrl/Cmd + Click**: Select through groups (deep select)
- **Ctrl/Cmd + A**: Select all on current page

**Selection Tips:**

- Objects are selected from front to back
- Hold `Ctrl/Cmd` to select objects inside frames/groups
- Use Layers panel to select hard-to-reach objects

### Working with Layers

#### Layer Panel

The Layers panel shows your file's structure:

```
📄 Page 1
├── 📱 Frame: Home Screen
│   ├── 🔲 Header
│   │   ├── 🔤 Logo
│   │   └── 🔲 Nav Items
│   ├── 🖼️ Hero Section
│   └── 📝 Content
└── 📱 Frame: About Screen
```

**Layer Types (icons):**

- 📱 Frame
- 🔲 Rectangle/Shape
- ⭕ Ellipse
- 🔤 Text
- 🖼️ Image
- ◇ Component
- ⬚ Component Instance
- 📁 Group

**Layer Actions:**

- **Click**: Select layer
- **Double-click**: Rename layer
- **Drag**: Reorder layers
- **👁️ Eye icon**: Toggle visibility
- **🔒 Lock icon**: Lock/unlock layer

#### Organizing Layers

**Nesting Layers:**

Drag layers onto frames or groups to nest them:
```
📱 Card
├── 🖼️ Image
├── 🔤 Title
└── 🔤 Description
```

**Reordering:**

- **Drag** in Layers panel
- **Ctrl/Cmd + ]**: Bring forward
- **Ctrl/Cmd + [**: Send backward
- **Ctrl/Cmd + Shift + ]**: Bring to front
- **Ctrl/Cmd + Shift + [**: Send to back

**Grouping:**

- Select objects and press `Ctrl/Cmd + G` to group
- `Ctrl/Cmd + Shift + G` to ungroup

#### Naming Conventions

Good naming makes files easier to navigate:

**Recommended Format:**

```
[Type] / [Name] / [State/Variant]

Examples:
Button / Primary / Default
Button / Primary / Hover
Icon / Arrow / Right
Card / Product / Small
```

**Tips:**

- Use `/` to create visual hierarchy (Figma shows as breadcrumbs)
- Be consistent across your file
- Name frames after screens: "Home", "Profile", "Settings"
- Name components descriptively: "Card/Product" not "Rectangle 47"

### Properties Panel

#### Position and Size

Selected objects show their properties in the Design panel:

**Position:**
- **X**: Horizontal position from left
- **Y**: Vertical position from top
- Reference point can be changed (center, corners)

**Size:**
- **W**: Width in pixels
- **H**: Height in pixels
- **🔗 Link icon**: Constrain proportions

**Rotation:**
- Degrees from 0-360
- Drag corner handles to rotate
- Hold `Shift` for 15° increments

**Math in Fields:**

You can use math in any numeric field:
- `100+50` = 150
- `200/2` = 100
- `50*3` = 150
- `100-25` = 75

#### Constraints

Constraints control how objects resize when their parent frame resizes:

**Horizontal Constraints:**
- **Left**: Stay fixed distance from left
- **Right**: Stay fixed distance from right
- **Left & Right**: Stretch with frame
- **Center**: Stay centered
- **Scale**: Scale proportionally

**Vertical Constraints:**
- **Top**: Stay fixed distance from top
- **Bottom**: Stay fixed distance from bottom
- **Top & Bottom**: Stretch with frame
- **Center**: Stay centered
- **Scale**: Scale proportionally

**Example Usage:**

```
Header bar: Left & Right (horizontal), Top (vertical)
   → Stretches full width, stays at top

Center button: Center (both)
   → Always centered in frame

Footer: Left & Right (horizontal), Bottom (vertical)
   → Stretches full width, stays at bottom
```

#### Alignment and Distribution

**Alignment** (when multiple objects selected):
- Align Left, Center, Right
- Align Top, Middle, Bottom

**Distribution**:
- Distribute horizontally (equal spacing)
- Distribute vertically (equal spacing)

**Tidy Up**: Auto-arrange selected objects neatly

**Keyboard Shortcuts:**
- `Alt/Option + A`: Align left
- `Alt/Option + D`: Align right
- `Alt/Option + H`: Align center horizontally
- `Alt/Option + W`: Align top
- `Alt/Option + S`: Align bottom
- `Alt/Option + V`: Align center vertically

### Colors and Fills

#### Solid Colors

Every shape can have a fill (inside color) and stroke (border).

**Adding a Fill:**

1. Select object
2. Click **+** next to "Fill" in Design panel
3. Click the color swatch to open color picker

**Color Picker Options:**

- **Solid**: Single color
- **Gradient**: Color transition
- **Image**: Fill with image

**Color Formats:**

- **Hex**: #FF5733
- **RGB**: 255, 87, 51
- **HSB**: Hue, Saturation, Brightness

**Opacity:**

- Adjust the % next to the color
- 100% = fully visible, 0% = invisible

**Document Colors:**

Colors you use are saved in "Document colors" for reuse. Click a saved color to apply it.

**Eyedropper:**

- Press `I` or click eyedropper icon
- Click anywhere to pick that color

#### Gradients

Figma supports multiple gradient types:

**Gradient Types:**

1. **Linear**: Straight line transition
2. **Radial**: Circular transition from center
3. **Angular**: Rotates around center point
4. **Diamond**: Diamond-shaped transition

**Creating a Gradient:**

1. Select object
2. Click fill color swatch
3. Change "Solid" dropdown to gradient type
4. Click on the gradient bar to add color stops
5. Drag stops to adjust positions
6. Use handles on canvas to adjust angle/position

**Gradient Controls:**

- **Add stop**: Click on gradient bar
- **Remove stop**: Drag stop away from bar
- **Move stop**: Drag along bar
- **Rotate**: Drag handles on canvas

#### Images

**Adding Images:**

1. **Drag and drop** from your computer
2. **Copy/paste** from clipboard
3. **File menu → Place Image** (`Ctrl/Cmd + Shift + K`)

**Image Fill:**

Images can be used as fills for any shape:
1. Select shape
2. Click fill color
3. Choose "Image" from dropdown
4. Select image file

**Image Fit Options:**

- **Fill**: Scales to fill shape (may crop)
- **Fit**: Scales to fit inside (may letterbox)
- **Crop**: Manual positioning
- **Tile**: Repeats image as pattern

**Image Adjustments:**

- **Exposure**: Brightness
- **Contrast**: Difference between light/dark
- **Saturation**: Color intensity
- **Temperature**: Warm/cool tones
- **Tint**: Color shift
- **Highlights/Shadows**: Adjust specific tones

### Strokes and Effects

#### Stroke Properties

**Adding a Stroke:**

1. Select object
2. Click **+** next to "Stroke"
3. Set color, weight, and style

**Stroke Options:**

- **Color**: Same options as fill
- **Weight**: Thickness in pixels
- **Position**: Inside, Center, or Outside of path
- **Type**: Solid, Dashed, or Custom

**Dash Pattern:**

For dashed lines:
- **Dash**: Length of dash
- **Gap**: Space between dashes

**Cap and Join:**

- **Cap** (line ends): None, Round, Square
- **Join** (corners): Miter (sharp), Round, Bevel (flat)

**Advanced Strokes:**

- Multiple strokes: Click **+** to add more
- Gradient strokes: Use gradient as stroke color
- Variable width: Use Pen tool for paths with varying widths

#### Drop Shadows

**Adding a Shadow:**

1. Select object
2. Click **+** next to "Effects"
3. Choose "Drop shadow"

**Shadow Properties:**

- **X offset**: Horizontal distance
- **Y offset**: Vertical distance
- **Blur**: Softness (higher = softer)
- **Spread**: Size expansion
- **Color**: Shadow color with opacity

**Common Shadow Values:**

| Style | X | Y | Blur | Spread | Opacity |
|-------|---|---|------|--------|---------|
| Subtle | 0 | 2 | 4 | 0 | 10% |
| Medium | 0 | 4 | 8 | 0 | 15% |
| Large | 0 | 8 | 24 | 0 | 20% |
| Floating | 0 | 20 | 40 | 0 | 25% |

**Inner Shadow:**

Creates shadow inside the object (inset effect).

#### Blur Effects

**Layer Blur:**

Blurs the entire selected layer:
- Good for background elements
- Specify blur amount in pixels

**Background Blur:**

Blurs content *behind* the layer:
- Perfect for frosted glass effect
- Layer must have semi-transparent fill
- Common in iOS-style interfaces

**Creating Frosted Glass:**

1. Create a rectangle
2. Add white fill at 50% opacity
3. Add Background Blur effect (10-20px)
4. Optionally add subtle border

### Typography Basics

#### Font Selection

**Accessing Fonts:**

Figma has access to:
- **Google Fonts**: Thousands of free fonts, available to everyone
- **Local Fonts**: Fonts installed on your computer (need Figma Font Helper)

**Installing Font Helper:**

For local fonts: figma.com/downloads → Figma Font Installers

**Choosing Fonts:**

Consider:
- **Readability**: Clear at various sizes
- **Personality**: Matches brand/product tone
- **Versatility**: Multiple weights available
- **Web availability**: Can developers use it?

**Safe Font Combinations:**

| Use Case | Heading | Body |
|----------|---------|------|
| Modern | Inter | Inter |
| Classic | Playfair Display | Lora |
| Clean | Montserrat | Open Sans |
| Technical | Space Grotesk | IBM Plex Sans |

#### Text Properties

**Essential Properties:**

| Property | Description | Common Values |
|----------|-------------|---------------|
| Font Size | Text height | 14-16px body, 24-48px headings |
| Line Height | Space between lines | 1.4-1.6x font size |
| Letter Spacing | Character spacing | 0-2% for body, more for headings |
| Paragraph Spacing | Space after paragraphs | Equal to line height |

**Line Height Tips:**

- **Auto**: Figma calculates (~1.2x)
- Use **%** for scalable designs (e.g., 150%)
- Use **px** for precise control

**Advanced Properties:**

- **Case**: Uppercase, Lowercase, Title Case
- **Decoration**: Underline, Strikethrough
- **Baseline**: Subscript, Superscript
- **Truncation**: Clip with ellipsis (...)

#### Text Styles

Create reusable text styles for consistency:

**Creating a Text Style:**

1. Select text with desired formatting
2. Click **Style** icon (4 dots) next to text properties
3. Click **+** to create new style
4. Name it descriptively (e.g., "Heading/H1")

**Recommended Text Styles:**

```
Heading / H1        - 48px, Bold
Heading / H2        - 36px, Bold
Heading / H3        - 24px, Semibold
Heading / H4        - 20px, Semibold
Body / Large        - 18px, Regular
Body / Default      - 16px, Regular
Body / Small        - 14px, Regular
Caption             - 12px, Regular
Button              - 14px, Medium, Uppercase
Link                - 16px, Regular, Underline
```

**Using Styles:**

1. Select text
2. Click style dropdown
3. Choose saved style

**Editing Styles:**

- Edit the style: All instances update automatically
- Detach from style: Make local changes without affecting style

---

## Part 2: Advanced Topics

### Components

Components are reusable design elements that help maintain consistency and save time. When you update a component, all instances update automatically.

#### Creating Components

**Creating a Component:**

1. Select the object(s) you want to make into a component
2. Press `Ctrl/Cmd + Alt + K`, or
3. Right-click → "Create component", or
4. Click the component icon in the toolbar

**Component Structure:**

```
◇ Main Component (purple diamond)
├── Has a purple border
├── Is the "source of truth"
└── Lives in your file

⬚ Instance (empty diamond)
├── Has a dashed purple border
├── Linked to main component
└── Updates when main changes
```

**Naming Components:**

Use `/` to organize in the Assets panel:
```
Button / Primary / Default
Button / Primary / Hover
Button / Secondary / Default
Icon / Arrow / Left
Icon / Arrow / Right
```

This creates a folder structure:
```
📁 Button
   📁 Primary
      ◇ Default
      ◇ Hover
   📁 Secondary
      ◇ Default
📁 Icon
   📁 Arrow
      ◇ Left
      ◇ Right
```

#### Component Instances

**Creating Instances:**

- **Drag** from Assets panel (left sidebar)
- **Copy/paste** an existing instance or component
- **Alt/Option + drag** a component

**Instance Properties:**

Instances inherit all properties from the main component but can have:
- **Overrides**: Local changes that don't affect main
- **Nested instances**: Swap internal components
- **Text overrides**: Change text content

**Finding the Main Component:**

- Right-click instance → "Go to main component"
- Or click the "Main component" link in the right panel

#### Overriding Properties

Instances can be customized without breaking the link:

**What Can Be Overridden:**

| Property | Can Override |
|----------|--------------|
| Text content | ✅ Yes |
| Fill color | ✅ Yes |
| Stroke color | ✅ Yes |
| Visibility | ✅ Yes |
| Nested instances | ✅ Yes |
| Position | ❌ No (unless using Auto Layout) |
| Size | ❌ No (unless using constraints) |

**Resetting Overrides:**

- Right-click → "Reset all overrides"
- Or reset individual properties in the right panel

**Detaching Instances:**

- Right-click → "Detach instance"
- Instance becomes a regular frame
- No longer linked to component
- Use sparingly!

#### Component Variants

Variants group related components together (e.g., button states, sizes).

**Creating Variants:**

1. Select multiple components that are variations of each other
2. Click "Combine as variants" in the right panel
3. Figma creates a variant component set

**Variant Properties:**

```
◇ Button (Component Set)
├── Size: Small, Medium, Large
├── State: Default, Hover, Pressed, Disabled
└── Type: Primary, Secondary, Outline
```

**Setting Up Properties:**

1. Select the variant component set
2. Add properties in the right panel:
   - Property name: "Size"
   - Values: "Small, Medium, Large"
3. Assign values to each variant

**Swapping Variants:**

When using an instance:
1. Select the instance
2. Use dropdowns in right panel to switch variants
3. Changes instantly

**Example: Button Variant Structure:**

```
Property: Size      [Small] [Medium] [Large]
Property: State     [Default] [Hover] [Pressed] [Disabled]
Property: Type      [Primary] [Secondary]

= 3 × 4 × 2 = 24 possible combinations
```

#### Boolean Properties

Boolean properties create toggleable on/off options in components.

**Common Uses:**

- Show/hide icons
- Show/hide badges or notifications
- Toggle states (loading, checked)

**Creating a Boolean Property:**

1. Select the layer you want to toggle
2. In the right panel, click the property icon (⚙️)
3. Choose "Boolean" property type
4. Name it (e.g., "Show icon")

**Using in Instances:**

A toggle checkbox appears in the instance properties:
```
☐ Show icon
☑ Show badge
☐ Loading
```

### Auto Layout

Auto Layout makes frames behave like CSS flexbox, automatically arranging and resizing children.

#### Setting Up Auto Layout

**Adding Auto Layout:**

1. Select a frame or objects
2. Press `Shift + A`, or
3. Click "+" next to Auto Layout in right panel

**Direction:**

- **Horizontal (→)**: Children arranged left to right
- **Vertical (↓)**: Children arranged top to bottom
- **Wrap**: Items wrap to next line when space runs out

**Example - Creating a Button:**

1. Create a text layer: "Submit"
2. Select text and press `Shift + A`
3. Add fill color to the frame
4. Add corner radius
5. Now button resizes with text!

#### Spacing and Padding

**Padding** (space inside frame):

```
┌─────────────────────────────────────┐
│  padding-top                        │
│  ┌─────────────────────────────┐    │
│ p│         Content             │p   │
│ a│                             │a   │
│ d│                             │d   │
│ l│                             │r   │
│ e│                             │i   │
│ f├─────────────────────────────┤g   │
│ t│  padding-bottom             │h   │
│  └─────────────────────────────┘t   │
└─────────────────────────────────────┘
```

- **Uniform**: Same on all sides
- **Separate**: Different for each side (click the padding icon)

**Gap** (space between children):

```
[Item 1]  gap  [Item 2]  gap  [Item 3]
```

**Common Padding/Spacing:**

| Element | Padding | Gap |
|---------|---------|-----|
| Button | 12-16px | N/A |
| Card | 16-24px | 12-16px |
| Section | 40-80px | 24-32px |
| Navigation | 16px | 24px |

#### Direction and Alignment

**Main Axis Alignment** (direction of children):

| Value | Description |
|-------|-------------|
| Start | Pack to start |
| Center | Center along axis |
| End | Pack to end |
| Space Between | Equal space between items |

**Cross Axis Alignment** (perpendicular to direction):

| Value | Description |
|-------|-------------|
| Top/Left | Align to start |
| Center | Center on axis |
| Bottom/Right | Align to end |
| Stretch | Fill available space |

**Visual Guide:**

```
Horizontal Layout (→):
┌────────────────────────────────┐
│ [A] [B] [C]                    │ ← Packed start, Top
│         [A] [B] [C]            │ ← Centered, Center
│                    [A] [B] [C] │ ← Packed end, Bottom
│ [A]      [B]      [C]          │ ← Space between
└────────────────────────────────┘
```

#### Responsive Resizing

**Resizing Behavior** (per child):

- **Hug**: Shrink to fit content
- **Fill**: Expand to fill available space
- **Fixed**: Stay at set size

**Example - Responsive Navigation:**

```
[Logo (Fixed)] [Nav Items (Fill)] [Button (Hug)]
     120px         Expands            Auto
```

**Setting Resizing:**

1. Select child within auto layout
2. In right panel, set:
   - **Horizontal resizing**: Fixed, Hug, or Fill
   - **Vertical resizing**: Fixed, Hug, or Fill

**Min/Max Width:**

Set minimum and maximum sizes for flexible elements:
- Prevents text from getting too narrow
- Keeps components from stretching too wide

#### Nested Auto Layouts

Combine auto layouts for complex responsive designs:

**Example - Card Layout:**

```
Card (Vertical Auto Layout)
├── Image (Fixed height)
├── Content (Vertical Auto Layout, Hug)
│   ├── Title
│   └── Description
└── Actions (Horizontal Auto Layout)
    ├── Button 1 (Fill)
    └── Button 2 (Fill)
```

**Example - Responsive Grid:**

```
Container (Horizontal Auto Layout, Wrap)
├── Card 1 (Fixed width, fills available)
├── Card 2
├── Card 3
└── Card 4 (wraps to next row when needed)
```

### Prototyping

#### Creating Interactions

**Connecting Frames:**

1. Select an element (button, link, etc.)
2. Switch to **Prototype** tab (right panel)
3. Click and drag the blue circle to target frame
4. Connection appears as arrow

**Trigger Types:**

| Trigger | Description |
|---------|-------------|
| On Click | When clicked/tapped |
| On Drag | While dragging |
| While Hovering | Mouse over element |
| While Pressing | Mouse button held down |
| Key/Gamepad | Keyboard input |
| Mouse Enter | Mouse enters area |
| Mouse Leave | Mouse exits area |
| After Delay | Auto-trigger after time |

**Action Types:**

| Action | Description |
|--------|-------------|
| Navigate to | Go to another frame |
| Open Overlay | Show frame on top |
| Swap Overlay | Replace current overlay |
| Close Overlay | Dismiss overlay |
| Back | Return to previous frame |
| Scroll to | Scroll to specific element |
| Open Link | Navigate to URL |

#### Transitions and Animations

**Transition Types:**

| Type | Description | Best For |
|------|-------------|----------|
| Instant | No animation | Quick switches |
| Dissolve | Fade transition | General transitions |
| Smart Animate | Animate changes | Micro-interactions |
| Move In | Slide from direction | Modals, panels |
| Move Out | Slide to direction | Dismissing |
| Push | Push current frame | Page navigation |
| Slide In | Slide over content | Drawers |
| Slide Out | Slide current away | Dismissing |

**Easing Options:**

| Easing | Description |
|--------|-------------|
| Linear | Constant speed |
| Ease In | Start slow, end fast |
| Ease Out | Start fast, end slow |
| Ease In and Out | Smooth start and end |
| Ease In Back | Slight pullback before moving |
| Custom | Define bezier curve |

**Duration:**

- **Micro-interactions**: 100-200ms
- **Page transitions**: 200-400ms
- **Complex animations**: 400-600ms

#### Overlays

Overlays appear on top of the current screen (modals, dropdowns, etc.).

**Creating an Overlay:**

1. Design your overlay as a separate frame
2. Connect trigger element → overlay frame
3. Set action to "Open overlay"

**Overlay Settings:**

- **Position**: Where overlay appears (center, top-left, etc.)
- **Close when clicking outside**: Enable/disable
- **Add background behind overlay**: Dim background
- **Background color**: Usually black at 50% opacity

**Example - Dropdown Menu:**

1. Create dropdown frame (list of options)
2. Select dropdown trigger button
3. Connect with "Open overlay"
4. Position: Bottom left of trigger
5. Set "Close when clicking outside": On

#### Smart Animate

Smart Animate creates smooth animations between frames when elements share the same name.

**How It Works:**

1. Create Frame A with named element
2. Create Frame B with same named element in different state
3. Connect with Smart Animate transition
4. Figma animates the differences

**What Smart Animate Detects:**

- Position changes
- Size changes
- Rotation
- Opacity
- Fill/stroke color
- Corner radius
- Scale

**Tips for Smart Animate:**

1. **Name layers identically** in both frames
2. Keep component structure similar
3. Use on small changes for best results
4. Test with short durations first

**Example - Button Press:**

```
Frame 1 (Default)       Frame 2 (Pressed)
[Button]                [Button]
  Color: Blue            Color: Dark Blue
  Scale: 100%            Scale: 95%

Connect with Smart Animate → Smooth press effect
```

#### Device Frames

Add realistic device frames to your prototypes:

**Adding Device Frame:**

1. Select your frame
2. In right panel, expand "Device frame"
3. Choose device type

**Available Devices:**

- iPhones (various models)
- Android phones
- iPads and tablets
- MacBooks and laptops
- Desktop monitors
- Apple Watch

**Custom Device Frames:**

- Set custom colors for phone frames
- Toggle device shadows

#### Presenting Prototypes

**Starting Presentation:**

1. Click **Present** button (▶️) in top right
2. Or press `Ctrl/Cmd + Alt + Enter`

**Presentation Options:**

- **Starting frame**: Which frame to show first
- **Device**: Show device frame
- **Background color**: Canvas background
- **Hotspot hints**: Show clickable areas (press `H`)

**Sharing Prototypes:**

1. Click **Share** in presentation mode
2. Copy link
3. Set permissions (view, comment, edit)

**Viewer Experience:**

- Click through interactions
- Comment on specific elements
- No Figma account needed (for view-only)

### Design Systems

#### Color Styles

Create reusable color definitions:

**Creating Color Styles:**

1. Select object with desired color
2. Click fill color → Style icon (4 dots)
3. Click **+** to create new style
4. Name descriptively (e.g., "Primary/500")

**Recommended Color Structure:**

```
Primary
├── 50 (lightest)
├── 100
├── 200
├── 300
├── 400
├── 500 (base)
├── 600
├── 700
├── 800
└── 900 (darkest)

Neutral / Gray
├── 50 to 900

Semantic
├── Success
├── Warning
├── Error
├── Info

Surface
├── Background
├── Card
├── Overlay
```

**Using Color Styles:**

1. Select object
2. Click fill color
3. Switch to "Styles" tab
4. Click style to apply

#### Text Styles

(Covered in Part 1 - see Typography Basics)

**Advanced Text Style Organization:**

```
Heading
├── Display / Large
├── Display / Medium
├── H1
├── H2
├── H3
└── H4

Body
├── Large / Regular
├── Large / Bold
├── Default / Regular
├── Default / Bold
├── Small / Regular
└── Small / Bold

UI
├── Button / Large
├── Button / Default
├── Label
├── Caption
└── Overline
```

#### Effect Styles

Save reusable effects (shadows, blurs):

**Creating Effect Styles:**

1. Apply effect to object
2. Click effect → Style icon
3. Click **+** to create style
4. Name it (e.g., "Shadow/Medium")

**Example Effect Styles:**

```
Shadow
├── Small    (y:1, blur:2)
├── Medium   (y:4, blur:8)
├── Large    (y:8, blur:24)
└── XL       (y:16, blur:48)

Blur
├── Glass / Light
├── Glass / Dark
└── Background
```

#### Grid Styles

Save reusable layout grids:

**Creating Grid Styles:**

1. Add grid to frame
2. Click grid → Style icon
3. Click **+** to create style

**Common Grid Styles:**

```
Layout / Desktop (1440px)
├── 12 columns, 72px each
├── 24px gutter
└── 120px margin

Layout / Tablet (768px)
├── 8 columns
├── 20px gutter
└── 32px margin

Layout / Mobile (375px)
├── 4 columns
├── 16px gutter
└── 20px margin

Spacing / 8pt Grid
└── 8px uniform grid
```

#### Building a Component Library

**Organization Strategy:**

```
📄 Cover Page
📄 Getting Started
📄 Components
   ├── Atoms
   │   ├── Icons
   │   ├── Buttons
   │   ├── Inputs
   │   └── Tags
   ├── Molecules
   │   ├── Cards
   │   ├── List Items
   │   └── Form Groups
   └── Organisms
       ├── Navigation
       ├── Headers
       └── Footers
📄 Patterns
   ├── Forms
   ├── Tables
   └── Modals
📄 Documentation
```

**Best Practices:**

1. Use consistent naming conventions
2. Document component usage with text annotations
3. Include all states and variants
4. Test with real content
5. Version your updates

### Advanced Layout Techniques

#### Layout Grids

Layout grids help maintain consistent spacing and alignment.

**Grid Types:**

| Type | Use Case |
|------|----------|
| Columns | Page layout structure |
| Rows | Vertical rhythm |
| Grid | Baseline grid, icon alignment |

**Adding Grids:**

1. Select frame
2. Click **+** next to "Layout grid"
3. Configure: columns, rows, or grid

**Column Grid Settings:**

- **Count**: Number of columns (12 is common)
- **Type**: Stretch, Center, or Left/Right
- **Width**: Column width (if fixed)
- **Gutter**: Space between columns
- **Margin**: Space on edges

**Example - 12 Column Grid:**

```
|--margin--|--col--|gutter|--col--|gutter|...|--col--|--margin--|
```

#### Constraints and Resizing

**Advanced Constraint Patterns:**

**Sticky Header:**
```
Header constraints: Left & Right, Top
→ Stretches with frame, stays at top
```

**Centered Modal:**
```
Modal constraints: Center, Center
→ Always centered regardless of screen size
```

**Fixed Sidebar:**
```
Sidebar constraints: Left, Top & Bottom
→ Fixed width, full height
```

**Fluid Content:**
```
Content constraints: Left & Right, Top & Bottom
→ Fills remaining space
```

#### Responsive Design

**Breakpoint Strategy:**

| Name | Width | Common Devices |
|------|-------|----------------|
| Mobile | 375px | iPhones |
| Mobile Large | 414px | Large phones |
| Tablet | 768px | iPad, tablets |
| Desktop | 1440px | Laptops, monitors |
| Wide | 1920px | Large monitors |

**Designing Responsively:**

1. **Start mobile-first**: Design smallest size first
2. **Create variants**: Multiple frames for each breakpoint
3. **Use Auto Layout**: Makes responsive behavior easier
4. **Test constraints**: Resize frames to test flexibility

#### Breakpoints

**Setting Up Breakpoints:**

1. Create separate frames for each breakpoint
2. Name consistently: "Home - Mobile", "Home - Desktop"
3. Use same styles and components
4. Adjust layouts for each size

**Common Layout Changes:**

| Element | Mobile | Desktop |
|---------|--------|---------|
| Navigation | Hamburger menu | Horizontal nav |
| Columns | 1 column | 2-4 columns |
| Sidebar | Hidden/collapsed | Visible |
| Images | Full width | Contained |
| Font sizes | Smaller | Larger |

### Plugins and Integrations

#### Essential Figma Plugins

**Search for plugins**: Menu → Plugins → Browse plugins

**Must-Have Plugins:**

| Plugin | Purpose |
|--------|---------|
| Unsplash | Free stock photos |
| Iconify | Access to icon libraries |
| Lorem Ipsum | Generate placeholder text |
| Stark | Accessibility checker |
| Figmotion | Advanced animations |
| Autoflow | Create user flow arrows |

#### Content Generation

**Content Plugins:**

- **Content Reel**: Real names, addresses, photos
- **Lorem Ipsum**: Placeholder text
- **Unsplash**: Stock photography
- **UI Faces**: Avatar photos
- **Charts**: Generate chart graphics
- **Blobs**: Create organic shapes

**Using Content Reel:**

1. Install plugin
2. Select text layers
3. Run plugin → choose content type
4. Populates with realistic data

#### Accessibility Plugins

**Stark:**

- Check color contrast ratios
- Simulate color blindness
- Generate accessibility reports

**A11y - Color Contrast Checker:**

- Quick WCAG contrast checking
- Shows pass/fail for AA and AAA

**Include - Accessibility Annotations:**

- Add accessibility annotations
- Document landmarks, headings
- Export for developers

#### Export Plugins

**Advanced Export:**

- Batch export with custom settings
- Export as PDF, multiple formats

**Zeplin:**

- Enhanced developer handoff
- Style guide generation

**Avocode:**

- Collaborative handoff
- Code generation for multiple platforms

### Collaboration Features

#### Commenting

**Adding Comments:**

1. Press `C` to enter comment mode
2. Click anywhere to add comment
3. Type message and post

**Comment Features:**

- **@mention**: Notify specific people
- **Threads**: Reply to continue discussion
- **Resolve**: Mark as addressed
- **Pin to layer**: Attach to specific element

**Best Practices:**

- Be specific about locations
- Use @mentions for action items
- Resolve when addressed
- Use emoji reactions for quick feedback 👍

#### Sharing and Permissions

**Permission Levels:**

| Level | Can View | Can Comment | Can Edit |
|-------|----------|-------------|----------|
| View | ✅ | ❌ | ❌ |
| Comment | ✅ | ✅ | ❌ |
| Edit | ✅ | ✅ | ✅ |

**Sharing a File:**

1. Click **Share** button (top right)
2. Add email or copy link
3. Set permission level
4. Send invitation

**Link Sharing Options:**

- **Anyone with link**: Public access
- **Only invited people**: Private access
- **Allow copying**: Let viewers duplicate

#### Version History

**Viewing History:**

1. Click file name → "Show version history"
2. Or `Ctrl/Cmd + Alt + H`

**History Features:**

- See all changes with timestamps
- Preview old versions
- Restore previous versions
- Name important versions

**Saving Versions:**

- Figma auto-saves continuously
- Name important milestones:
  - "Before client review"
  - "v1.0 Launch ready"
  - "Pre-redesign backup"

**To Name a Version:**

1. Open version history
2. Click **+** next to current state
3. Add title and description

#### Branching

Branching allows parallel work without affecting the main file:

**Creating a Branch:**

1. Click dropdown next to file name
2. Select "Create branch"
3. Name your branch (e.g., "Dark mode exploration")

**Branch Workflow:**

1. **Create branch** for experimental work
2. **Make changes** freely
3. **Review** differences from main
4. **Merge** if approved, or discard

**Best For:**

- Design explorations
- Major redesigns
- Multiple designers working on same file
- A/B testing variations

#### Team Libraries

**Publishing to Library:**

1. Open the file with components
2. Click **Assets** panel → library icon (book)
3. Click "Publish"
4. Add description and publish

**Using Libraries:**

1. In any file, click Assets panel
2. Click library icon
3. Enable team libraries
4. Components appear in assets

**Library Updates:**

- When library changes, instances show update available
- Review changes before accepting
- Update all at once or individually

### Developer Handoff

#### Inspect Mode

**Accessing Inspect:**

1. Switch to **Inspect** tab in right panel
2. Or click an element while in view-only mode

**Inspect Features:**

- **Measurements**: Click to see dimensions and spacing
- **Properties**: View all element properties
- **Code**: Get CSS/iOS/Android code snippets

**Viewing Measurements:**

- Hover over elements to see sizes
- Hold `Alt/Option` and hover to see distances
- Click to select and see all properties

#### Exporting Assets

**Export Settings:**

1. Select element to export
2. Scroll to "Export" section in right panel
3. Click **+** to add export
4. Set format and scale

**Export Formats:**

| Format | Use Case |
|--------|----------|
| PNG | Raster images, transparency |
| JPG | Photos, smaller files |
| SVG | Icons, logos, illustrations |
| PDF | Documents, print |

**Export Scales:**

- **1x**: Standard resolution
- **2x**: Retina/HiDPI displays
- **3x**: High-end mobile
- **4x**: Print or very high resolution

**Batch Export:**

1. Add export settings to multiple elements
2. File → Export (or `Ctrl/Cmd + Shift + E`)
3. All elements export at once

**Export Naming:**

- Name layers properly before export
- "icon-arrow-right" → icon-arrow-right.svg

#### Code Generation

**CSS Code:**

Figma generates CSS for selected elements:

```css
/* Example output */
width: 320px;
height: 48px;
background: #2563EB;
border-radius: 8px;
font-family: 'Inter';
font-size: 16px;
color: #FFFFFF;
```

**iOS Code:**

```swift
// Example output
view.frame = CGRect(x: 0, y: 0, width: 320, height: 48)
view.backgroundColor = UIColor(red: 0.145, green: 0.388, blue: 0.922, alpha: 1)
view.layer.cornerRadius = 8
```

**Android Code:**

```xml
<!-- Example output -->
android:layout_width="320dp"
android:layout_height="48dp"
android:background="@color/primary_500"
```

#### CSS Properties

**What Figma Exports:**

| Figma | CSS |
|-------|-----|
| Fill | background, background-color |
| Stroke | border |
| Corner radius | border-radius |
| Shadow | box-shadow |
| Blur | filter: blur() |
| Position | top, left, width, height |
| Text | font-family, font-size, etc. |

**Limitations:**

- Auto Layout → Flexbox (not perfect match)
- Constraints → May need manual positioning
- Complex effects → May need simplification

**Tips for Developers:**

- Use Design panel, not just Inspect
- Check for color/text styles for consistency
- Export SVGs for icons
- Ask designers about intended behavior

---

## Part 3: Best Practices & Tips

### Design Workflow

#### Starting a New Project

**Project Setup Checklist:**

1. **Create project folder** in Figma
2. **Set up file structure**:
   ```
   📁 Project Name
   ├── 📄 Research & References
   ├── 📄 Wireframes
   ├── 📄 Design System
   ├── 📄 Designs (Working File)
   └── 📄 Handoff (Clean File)
   ```
3. **Configure pages** within design file:
   ```
   📄 Designs
   ├── 📑 Cover
   ├── 📑 Components
   ├── 📑 Desktop
   ├── 📑 Tablet
   ├── 📑 Mobile
   └── 📑 Archive
   ```
4. **Set up layout grids** for each breakpoint
5. **Define initial styles** (colors, typography)
6. **Import brand assets** (logos, icons)

**Cover Page Best Practices:**

Create a cover page with:
- Project name and description
- Last updated date
- Team members and roles
- Status (In Progress, Review, Complete)
- Links to related files

#### Design Process

**Recommended Workflow:**

1. **Research & Gather Requirements**
   - Understand user needs
   - Review competitive analysis
   - Collect brand guidelines

2. **Low-Fidelity Wireframes**
   - Focus on layout and structure
   - Use simple shapes (no styling)
   - Iterate quickly

3. **High-Fidelity Mockups**
   - Apply visual design
   - Use real content when possible
   - Create component library as you go

4. **Prototype**
   - Add interactions
   - Test user flows
   - Validate with stakeholders

5. **Handoff**
   - Clean up layers and naming
   - Add documentation
   - Export assets

**Time-Saving Tips:**

- Build components early, reuse often
- Use Auto Layout from the start
- Copy successful patterns from previous projects
- Use plugins to speed up repetitive tasks

#### Iteration and Feedback

**Getting Good Feedback:**

1. **Set context**: Explain what you're showing and why
2. **Ask specific questions**: "Is the hierarchy clear?" vs "What do you think?"
3. **Use presentation mode**: Show the design as users will see it
4. **Record user reactions**: Note hesitations and confusion

**Managing Feedback:**

- Use comments in Figma for async feedback
- Create a feedback log with priorities
- Distinguish between "nice to have" and "must fix"
- Set deadlines for feedback rounds

**Version Control:**

- Name versions at key milestones
- Branch for major explorations
- Keep an "Archive" page for old iterations
- Never delete—archive instead

### Organization Best Practices

#### File Structure

**Team-Level Organization:**

```
📁 Team Workspace
├── 📁 Brand & Assets
│   ├── 📄 Brand Guidelines
│   ├── 📄 Logo Files
│   └── 📄 Icon Library
├── 📁 Design System
│   ├── 📄 Tokens & Styles
│   ├── 📄 Components
│   └── 📄 Documentation
├── 📁 Product A
│   ├── 📄 Designs
│   ├── 📄 Prototypes
│   └── 📄 Archive
└── 📁 Product B
    └── ...
```

**File-Level Organization:**

```
📄 App Designs
├── 📑 Cover
├── 📑 —— Design System ——
├── 📑 Colors & Typography
├── 📑 Components
├── 📑 —— Screens ——
├── 📑 Onboarding
├── 📑 Home
├── 📑 Profile
├── 📑 Settings
├── 📑 —— Other ——
├── 📑 Prototypes
└── 📑 Archive
```

**Tips:**

- Use "——" separator pages for visual grouping
- Keep components on dedicated pages
- Maintain a "Sandbox" page for experiments
- Archive old work instead of deleting

#### Page Organization

**Component Page Layout:**

```
┌─────────────────────────────────────────────────────────────┐
│  📝 Page Title: Components                                  │
│  Description and usage notes                                │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐         │
│  │ Buttons     │  │ Inputs      │  │ Cards       │         │
│  │ ○ Primary   │  │ ○ Text      │  │ ○ Default   │         │
│  │ ○ Secondary │  │ ○ Dropdown  │  │ ○ Featured  │         │
│  │ ○ Outline   │  │ ○ Checkbox  │  │             │         │
│  └─────────────┘  └─────────────┘  └─────────────┘         │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

**Screen Design Layout:**

```
┌─────────────────────────────────────────────────────────────┐
│  📝 Screen: Home                                            │
│  Notes: Main dashboard view after login                     │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  [Mobile]     [Tablet]        [Desktop]                     │
│  ┌───────┐    ┌───────────┐   ┌─────────────────────────┐  │
│  │       │    │           │   │                         │  │
│  │       │    │           │   │                         │  │
│  │       │    │           │   │                         │  │
│  └───────┘    └───────────┘   └─────────────────────────┘  │
│                                                             │
│  Annotations and specifications below...                    │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

#### Naming Conventions

**Layer Naming Rules:**

| Type | Format | Example |
|------|--------|---------|
| Frames (screens) | PascalCase | `HomeScreen`, `UserProfile` |
| Components | Type/Name/Variant | `Button/Primary/Default` |
| Groups | kebab-case | `header-content`, `nav-items` |
| Shapes | descriptive | `background`, `icon-container` |
| Icons | icon-name | `icon-arrow-right`, `icon-close` |

**Avoid:**

- Default names: "Rectangle 47", "Frame 123"
- Vague names: "Group 1", "Component 2"
- Inconsistent patterns: mixing styles

**Find and Rename:**

Use plugins like "Rename It" to batch rename layers with patterns:
- `icon-*` → adds prefix
- `*-v2` → adds suffix
- Sequential numbering

### Component Best Practices

#### When to Create Components

**Create a Component When:**

- Element appears **3+ times** in designs
- Element has **multiple states** (hover, active, disabled)
- Element needs to be **consistent** across pages
- You want **single source of truth** for updates

**Don't Over-Component:**

- One-off decorative elements
- Highly specific layouts that won't repeat
- Simple shapes without states

**Component Candidates:**

| Always | Sometimes | Rarely |
|--------|-----------|--------|
| Buttons | Page headers | Decorative dividers |
| Form inputs | Hero sections | Background patterns |
| Cards | Navigation | One-off illustrations |
| Icons | Footers | Unique layouts |
| Avatars | Modals | |

#### Component Architecture

**Atomic Design Approach:**

```
Atoms (smallest elements)
├── Icons
├── Buttons
├── Inputs
├── Labels
└── Avatars

Molecules (combinations of atoms)
├── Input + Label + Error = Form Field
├── Avatar + Name = User Chip
└── Icon + Text = Menu Item

Organisms (complex combinations)
├── Logo + Nav Items + CTA = Header
├── Card Grid = Product Listing
└── Form Fields + Button = Contact Form

Templates (page layouts)
└── Header + Content + Footer = Page Template
```

**Building Flexible Components:**

1. **Use Auto Layout**: Makes components responsive
2. **Add variants**: Cover all states and sizes
3. **Use boolean properties**: Toggle optional elements
4. **Expose text**: Let instances change text content
5. **Use slot components**: Placeholders for swappable content

**Slot Pattern:**

```
Card Component
├── Image Slot (swap with any image component)
├── Content Slot (swap with different content layouts)
└── Action Slot (swap with different button groups)
```

#### Variant Strategy

**Organizing Variants:**

**Property Types:**

| Property | Values | Use |
|----------|--------|-----|
| Size | Small, Medium, Large | Scale variations |
| Type | Primary, Secondary, Outline | Visual style |
| State | Default, Hover, Active, Disabled | Interaction states |
| Icon | Left, Right, None | Icon position |

**Naming Convention:**

```
Size=Medium, Type=Primary, State=Default
Size=Large, Type=Secondary, State=Hover
```

**Variant Grid Organization:**

```
           Default    Hover    Active    Disabled
           ──────────────────────────────────────
Primary    [●]        [●]      [●]       [●]
Secondary  [●]        [●]      [●]       [●]
Outline    [●]        [●]      [●]       [●]
```

### Performance Tips

#### Optimizing Large Files

**Signs of Performance Issues:**

- Slow zooming and panning
- Delayed selection
- Long loading times
- Memory warnings

**Optimization Strategies:**

1. **Reduce unnecessary complexity**
   - Flatten unused groups
   - Simplify complex paths
   - Remove hidden layers

2. **Use components wisely**
   - Don't nest too deeply (3-4 levels max)
   - Avoid massive variant sets
   - Split large libraries into multiple files

3. **Optimize images**
   - Use appropriate resolution
   - Compress before importing
   - Consider SVG for simple graphics

4. **Clean up regularly**
   - Delete unused pages
   - Remove detached instances
   - Archive old iterations

#### Managing Complex Components

**Component Complexity Limits:**

- Keep variants under 100 per component set
- Limit nesting to 3-4 levels
- Split complex components into composable parts

**Example - Simplifying a Complex Button:**

Instead of:
```
Button (200+ variants)
├── Size: S, M, L
├── Type: Primary, Secondary, Tertiary, Ghost, Destructive
├── State: Default, Hover, Active, Disabled, Loading
├── Icon: None, Left, Right, Both
└── = 3 × 5 × 5 × 4 = 300 combinations
```

Split into:
```
Button Base (45 variants)
├── Size: S, M, L
├── Type: Primary, Secondary, Tertiary, Ghost, Destructive
└── State: Default, Hover, Active

Button Content (slots)
├── Icon Left (optional)
├── Label
└── Icon Right (optional)

Button States (handled via boolean/instance swap)
├── isDisabled
└── isLoading
```

#### Using Instances Wisely

**Do:**

- Create instances from Assets panel (not copy/paste main)
- Override only what's necessary
- Update to latest library version regularly
- Use instance swap for flexible layouts

**Don't:**

- Create hundreds of instances on one page
- Override structure (add/remove layers)
- Ignore library updates
- Detach instances unnecessarily

**Instance vs Detach:**

| Scenario | Action |
|----------|--------|
| Need to change color | Override ✅ |
| Need different text | Override ✅ |
| Need completely different structure | Consider new component or detach |
| One-off unique element | Detach may be okay |

### Accessibility in Design

#### Color Contrast

**WCAG Contrast Requirements:**

| Level | Normal Text | Large Text | UI Components |
|-------|-------------|------------|---------------|
| AA | 4.5:1 | 3:1 | 3:1 |
| AAA | 7:1 | 4.5:1 | N/A |

**Large Text = 18px+ (or 14px+ bold)**

**Checking Contrast:**

1. Use Stark or Contrast plugin
2. Check Figma's built-in contrast checker
3. Manual: Use online contrast checkers

**Tips:**

- Don't rely on color alone to convey meaning
- Ensure text is readable on all backgrounds
- Test with grayscale filter
- Consider dark mode accessibility

#### Text Readability

**Minimum Sizes:**

| Type | Desktop | Mobile |
|------|---------|--------|
| Body text | 16px | 16px |
| Small text | 14px | 14px |
| Caption | 12px | 12px (use sparingly) |

**Line Length:**

- Optimal: 50-75 characters per line
- Maximum: 80 characters
- Adjust container widths accordingly

**Line Height:**

- Body text: 1.4 - 1.6
- Headings: 1.1 - 1.3
- Increase for longer line lengths

**Font Choice:**

- Use highly legible fonts for body text
- Avoid decorative fonts for small text
- Test with real content, not lorem ipsum

#### Keyboard Navigation

**Design Considerations:**

- **Focus states**: Every interactive element needs visible focus
- **Tab order**: Logical progression through the page
- **Skip links**: Allow jumping to main content
- **No traps**: Users must be able to navigate away

**Focus State Design:**

```
Default:      [  Button  ]
Focused:      [  Button  ] ← 2px outline, offset 2px
                  └── High contrast outline
```

**Document Focus Order:**

Create annotations showing tab order:
```
[1] Skip to content link
[2] Logo (home link)
[3] Nav item 1
[4] Nav item 2
...
```

#### Inclusive Design

**Consider Diverse Users:**

- **Visual impairments**: Contrast, screen readers, zoom
- **Motor impairments**: Touch target size (44x44px min), keyboard access
- **Cognitive differences**: Clear hierarchy, simple language
- **Situational limitations**: Bright sunlight, one-handed use

**Touch Targets:**

| Platform | Minimum Size | Recommended |
|----------|--------------|-------------|
| iOS | 44 × 44 pt | 44 × 44 pt |
| Android | 48 × 48 dp | 48 × 48 dp |
| Web | 24 × 24 px | 44 × 44 px |

**Inclusive Patterns:**

- Icons + text labels (not icons alone)
- Error messages with suggestions
- Multiple ways to complete tasks
- Forgiving input formats

### Design-to-Development Bridge

#### Understanding Developer Needs

**What Developers Need:**

1. **Specifications**: Exact sizes, colors, spacing
2. **Assets**: Icons, images, logos (properly exported)
3. **States**: All interactive states defined
4. **Responsive behavior**: How layouts adapt
5. **Animations**: Timing and easing values
6. **Edge cases**: Empty states, loading, errors

**Common Developer Questions:**

- "What happens when this text is really long?"
- "How does this look on different screen sizes?"
- "What's the hover/focus/active state?"
- "Is this spacing 16px or 24px?"
- "What font weights are we using?"

#### Design Tokens

Design tokens are named values for design decisions:

**Token Types:**

```
Colors
├── color-primary-500: #2563EB
├── color-neutral-100: #F3F4F6
└── color-error-500: #EF4444

Spacing
├── space-1: 4px
├── space-2: 8px
├── space-4: 16px
└── space-8: 32px

Typography
├── font-size-sm: 14px
├── font-size-base: 16px
├── line-height-normal: 1.5
└── font-weight-bold: 700

Radius
├── radius-sm: 4px
├── radius-md: 8px
└── radius-full: 9999px

Shadows
├── shadow-sm: 0 1px 2px rgba(0,0,0,0.05)
└── shadow-md: 0 4px 6px rgba(0,0,0,0.1)
```

**Benefits:**

- Consistency between design and code
- Easy theme switching (light/dark mode)
- Clear communication with developers
- Single source of truth

**Implementing in Figma:**

- Use Figma styles (name them like tokens)
- Use plugins like "Tokens Studio for Figma"
- Export token files (JSON format)

#### Responsive Considerations

**Documenting Responsive Behavior:**

For each component/layout, specify:

1. **Breakpoints**: When layout changes
2. **Scaling**: What stretches, what stays fixed
3. **Reordering**: Elements that move on mobile
4. **Hiding**: Elements not shown on certain sizes

**Example Documentation:**

```
Header Component
├── Desktop (1440px+)
│   └── [Logo] [—— Nav Items ——] [Search] [Avatar]
├── Tablet (768px - 1439px)
│   └── [Logo] [—— Nav Items ——] [Icons only]
└── Mobile (<768px)
    └── [Hamburger] [Logo] [Search Icon]
```

#### Design Documentation

**What to Document:**

| Item | Description |
|------|-------------|
| Component usage | When and how to use each component |
| States | All possible states with visuals |
| Anatomy | Named parts of complex components |
| Dos and Don'ts | Usage guidelines |
| Spacing rules | Consistent spacing logic |
| Motion | Animation specifications |

**Documentation Format:**

```
┌─────────────────────────────────────────────────────────────┐
│  Button / Primary                                           │
├─────────────────────────────────────────────────────────────┤
│  Use for main actions like "Submit", "Save", "Continue"     │
│                                                             │
│  States:                                                    │
│  [Default] [Hover] [Active] [Disabled] [Loading]            │
│                                                             │
│  Sizes:                                                     │
│  [Small - 32px] [Medium - 40px] [Large - 48px]             │
│                                                             │
│  ✓ Do: Use one primary button per section                   │
│  ✗ Don't: Use for destructive actions (use Destructive)    │
└─────────────────────────────────────────────────────────────┘
```

### Common Mistakes to Avoid

**Organization:**

- ❌ Not naming layers ("Rectangle 47", "Frame 156")
- ❌ Deeply nested groups without purpose
- ❌ Scattered components across pages
- ❌ Deleting instead of archiving

**Components:**

- ❌ Not using components for repeated elements
- ❌ Making everything a component (over-engineering)
- ❌ Detaching instances instead of creating new variants
- ❌ Not defining all states

**Layout:**

- ❌ Using fixed positioning for everything
- ❌ Ignoring Auto Layout benefits
- ❌ Designing only for one screen size
- ❌ Inconsistent spacing (random values)

**Collaboration:**

- ❌ Not using styles for colors/text
- ❌ Poor version naming
- ❌ Not resolving comments
- ❌ Making changes without communicating

**Handoff:**

- ❌ Unorganized, messy files
- ❌ Missing states and edge cases
- ❌ Unexported or poorly named assets
- ❌ No documentation

### Keyboard Shortcuts

**Essential Shortcuts:**

| Action | Windows | Mac |
|--------|---------|-----|
| Move tool | V | V |
| Frame | F | F |
| Rectangle | R | R |
| Ellipse | O | O |
| Line | L | L |
| Text | T | T |
| Pen | P | P |
| Comment | C | C |
| Hand (pan) | H or Space | H or Space |
| Zoom in/out | + / - | + / - |

**Selection & Navigation:**

| Action | Windows | Mac |
|--------|---------|-----|
| Select all | Ctrl + A | Cmd + A |
| Deep select | Ctrl + Click | Cmd + Click |
| Select parent | Shift + Enter | Shift + Enter |
| Zoom to fit | Shift + 1 | Shift + 1 |
| Zoom to selection | Shift + 2 | Shift + 2 |
| Zoom to 100% | Ctrl + 0 | Cmd + 0 |

**Editing:**

| Action | Windows | Mac |
|--------|---------|-----|
| Copy | Ctrl + C | Cmd + C |
| Paste | Ctrl + V | Cmd + V |
| Duplicate | Ctrl + D | Cmd + D |
| Group | Ctrl + G | Cmd + G |
| Ungroup | Ctrl + Shift + G | Cmd + Shift + G |
| Component | Ctrl + Alt + K | Cmd + Option + K |
| Auto Layout | Shift + A | Shift + A |
| Undo | Ctrl + Z | Cmd + Z |
| Redo | Ctrl + Shift + Z | Cmd + Shift + Z |

**Layers:**

| Action | Windows | Mac |
|--------|---------|-----|
| Bring forward | Ctrl + ] | Cmd + ] |
| Send backward | Ctrl + [ | Cmd + [ |
| Bring to front | Ctrl + Shift + ] | Cmd + Shift + ] |
| Send to back | Ctrl + Shift + [ | Cmd + Shift + [ |
| Hide/show | Ctrl + Shift + H | Cmd + Shift + H |
| Lock/unlock | Ctrl + Shift + L | Cmd + Shift + L |

### Resources and Learning

**Official Resources:**

- **Figma Help Center**: help.figma.com
- **Figma Community**: figma.com/community (free templates & plugins)
- **Figma YouTube**: youtube.com/@figma
- **Figma Blog**: figma.com/blog

**Learning Platforms:**

- **Figma's own tutorials**: Built into the app
- **YouTube**: Tons of free tutorials
- **Skillshare/LinkedIn Learning**: Structured courses
- **DesignLab**: Mentorship programs

**Community Files:**

Explore the Community for:
- UI kits and design systems
- Wireframe templates
- Icon libraries
- Practice projects

**Stay Updated:**

- Follow Figma on Twitter/X
- Join Figma Discord communities
- Subscribe to newsletters (Figmalion, Design Systems newsletter)
- Attend Config (Figma's annual conference)

**Practice Projects:**

1. **Redesign an app**: Pick an app you use, redesign it
2. **Daily UI challenge**: 100 days of UI prompts
3. **Clone a website**: Recreate a site you admire
4. **Build a design system**: Start small, grow over time
5. **Prototype micro-interactions**: Practice Smart Animate

---

**Congratulations!** 🎨 You now have a solid foundation in Figma. Remember:

- **Practice regularly**: Design something every day
- **Study good design**: Analyze apps and sites you admire
- **Get feedback**: Share your work and learn from critiques
- **Stay curious**: Figma updates frequently—keep learning new features

Happy designing!
