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

Basic image:

```markdown
![alt text](image-url.jpg)
```

Resize image:

```markdown
![w:800 h:480 alt text](image-url.jpg)
```

Background image:

```markdown
![bg](image-url.jpg)

# Title over background
```

Split layout (image left, text right):

```markdown
![bg left 70%](image-url.jpg)

# Content on the right

- Bullet point 1
- Bullet point 2
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
