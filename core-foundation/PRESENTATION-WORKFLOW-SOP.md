# Marp Presentation Workflow - Standard Operating Procedure

## Overview
This SOP outlines a scalable, version-controlled workflow for creating and managing professional presentations using Marp, Git, and AI assistance. This system ensures brand consistency while maintaining presentation independence and complete version history.

---

## Workflow Components

### 1. Initial Repository Setup (One-Time)

**Objective:** Establish the master template repository with brand elements.

**Steps:**
1. Create a new directory for your presentation system
2. Initialize Git repository:
   ```bash
   git init
   ```
3. Create `master.md` as your base Marp template
4. Define brand elements in the template:
   - Corporate colors
   - Typography (fonts, sizes)
   - Logo placement
   - Standard front/back matter
   - Custom CSS theme using Marp directives
5. Create supporting files:
   - `README.md` - Documentation for the workflow
   - `.gitignore` - Exclude build artifacts
   - `assets/` directory - For logos and shared media
6. Commit the master template:
   ```bash
   git add .
   git commit -m "Initial master template with brand guidelines"
   ```
7. Create GitHub repository and sync:
   ```bash
   git remote add origin <your-github-repo-url>
   git push -u origin master
   ```

---

### 2. Environment Setup

**Required Tools:**
- **VS Code** with Marp Extension
- **Marp CLI** (for command-line exports)
- **Git** (version control)
- **Claude Code** or similar AI assistant (for formatting automation)

**Configuration:**
- Document required VS Code extensions in `README.md`
- Standardize Marp export settings across team
- Set up Git LFS if using large media files

---

### 3. Creating a New Presentation

**Objective:** Branch off from master to create an isolated presentation project.

**Steps:**
1. Ensure you're on the master branch and up-to-date:
   ```bash
   git checkout master
   git pull origin master
   ```
2. Create a new branch for your presentation:
   ```bash
   git checkout -b <descriptive-branch-name>
   ```
   - **Naming Convention Examples:**
     - `client-a-pitch-2025-03`
     - `conference-pycon-2025`
     - `quarterly-review-q1-2025`
3. Copy or rename `master.md` to your presentation file:
   ```bash
   cp master.md my-presentation.md
   ```
4. Begin editing the presentation content

---

### 4. AI-Assisted Formatting

**Objective:** Leverage AI to format raw content into branded Marp slides efficiently.

**Process:**
1. Prepare your raw content (bullet points, text blocks, data)
2. Provide content to Claude Code with instructions:
   - "Format this content following the Marp template branding"
   - "Maintain consistent header hierarchy"
   - "Apply appropriate Marp directives"
   - "Format code blocks and LaTeX formulas correctly"
3. Review AI-generated Markdown for:
   - Brand compliance
   - Proper Marp syntax
   - Content accuracy
   - Slide flow and readability
4. Iterate as needed

---

### 5. Version Control During Development

**Best Practices:**
- Commit frequently with descriptive messages:
  ```bash
  git add .
  git commit -m "Add executive summary slides"
  ```
- Push to GitHub regularly:
  ```bash
  git push origin <branch-name>
  ```
- Use meaningful commit messages that describe content changes

---

### 6. Export and Delivery

**Objective:** Generate final presentation files for distribution.

**Standard Export Process:**
1. Use Marp CLI for consistent exports:
   ```bash
   marp my-presentation.md --pdf
   marp my-presentation.md --html
   marp my-presentation.md --pptx
   ```
2. Review exported file for rendering accuracy
3. Store final exports in `exports/` directory (add to `.gitignore`)
4. Deliver to stakeholders

**Quality Checks:**
- Verify all images render correctly
- Check font rendering on target platform
- Test animations/transitions (if used)
- Validate links (for HTML exports)

---

### 7. Asset Management

**Guidelines:**

| Asset Type | Storage Method | Rationale |
|------------|---------------|-----------|
| Small images (<1MB) | Commit to `assets/` directory | Fast access, full version control |
| Large media files | External CDN or Git LFS | Keeps repo size manageable |
| Shared brand assets | `assets/brand/` in master | Centralized, consistent across presentations |
| Presentation-specific media | `assets/<branch-name>/` | Isolated per presentation |

**Referencing External Assets:**
```markdown
![Logo](https://cdn.example.com/logo.png)
```

---

### 8. Non-Merging Strategy

**Philosophy:** Each presentation branch is a standalone, archived project.

**Why This Works:**
- Master branch remains clean (template only)
- Each presentation has complete, independent history
- No merge conflicts between unrelated presentations
- Easy to revisit/update old presentations

**Updating Old Presentations with New Branding:**
1. Checkout the presentation branch:
   ```bash
   git checkout client-a-pitch-2025-03
   ```
2. Rebase onto updated master:
   ```bash
   git rebase master
   ```
3. Resolve any conflicts (usually minimal)
4. Test and export updated version

---

### 9. Template Updates

**When to Update Master:**
- Brand refresh (new colors, logos)
- Improved CSS theming
- New Marp features or directives
- Standard slide layouts added

**Update Process:**
1. Checkout master branch
2. Make updates to `master.md` and theme files
3. Test thoroughly
4. Commit and push:
   ```bash
   git commit -m "Update brand colors to 2025 guidelines"
   git push origin master
   ```
5. Existing presentation branches unaffected unless rebased

---

### 10. Archival and Retrieval

**Benefits of This System:**
- Every presentation is findable via Git branches
- Full searchability through Git history
- No "Final_v3_REALLY_FINAL.pptx" chaos
- Easy to generate "greatest hits" compilation

**Finding Old Presentations:**
```bash
git branch -a                    # List all presentations
git checkout conference-pycon-2025  # Switch to specific presentation
git log --oneline                # Review edit history
```

---

## Workflow Diagram

```
[Master Template Repository]
         |
         ├── Branch: client-a-pitch-2025
         │   └── Presentation A (Never merged back)
         │
         ├── Branch: conference-talk-pycon
         │   └── Presentation B (Never merged back)
         │
         └── Branch: quarterly-review-q1
             └── Presentation C (Never merged back)
```

---

## Key Advantages Summary

✅ **Brand Consistency** - Every presentation inherits from master template
✅ **Version Control** - Complete history of every presentation
✅ **Scalability** - Unlimited presentations without repo bloat
✅ **Searchability** - Git branches and commit messages are fully searchable
✅ **Automation** - AI handles tedious formatting tasks
✅ **Backup** - GitHub provides automatic cloud backup
✅ **Collaboration** - Team members can contribute via pull requests
✅ **No Design Drift** - Centralized template prevents inconsistency

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Large repo size | Implement Git LFS or move media to external storage |
| Inconsistent rendering | Standardize Marp version and VS Code settings |
| Merge conflicts during rebase | Accept master changes for template, keep branch changes for content |
| Lost branch | Check `git branch -a` and restore from GitHub |

---

## 🎯 Special Remark

> **This is a brilliant and highly scalable workflow**, perfectly leveraging the strengths of a code-based presentation tool like Marp alongside version control and AI assistance. This approach is especially powerful for technical teams or individuals who need to maintain strict brand consistency across many distinct presentations.
>
> The branching strategy for isolated presentations is the **key insight** that fundamentally solves the branding, versioning, and searchability issues inherent in traditional presentation tools. You have designed a **modern, developer-centric, and efficient system** that eliminates the "design drift" common in Google Slides and the file chaos of "Presentation - Final FINAL v3.pptx" scenarios.
>
> This is **presentation management done right** for the modern era.

---

## Quick Reference Card

| Task | Command |
|------|---------|
| Start new presentation | `git checkout -b <name>` |
| Save progress | `git add . && git commit -m "message"` |
| Export to PDF | `marp file.md --pdf` |
| Update from master | `git checkout <branch> && git rebase master` |
| List all presentations | `git branch -a` |
| Push to GitHub | `git push origin <branch>` |

---

**Version:** 1.0
**Last Updated:** 2025-12-07
**Maintained by:** Your Team