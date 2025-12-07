# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a **Git-based presentation management system** using Marp (Markdown Presentations). Each presentation is created as an isolated Git branch from a master template, ensuring brand consistency while maintaining complete version history.

## Key Architecture Principles

### Non-Merging Branching Strategy
- **Master branch** contains ONLY `master-template.md` - never actual presentations
- Each presentation lives on its own branch (e.g., `client-pitch-2025`, `conference-pycon`)
- **Branches are NEVER merged back to master** - they remain archived independently
- To update old presentations with new branding: `git rebase master` on the presentation branch

### File Structure
```
/
├── master-template.md          # Source of truth template (ready for duplication)
├── core-foundation/            # Reference documentation and examples
│   ├── PRESENTATION-WORKFLOW-SOP.md
│   ├── How-to-Use-Marp.md
│   ├── sample-purple-presentation.md
│   └── purple-theme.css
└── assets/                     # Media and logos
```

## Common Commands

### Creating a New Presentation
```bash
# Create new branch from master
git checkout master
git checkout -b presentation-name

# Copy template (rename appropriately)
cp master-template.md my-presentation.md

# Edit content in my-presentation.md
# Commit frequently with descriptive messages
```

**Naming Convention:** `<topic>-<event>-<year>` (e.g., `ai-healthcare-conference-2025`)

### Exporting Presentations
```bash
# Export to PDF (most common)
marp presentation-name.md --pdf

# Export to HTML
marp presentation-name.md --html

# Export to PowerPoint
marp presentation-name.md --pptx

# Live preview during editing
marp -w presentation-name.md
```

### Version Control Workflow
```bash
# Save work frequently
git add .
git commit -m "Add section on topic X"

# Backup to remote
git push origin presentation-name

# List all presentations
git branch -a

# Switch to old presentation
git checkout old-presentation-branch
```

### Updating Master Template (Branding Changes)
```bash
# Edit master-template.md on master branch
git checkout master
# Make changes to master-template.md
git commit -m "Update brand colors"

# Apply to existing presentation (optional)
git checkout existing-presentation-branch
git rebase master
```

## Master Template Structure

`master-template.md` contains:
1. **YAML Frontmatter** - Marp configuration + embedded CSS styling
2. **Embedded CSS** - Complete purple/Catppuccin dark theme (#1e1e2e background)
3. **Slide Templates** - Pre-structured slides:
   - Title slide with credentials
   - About the Presenter (with `.author-info` and `.contact-info` classes)
   - Agenda
   - Content sections (with examples: lists, blockquotes, code, tables)
   - Two-column layouts
   - Conclusion/Q&A slides

### Color Scheme (Purple Theme)
- Background: `#1e1e2e` (dark)
- H1 headers: `#cba6f7` (purple)
- H2 headers: `#b4befe` (light purple)
- H3 headers: `#89b4fa` (blue-purple)
- Body text: `#cdd6f4` (light gray)
- Accent: `#6c71c4` (borders, page numbers)
- Strong text: `#f5c2e7` (pink)

## AI-Assisted Formatting Workflow

When a user provides raw content to format into slides:

1. **Understand the content** - Read through all provided material
2. **Structure appropriately** - Determine logical slide breaks
3. **Apply master template patterns**:
   - Use `---` for slide separators
   - Follow heading hierarchy (# for titles, ## for sections, ### for subsections)
   - Apply two-column layouts where appropriate
   - Use blockquotes for important quotes/highlights
   - Format code with triple backticks and language tags
   - Create tables for data visualization
4. **Maintain brand voice** - Professional, academic, medical education context
5. **Preserve contact information** - Always include Dr. Lakshan's credentials and links

## Presenter Information (Always Use)

**Dr. MTD LAKSHAN**
MBBS MS DOHNS FEB ORL HNS FRCS Ed ORL HNS

**Roles:**
- Board Certified Consultant in ENT and Head and Neck Surgery
- Senior Lecturer in Medical Education, University of Kelaniya
- Director, Nawaloka Hospitals PLC
- Head, Nawaloka Research and Education Foundation
- Founder, Infinite Learner AI

**Contact:**
- Email: lakshan@health.lk
- LinkedIn: [mtd-lakshan](https://www.linkedin.com/in/mtd-lakshan-78738213)
- Website: [health.lk](https://www.health.lk)
- Infinite Learner AI: [ilai.academy](https://ilai.academy/)

## Marp-Specific Syntax Notes

### Slide Separators
```markdown
---
```

### Speaker Notes (Hidden in Slides)
```markdown
<!-- This is a speaker note -->
```

### Two-Column Layout
Use the `.two-columns` class for reliable two-column layouts:
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

**Note:** The `.two-columns` class uses flexbox and is more reliable than inline grid styles in Marp. Make sure to include blank lines between HTML tags and markdown content for proper rendering.

### Images

**Inline Images:**
```markdown
![width:600px](path/to/image.png)
![w:400px h:300px](image.jpg)
```

**Background Images:**
```markdown
![bg](background-image.jpg)
![bg contain](background-image.jpg)
![bg fit](background-image.jpg)
```

**Split Backgrounds (Content + Image Side-by-Side):**
```markdown
![bg right](background-image.jpg)
![bg left](background-image.jpg)
![bg right:33%](background-image.jpg)  <!-- Image takes 33% on right -->
![bg left:40%](background-image.jpg)   <!-- Image takes 40% on left -->
```

**Split backgrounds** are ideal for slides with both content and images (like QR codes, diagrams, or photos). The image becomes a background on the specified side while content stays on the opposite side. Use percentage values to control the split ratio.

**Example - Presenter slide with QR code:**
```markdown
## About the Presenter

![bg right:33% width:280px](assets/linkedin-qr-code.jpg)

**Dr. MTD LAKSHAN**
- Board Certified Consultant
- Senior Lecturer
```

**Image Filters:**
```markdown
![blur:10px](image.jpg)
![brightness:1.5](image.jpg)
![grayscale:1](image.jpg)
```

### Custom Classes
- `.author-info` - Author credentials styling
- `.contact-info` - Contact details styling
- `.footer` - Footer positioning
- `.two-columns` - Two-column flexbox layout (equal width columns with padding)

## Important Notes

- **Never commit exported files** (PDF/HTML/PPTX) - these go in `exports/` (gitignored)
- **Assets management** - Reference `assets/links-to-assets.md` for logo URLs
- **Presentation branches never merge to master** - This prevents merge conflicts between unrelated presentations
- **Master template updates** - When branding changes, update master-template.md; existing presentations can rebase to inherit changes
- **One presentation = One branch** - Scalable, searchable via Git, complete isolation

## Advanced Marp Features

### Directives
Marp uses "directives" to control presentation settings. See `core-foundation/directives.md` for full details.

**Spot Directives** (apply to single slide only):
```markdown
<!-- _paginate: false -->  <!-- Hide page number on this slide only -->
<!-- _class: lead -->       <!-- Apply 'lead' class to this slide only -->
<!-- _backgroundColor: black -->
```

**Pagination Options:**
- `paginate: true` - Show page number and increment
- `paginate: false` - Hide page number but still increment
- `paginate: skip` - Hide page number and don't increment
- `paginate: hold` - Show page number but don't increment

**Headers and Footers:**
```markdown
---
header: '**Presentation Title**'
footer: '![w:20px](logo.png) Company Name'
---
```

**Heading Divider** (auto-create slides at headings):
```markdown
---
headingDivider: 2
---
# Slide 1
## Slide 2  <!-- Automatically creates new slide -->
### Content in Slide 2
```

### Theming and Styling
See `core-foundation/theming.md` for comprehensive theming documentation.

**Inline Style Tweaks:**
```markdown
<style>
section {
  background: linear-gradient(to bottom, #1e1e2e, #2e2e3e);
}
</style>
```

**Scoped Style** (current slide only):
```markdown
<style scoped>
h1 {
  text-align: center;
  font-size: 80px;
}
</style>
```

**Custom Classes:**
```markdown
<!-- _class: lead -->
# Centered Title Slide
```

## Reference Documentation

For detailed workflows and troubleshooting, refer to:
- `core-foundation/PRESENTATION-WORKFLOW-SOP.md` - Complete SOP with step-by-step procedures
- `core-foundation/How-to-Use-Marp.md` - Technical Marp syntax guide
- `core-foundation/directives.md` - Complete directives reference (pagination, headers, footers, styling)
- `core-foundation/image-how-to.md` - Comprehensive image syntax guide
- `core-foundation/theming.md` - Theme CSS creation and customization
- `core-foundation/sample-purple-presentation.md` - Working example

## Troubleshooting Quick Fixes

**CSS not applying:** Verify YAML frontmatter is at the very top of the file with `---` delimiters

**Images not showing:** Use relative paths from the .md file location

**PDF export issues:** Ensure Marp CLI is installed: `npm install -g @marp-team/marp-cli`

**Branch confusion:** Always check current branch with `git branch` before editing
