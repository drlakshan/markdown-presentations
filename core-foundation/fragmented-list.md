[View source on Github](https://github.com/marp-team/marpit)

# [![Marpit](https://marpit.marp.app/marpit.png)](https://marpit.marp.app/)

- [Introduction](https://marpit.marp.app/ "Introduction")
- [Usage](https://marpit.marp.app/usage "Usage")
- [Marpit Markdown](https://marpit.marp.app/markdown "Marpit Markdown")
  - [Directives](https://marpit.marp.app/directives "Directives")
    - [Usage](https://marpit.marp.app/directives?id=usage "Usage")

      - [HTML comment](https://marpit.marp.app/directives?id=html-comment "HTML comment")
      - [Front-matter](https://marpit.marp.app/directives?id=front-matter "Front-matter")

    - [Type of directives](https://marpit.marp.app/directives?id=type-of-directives "Type of directives")
    - [Global directives](https://marpit.marp.app/directives?id=global-directives-1 "Global directives")

      - [Theme](https://marpit.marp.app/directives?id=theme "Theme")
      - [Heading divider](https://marpit.marp.app/directives?id=heading-divider "Heading divider")

    - [Local directives](https://marpit.marp.app/directives?id=local-directives-1 "Local directives")

      - [Pagination](https://marpit.marp.app/directives?id=pagination "Pagination")
      - [Header and footer](https://marpit.marp.app/directives?id=header-and-footer "Header and footer")
      - [Styling slide](https://marpit.marp.app/directives?id=styling-slide "Styling slide")

    - [Advanced](https://marpit.marp.app/directives?id=advanced "Advanced")

      - [Custom directives](https://marpit.marp.app/directives?id=custom-directives "Custom directives")
  - [Image syntax](https://marpit.marp.app/image-syntax "Image syntax")
  - [Fragmented list](https://marpit.marp.app/fragmented-list "Fragmented list")
- [Theme CSS](https://marpit.marp.app/theme-css "Theme CSS")
- [Inline SVG slide](https://marpit.marp.app/inline-svg "Inline SVG slide")

* * *

- [![Marpit API](https://icongr.am/material/open-in-new.svg?size=24&color=808080)Marpit API (JSDoc)](https://marpit-api.marp.app/ "Marpit API (JSDoc)")
- [![GitHub](https://icongr.am/material/github.svg?size=24&color=808080)GitHub](https://github.com/marp-team/marpit "GitHub")
- [![npm](https://icongr.am/material/npm.svg?size=24&color=808080)npm ![](https://img.shields.io/npm/v/@marp-team/marpit.svg?style=flat-square&label=&colorB=888)](https://www.npmjs.com/package/@marp-team/marpit "npm ")

# [Directives](https://marpit.marp.app/directives?id=directives)

Marpit Markdown uses extended syntax called **“Directives”** to support writing awesome slides. It can control your slide-deck theme, page number, header, footer, style, and so on.

## [Usage](https://marpit.marp.app/directives?id=usage)

The written directives would parse as [YAML](http://yaml.org/).

When the value includes YAML special chars, you should wrap with quotes to be recognized correctly. You may enable a loose parsing by [`looseYAML` Marpit constructor option](https://marpit-api.marp.app/marpit) if you want.

### [HTML comment](https://marpit.marp.app/directives?id=html-comment)

```markdown
<!--
theme: default
paginate: true
-->Copy to clipboardErrorCopied
```

The HTML comment is also used for [presenter notes](https://marpit.marp.app/usage?id=presenter-notes). When it is parsed as a directive, it would not be collected in the `comments` result of `Marpit.render()`.

### [Front-matter](https://marpit.marp.app/directives?id=front-matter)

Marpit also supports [YAML front-matter](https://jekyllrb.com/docs/frontmatter/), that is a syntax often used for keeping metadata of Markdown. It must be the first thing of Markdown, and between the dash rulers.

```markdown
---
theme: default
paginate: true
---Copy to clipboardErrorCopied
```

Please not confuse to the ruler for paging slides. The actual slide contents would start after the ending ruler of front-matter.

## [Type of directives](https://marpit.marp.app/directives?id=type-of-directives)

### [Global directives](https://marpit.marp.app/directives?id=global-directives)

Global directives are _the setting value of the whole slide deck_ such as theme. Marpit recognizes only the last value if you wrote a same global directives many times.

`$` prefix for global directives has removed in v1.4.0. Developer may re-define dollar-prefixed [custom directives](https://marpit.marp.app/directives?id=custom-directives) as an alias to built-in directive if necessary.

### [Local directives](https://marpit.marp.app/directives?id=local-directives)

Local directives are _the setting value per slide pages._ These would apply to **defined page and following pages.**

```markdown
<!-- backgroundColor: aqua -->

This page has aqua background.

---

The second page also has same color.Copy to clipboardErrorCopied
```

#### [Apply to a single page (Spot directives)](https://marpit.marp.app/directives?id=apply-to-a-single-page-spot-directives)

If you want to apply local directives only to the current page, you have to add the prefix `_` to the name of directives.

```markdown
<!-- _backgroundColor: aqua -->

Add underscore prefix `_` to the name of local directives.

---

The second page would not apply setting of directives.Copy to clipboardErrorCopied
```

#### [Diagram](https://marpit.marp.app/directives?id=diagram)

[![Diagram](https://marpit.marp.app/assets/directives.png)](https://marpit.marp.app/assets/directives.png)

* * *

## [Global directives](https://marpit.marp.app/directives?id=global-directives-1)

| Name | Description |
| :-- | :-- |
| `headingDivider` | Specify heading divider option. |
| `lang` | Set the value of [`lang` attribute](https://developer.mozilla.org/docs/Web/HTML/Global_attributes/lang) for each slide |
| `style` | Specify CSS for tweaking theme. |
| `theme` | Specify theme of the slide deck. |

### [Theme](https://marpit.marp.app/directives?id=theme)

Choose a theme with `theme` global directive.

```markdown
<!-- theme: registered-theme-name -->Copy to clipboardErrorCopied
```

It recognizes the name of theme added to [`themeSet` of `Marpit` instance](https://marpit-api.marp.app/marpit#themeSet).

#### [Tweak theme style](https://marpit.marp.app/directives?id=tweak-theme-style)

Normally [you may tweak theme by `<style>` element](https://marpit.marp.app/theme-css?id=tweak-style-through-markdown), but it might break a style for documentation when opening in another Markdown editor. Thus you can use `style` global directive instead of `<style>`.

```markdown
---
theme: base-theme
style: |
  section {
    background-color: #ccc;
  }
---Copy to clipboardErrorCopied
```

### [Heading divider](https://marpit.marp.app/directives?id=heading-divider)

You may instruct to divide slide pages automatically at before of headings by using `headingDivider` global directive. This feature is similar to [Pandoc](https://pandoc.org/)‘s [`--slide-level` option](https://pandoc.org/MANUAL.html#structuring-the-slide-show) and [Deckset 2](https://www.deckset.com/2/)‘s “Slide Dividers” option.

It have to specify heading level from 1 to 6, or array of them. This feature is enabled at headings whose the level _larger than or equal to the specified value_ if in a number, and it is enabled at _only specified levels_ if in array.

For example, the below two Markdowns have the same output.

#### [Regular syntax](https://marpit.marp.app/directives?id=regular-syntax)

```markdown
# 1st page

The content of 1st page

---

## 2nd page

### The content of 2nd page

Hello, world!

---

# 3rd page

😃Copy to clipboardErrorCopied
```

#### [Heading divider](https://marpit.marp.app/directives?id=heading-divider-1)

```markdown
<!-- headingDivider: 2 -->

# 1st page

The content of 1st page

## 2nd page

### The content of 2nd page

Hello, world!

# 3rd page

😃Copy to clipboardErrorCopied
```

It is useful when you want to create a slide deck from a plain Markdown. Even if you opened Markdown that is using `headingDivider` in general editor, it keeps a beautiful rendering with no unsightly rulers.

[`Marpit` constructor](https://marpit-api.marp.app/marpit) can set a default level of heading divider.

## [Local directives](https://marpit.marp.app/directives?id=local-directives-1)

| Name | Description |
| :-- | :-- |
| `paginate` | Show page number on the slide if you set `true`. |
| `header` | Specify the content of slide header. |
| `footer` | Specify the content of slide footer. |
| `class` | Specify HTML class of slide’s `<section>` element. |
| `backgroundColor` | Setting `background-color` style of slide. |
| `backgroundImage` | Setting `background-image` style of slide. |
| `backgroundPosition` | Setting `background-position` style of slide. |
| `backgroundRepeat` | Setting `background-repeat` style of slide. |
| `backgroundSize` | Setting `background-size` style of slide. |
| `color` | Setting `color` style of slide. |

### [Pagination](https://marpit.marp.app/directives?id=pagination)

We support pagination by the `paginate` local directive.

```markdown
<!-- paginate: true -->

You would be able to see a page number of slide in the lower right.Copy to clipboardErrorCopied
```

#### [Configuring pagination](https://marpit.marp.app/directives?id=configuring-pagination)

There are 2 things happening on each slide:

- the page number is rendered _and_
- the page number is being incremented.

You can control both of these with the `paginate` directive:

| `paginate` | Page number | Increment |
| --- | --- | --- |
| `true` | Show | Yes |
| `false` | Hide | Yes |
| `hold` | Show | No |
| `skip` | Hide | No |

#### [Skip pagination on title slide](https://marpit.marp.app/directives?id=skip-pagination-on-title-slide)

A common use case is excluding the title slide from pagination.
For this you simply have to define the `paginate` directive on the second page instead of the first.

```markdown
# Title slide

This page will not have pagination by lack of the `paginate` directive.

---

<!-- paginate: true -->

Pagination will render from this slide onwards (starting at 2).Copy to clipboardErrorCopied
```

Or you can use the spot directive.

```markdown
---
paginate: true
_paginate: false # or use `_paginate: skip`
---Copy to clipboardErrorCopied
```

#### [`paginate: skip` and `paginate: hold`](https://marpit.marp.app/directives?id=paginate-skip-and-paginate-hold)

To both exclude a page from pagination and hide the pagination at the same time use `skip`:

```markdown
<!-- _paginate: skip -->

# Slide to exclude

This page will not update the page number and also not show the paginationCopy to clipboardErrorCopied
```

You can exclude a page from pagination but keep the pagination visible using `hold`:

```markdown
---
paginate: true
---

# Slide 1

[](./assets/image_01.png)

> Page 1 of 1

---

<!-- _paginate: hold -->

# Slide 2

[](./assets/image_02.png)

> Page 1 of 1Copy to clipboardErrorCopied
```

### [Header and footer](https://marpit.marp.app/directives?id=header-and-footer)

When you have to be shown the same content across multiple slides like a title of the slide deck, you may use `header` or `footer` local directives.

```markdown
---
header: 'Header content'
footer: 'Footer content'
---

# Page 1

---

## Page 2Copy to clipboardErrorCopied
```

It will render to HTML like this:

```html
<section>
  <header>Header content</header>
  <h1>Page 1</h1>
  <footer>Footer content</footer>
</section>
<section>
  <header>Header content</header>
  <h2>Page 2</h2>
  <footer>Footer content</footer>
</section>Copy to clipboardErrorCopied
```

The content will be wrapped by a corresponding element, and insert to a right place of each slide. These could see as the part of slide contents.

If you want to place these contents to the marginal of the slide as like as PowerPoint, _you have to use supported theme._

#### [Formatting](https://marpit.marp.app/directives?id=formatting)

In addition, you can format the content of header/footer through markdown syntax and insert inline images.

```markdown
---
header: '**bold** _italic_'
footer: '![image](https://example.com/image.jpg)'
---

NOTE: Wrap by (double-)quotes to avoid parsed as invalid YAML.Copy to clipboardErrorCopied
```

You cannot use [`![bg]()` syntax](https://marpit.marp.app/image-syntax?id=slide-backgrounds) in `header` and `footer` directives due to the parsing order of Markdown.

### [Styling slide](https://marpit.marp.app/directives?id=styling-slide)

#### [Class](https://marpit.marp.app/directives?id=class)

At the some page, you might think want to change the layout, theme color, and so on. `class` local directive can change a class attribute of `<section>` element of slide page.

Let’s say you’re using a theme includes a rule like this:

```css
section.lead h1 {
  text-align: center;
}Copy to clipboardErrorCopied
```

You could use the centered leading header by setting `class` spot directive to `lead`.

```markdown
<!-- _class: lead -->

# THE LEADING HEADERCopy to clipboardErrorCopied
```

#### [Backgrounds](https://marpit.marp.app/directives?id=backgrounds)

If you want to use any color or the gradient as background, you can set style through `backgroundColor` or `backgroundImage` local directives.

```markdown
<!-- backgroundImage: "linear-gradient(to bottom, #67b8e3, #0288d1)" -->

Gradient background

---

<!--
_backgroundColor: black
_color: white
-->

Black background + White textCopy to clipboardErrorCopied
```

In addition, we have supported customize for these declarations:

- `backgroundColor`
- `backgroundImage`
- `backgroundPosition` (`center` by default)
- `backgroundRepeat` (`no-repeat` by default)
- `backgroundSize` (`cover` by default)
- `color`

It also can use [extended image syntax](https://marpit.marp.app/image-syntax?id=slide-backgrounds) if you want to set image or color as background to single page.

## [Advanced](https://marpit.marp.app/directives?id=advanced)

### [Custom directives](https://marpit.marp.app/directives?id=custom-directives)

Developer can extend recognizable directives. For example, [Marp Core](https://github.com/marp-team/marp-core) has extended `size` global directive to change slide size in Markdown. [Marp CLI](https://github.com/marp-team/marp-cli) will add directives for setting [meta properties of converted HTML](https://github.com/marp-team/marp-cli#metadata).

Marpit instance has [`customDirectives.global` and `customDirectives.local` object](https://marpit-api.marp.app/marpit#customDirectives) to allow adding directives as you like.

#### [Custom global directive](https://marpit.marp.app/directives?id=custom-global-directive)

The following example is defining dollar-prefixed alias of built-in [`theme` global directive](https://marpit.marp.app/directives?id=theme).

```javascript
marpit.customDirectives.global.$theme = (value, marpit) => {
  return { theme: value }
}Copy to clipboardErrorCopied
```

Please define a function to handle passed value from Markdown. The first argument is the passed value(s), and the second is the current Marpit instance. It should return an object includes pairs of key-value for passing to same kind directives.

#### [Custom local directive](https://marpit.marp.app/directives?id=custom-local-directive)

Custom directives also can provide a way of assigning multiple same kind directives at once. Let’s define `colorPreset` local directive for assigning preset of slide colors.

```javascript
marpit.customDirectives.local.colorPreset = (value, marpit) => {
  switch (value) {
    case 'sunset':
      return { backgroundColor: '#e62e00', color: '#fffff2' }
    case 'dark':
      return { backgroundColor: '#303033', color: '#f8f8ff' }
    default:
      // Return an empty object if not have to assign new values
      return {}
  }
}Copy to clipboardErrorCopied
```

Now you can use the defined `colorPreset` local directive with same way of built-in local directives. The underscore prefix (`_colorPreset`) for applying preset to single slide also works well.

```markdown
<!-- colorPreset: sunset -->

# Sunset color preset

---

<!-- _colorPreset: dark -->

# Dark color preset

---

# Sunset color presetCopy to clipboardErrorCopied
```

The returned key-value will assign to `marpitDirectives` property in [`meta` object](https://markdown-it.github.io/markdown-it/#Token.prototype.meta) of predetermined markdown-it token(s) by the kind of directive. It would be useful for using assigned value in [markdown-it plugin](https://marpit.marp.app/usage?id=extend-marpit-by-plugins).

[PREVIOUS\\
\\
Marpit Markdown](https://marpit.marp.app/markdown)

[NEXT\\
\\
Image syntax](https://marpit.marp.app/image-syntax)