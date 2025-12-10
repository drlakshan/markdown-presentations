# How to Use Marp

A simple guide to creating presentation slides with Markdown using Marp.

## What is Marp?

Marp allows you to write presentation slides in Markdown format. This means you can:

- Write slides quickly in your text editor
- Version control your presentations with Git
- Customize layouts with CSS
- Focus on content rather than design

## Installation

Install Marp CLI using a package manager:

```bash
yarn global add marp-cli
```

Or use Homebrew, Scoop, or npm.

## Creating Your First Slide Deck

### Basic Setup

Create a file called `presentation.md` with this content:

```markdown
---
marp: true
theme: uncover
paginate: true
---

# My Presentation Title

Your Name - @yoursocial

---
```

The section between `---` at the top is called **frontmatter**. It contains:
- `marp: true` - Indicates this is a Marp presentation
- `theme: uncover` - Sets the slide theme (other options: default, gaia)
- `paginate: true` - Adds page numbers to slides

### Viewing Your Slides

Run this command to preview your slides:

```bash
marp -w presentation.md
```

This opens a localhost URL in your browser showing your slides.

## Creating Slides

### Separating Slides

Use `---` to separate each slide:

```markdown
# First Slide

Content here

---

# Second Slide

More content here

---
```

### Adding Images

**Basic inline image:**

```markdown
![alt text](image-url.jpg)
```

**Resize inline image:**

```markdown
![w:800 h:480 alt text](image-url.jpg)
![width:600px](image.jpg)
```

**Background image (full slide):**

```markdown
![bg](image-url.jpg)

# Title over background
```

**Background sizing:**

```markdown
![bg contain](image.jpg)  # Fit image within slide
![bg fit](image.jpg)       # Alias for contain
![bg cover](image.jpg)     # Fill slide (default)
![bg 150%](image.jpg)      # Scale to 150%
```

**Split backgrounds (content + image side-by-side):**

Split backgrounds are perfect for slides that need both text content and an image (like QR codes, diagrams, or photos).

```markdown
# Image on the left (50% split)
![bg left](image-url.jpg)

# Content on the right

- Bullet point 1
- Bullet point 2
```

```markdown
# Image on the right (33% split)
![bg right:33%](image-url.jpg)

# Content on the left (67% width)

- Bullet point 1
- Bullet point 2
```

**Common split background use cases:**
- `![bg right:33%]` - Small image (like QR code) on right, content on left
- `![bg left:40%]` - Medium image on left, content on right
- `![bg right:50%]` or `![bg right]` - Equal split

**Image filters:**

Apply CSS filters to images:

```markdown
![blur:10px](image.jpg)
![brightness:1.5](image.jpg)
![grayscale:1](image.jpg)
![sepia:50%](image.jpg)
```

**Multiple filters:**

```markdown
![brightness:.8 sepia:50%](image.jpg)
```

### Code Snippets

Add code blocks with syntax highlighting:

````markdown
```go
type Reader interface {
    Read(p []byte) (n int, err error)
}
```
````

### Bullet Lists

Regular list:

```markdown
- Item 1
- Item 2
- Item 3
```

Fragmented list (items appear one by one):

```markdown
* Item 1
* Item 2
* Item 3
```

## Speaker Notes

Add notes only you can see when presenting:

```markdown
# My Slide

Slide content here

<!--
These are speaker notes
- Point to mention
- Reminder for myself
-->
```

To use speaker notes: Open the presentation in your browser, hover over the slides, and click the lectern icon to enter presenter view.

## Customizing with CSS

### Single Slide Styling

Use `<style scoped>` to style one slide:

```markdown
---

<style scoped>
code {
  font-size: 40px;
}
</style>

# My Slide

Content here

---
```

### All Slides Styling

Use `<style>` (without scoped) to style all slides:

```markdown
<style>
section {
  padding-bottom: 20%;
}
</style>
```

### Example: Title Slide with Background

```markdown
<style scoped>
h1, p {
  color: #FFFFFF;
  font-weight: bold;
  text-shadow: 5px 5px 3px #000000;
}
</style>

![bg](background-image.jpg)

# My Talk Title

Your Name - @yoursocial
```

### Two-Column Layouts

For reliable two-column layouts, use the `.two-columns` CSS class (included in master template):

```html
<div class="two-columns">
<div>

### Left Column

- Point 1
- Point 2
- Point 3

</div>
<div>

### Right Column

- Point A
- Point B
- Point C

</div>
</div>
```

**Important:** Include blank lines between HTML tags and markdown content for proper rendering.

The CSS for this class:
```css
.two-columns {
  display: flex;
}
.two-columns > div {
  flex: 1;
  padding: 0 20px;
}
```

## Advanced Features

### Directives

Marp uses "directives" to control slide settings. Full details in `directives.md`.

**Spot Directives** (underscore prefix applies to current slide only):

```markdown
<!-- _paginate: false -->  <!-- Skip page number on title slide -->
<!-- _class: lead -->       <!-- Center content on this slide -->
```

**Pagination Control:**

```markdown
---
paginate: true  <!-- Show page numbers starting from slide 2 -->
---

# Title Slide
<!-- No page number shown here -->

---

# Slide 2
<!-- Page 2 shown here -->
```

Advanced pagination:
- `paginate: skip` - Hide number and don't increment
- `paginate: hold` - Show number but don't increment

**Headers and Footers:**

```markdown
---
header: '**Becoming an Infinite Learner**'
footer: 'Dr. MTD Lakshan | December 2025'
---
```

Can include formatting and images:
```markdown
footer: '![w:20px](logo.png) University of Moratuwa'
```

**Heading Divider** (auto-create slides):

```markdown
---
headingDivider: 2
---

# Slide 1

## Slide 2  <!-- Automatically creates new slide -->

Content here

## Slide 3  <!-- Another new slide -->
```

### Styling

**Inline Style** (applies to all slides):

```markdown
<style>
section {
  background: linear-gradient(to bottom, #1e1e2e, #2e2e3e);
}
h1 {
  border-bottom: 5px solid #cba6f7;
}
</style>
```

**Scoped Style** (current slide only):

```markdown
<style scoped>
h1 {
  text-align: center;
  font-size: 100px;
  color: gold;
}
</style>

# This Title is Centered and Gold

---

# This Title is Normal
```

**Background Colors and Gradients:**

```markdown
<!-- _backgroundColor: #1a1a2e -->

Or with gradients:

<!-- _backgroundImage: "linear-gradient(to bottom, #67b8e3, #0288d1)" -->
```

## Tips and Tricks

### Background Image for All Slides

Add to frontmatter:

```markdown
---
marp: true
theme: uncover
paginate: true
backgroundImage: url('background.png')
---
```

### Common Image Directives

- `w:width` - Set width in pixels
- `h:height` - Set height in pixels
- `bg` - Use as background
- `bg left` - Background on left side only
- `bg right` - Background on right side only

### Exporting to PDF

```bash
marp presentation.md --pdf
```

### Exporting to HTML

```bash
marp presentation.md -o output.html
```

## Quick Example Presentation

```markdown
---
marp: true
theme: uncover
paginate: true
---

# Introduction to Marp

Creating slides with Markdown

---

## Why Use Marp?

* Fast to write
* Version control friendly
* Customizable with CSS

---

## Code Example

```javascript
function hello() {
  console.log("Hello, Marp!");
}
```

---

# Questions?

Thank you!
```

## Additional Resources

- Marp has a VSCode extension for live preview while editing
- Built-in themes: default, uncover, gaia
- Full CSS customization supported
- HTML elements can be mixed with Markdown

---

Happy presenting!


## Presentation with a server
marp -w -p infinite-learner-ai-era.md
