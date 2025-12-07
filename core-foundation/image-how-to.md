[View source on Github](https://github.com/marp-team/marpit)

# [![Marpit](https://marpit.marp.app/marpit.png)](https://marpit.marp.app/)

- [Introduction](https://marpit.marp.app/ "Introduction")
- [Usage](https://marpit.marp.app/usage "Usage")
- [Marpit Markdown](https://marpit.marp.app/markdown "Marpit Markdown")
  - [Directives](https://marpit.marp.app/directives "Directives")
  - [Image syntax](https://marpit.marp.app/image-syntax "Image syntax")
    - [Resizing image](https://marpit.marp.app/image-syntax?id=resizing-image "Resizing image")
    - [Image filters](https://marpit.marp.app/image-syntax?id=image-filters "Image filters")
    - [Slide backgrounds](https://marpit.marp.app/image-syntax?id=slide-backgrounds "Slide backgrounds")

      - [Background size](https://marpit.marp.app/image-syntax?id=background-size "Background size")

    - [Advanced backgrounds](https://marpit.marp.app/image-syntax?id=advanced-backgrounds "Advanced backgrounds")

      - [Multiple backgrounds](https://marpit.marp.app/image-syntax?id=multiple-backgrounds "Multiple backgrounds")
      - [Split backgrounds](https://marpit.marp.app/image-syntax?id=split-backgrounds "Split backgrounds")
  - [Fragmented list](https://marpit.marp.app/fragmented-list "Fragmented list")
- [Theme CSS](https://marpit.marp.app/theme-css "Theme CSS")
- [Inline SVG slide](https://marpit.marp.app/inline-svg "Inline SVG slide")

* * *

- [![Marpit API](https://icongr.am/material/open-in-new.svg?size=24&color=808080)Marpit API (JSDoc)](https://marpit-api.marp.app/ "Marpit API (JSDoc)")
- [![GitHub](https://icongr.am/material/github.svg?size=24&color=808080)GitHub](https://github.com/marp-team/marpit "GitHub")
- [![npm](https://icongr.am/material/npm.svg?size=24&color=808080)npm ![](https://img.shields.io/npm/v/@marp-team/marpit.svg?style=flat-square&label=&colorB=888)](https://www.npmjs.com/package/@marp-team/marpit "npm ")

# [Image syntax](https://marpit.marp.app/image-syntax?id=image-syntax)

Marpit has extended Markdown image syntax `![](image.jpg)` to help create beautiful slides.

| Features | Inline image | [Slide BG](https://marpit.marp.app/image-syntax?id=slide-backgrounds) | [Advanced BG](https://marpit.marp.app/image-syntax?id=advanced-backgrounds) |
| :-: | :-: | :-: | :-: |
| [Resizing by keywords](https://marpit.marp.app/image-syntax?id=resizing-image) | `auto` only | ![heavy_check_mark](https://github.githubassets.com/images/icons/emoji/heavy_check_mark.png) | ![heavy_check_mark](https://github.githubassets.com/images/icons/emoji/heavy_check_mark.png) |
| [Resizing by percentage](https://marpit.marp.app/image-syntax?id=resizing-image) | ![x](https://github.githubassets.com/images/icons/emoji/x.png) | ![heavy_check_mark](https://github.githubassets.com/images/icons/emoji/heavy_check_mark.png) | ![heavy_check_mark](https://github.githubassets.com/images/icons/emoji/heavy_check_mark.png) |
| [Resizing by length](https://marpit.marp.app/image-syntax?id=resizing-image) | ![heavy_check_mark](https://github.githubassets.com/images/icons/emoji/heavy_check_mark.png) | ![heavy_check_mark](https://github.githubassets.com/images/icons/emoji/heavy_check_mark.png) | ![heavy_check_mark](https://github.githubassets.com/images/icons/emoji/heavy_check_mark.png) |
| [Image filters](https://marpit.marp.app/image-syntax?id=image-filters) | ![heavy_check_mark](https://github.githubassets.com/images/icons/emoji/heavy_check_mark.png) | ![x](https://github.githubassets.com/images/icons/emoji/x.png) | ![heavy_check_mark](https://github.githubassets.com/images/icons/emoji/heavy_check_mark.png) |
| [Multiple backgrounds](https://marpit.marp.app/image-syntax?id=multiple-backgrounds) | - | ![x](https://github.githubassets.com/images/icons/emoji/x.png) | ![heavy_check_mark](https://github.githubassets.com/images/icons/emoji/heavy_check_mark.png) |
| [Split backgrounds](https://marpit.marp.app/image-syntax?id=split-backgrounds) | - | ![x](https://github.githubassets.com/images/icons/emoji/x.png) | ![heavy_check_mark](https://github.githubassets.com/images/icons/emoji/heavy_check_mark.png) |

The extended features are enabled by including corresponding keywords in the image’s alternative text; the remaining alternative text is rendered as alt text for inline images or the figure caption for background images.

### [Resizing image](https://marpit.marp.app/image-syntax?id=resizing-image)

You can resize image by using `width` and `height` keyword options.

```markdown
![width:200px](image.jpg) <!-- Setting width to 200px -->
![height:30cm](image.jpg) <!-- Setting height to 300px -->
![width:200px height:30cm](image.jpg) <!-- Setting both lengths -->Copy to clipboardErrorCopied
```

We also support the shorthand options `w` and `h`. Normally it’s useful to use these.

```markdown
![w:32 h:32](image.jpg) <!-- Setting size to 32x32 px -->Copy to clipboardErrorCopied
```

Inline images _only allow `auto` keyword and the length units defined in CSS._

Several units related to the size of the viewport (e.g. `vw`, `vh`, `vmin`, `vmax`) cannot use to ensure immutable render result.

### [Image filters](https://marpit.marp.app/image-syntax?id=image-filters)

You can apply [CSS filters](https://developer.mozilla.org/en-US/docs/Web/CSS/filter) to image through markdown image syntax. Include `<filter-name>(:<param>(,<param>...))` to the alternate text of image.

Filters can use in the inline image and [the advanced backgrounds](https://marpit.marp.app/image-syntax?id=advanced-backgrounds).

| Markdown | w/ arguments |
| --- | --- |
| `![blur]()` | `![blur:10px]()` |
| `![brightness]()` | `![brightness:1.5]()` |
| `![contrast]()` | `![contrast:200%]()` |
| `![drop-shadow]()` | `![drop-shadow:0,5px,10px,rgba(0,0,0,.4)]()` |
| `![grayscale]()` | `![grayscale:1]()` |
| `![hue-rotate]()` | `![hue-rotate:180deg]()` |
| `![invert]()` | `![invert:100%]()` |
| `![opacity]()` | `![opacity:.5]()` |
| `![saturate]()` | `![saturate:2.0]()` |
| `![sepia]()` | `![sepia:1.0]()` |

Marpit will use the default arguments shown in above when you omit arguments.

Naturally multiple filters can apply to a image.

```markdown
![brightness:.8 sepia:50%](https://example.com/image.jpg)Copy to clipboardErrorCopied
```

## [Slide backgrounds](https://marpit.marp.app/image-syntax?id=slide-backgrounds)

We provide a background image syntax to specify a slide’s background through Markdown. It only has to include `bg` keyword to the alternate text.

```markdown
![bg](https://example.com/background.jpg)Copy to clipboardErrorCopied
```

When you defined two or more background images in a slide, Marpit will show the last defined image only. If you want to show multiple images, try [the advanced backgrounds](https://marpit.marp.app/image-syntax?id=advanced-backgrounds) by enabling [inline SVG slide](https://marpit.marp.app/inline-svg).

### [Background size](https://marpit.marp.app/image-syntax?id=background-size)

You can resize the background image by keywords. The keyword value basically follows [`background-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-size) style.

```markdown
![bg contain](https://example.com/background.jpg)Copy to clipboardErrorCopied
```

| Keyword | Description | Example |
| --: | :-- | :-- |
| `cover` | Scale image to fill the slide. _(Default)_ | `![bg cover](image.jpg)` |
| `contain` | Scale image to fit the slide. | `![bg contain](image.jpg)` |
| `fit` | Alias to `contain`, compatible with Deckset. | `![bg fit](image.jpg)` |
| `auto` | Not scale image, and use the original size. | `![bg auto](image.jpg)` |
| _`x%`_ | Specify the scaling factor by percentage value. | `![bg 150%](image.jpg)` |

You also can continue to use [`width` (`w`) and `height` (`h`) option keywords](https://marpit.marp.app/image-syntax?id=resizing-image) to specify size by length.

## [Advanced backgrounds](https://marpit.marp.app/image-syntax?id=advanced-backgrounds)

📐 It will work only in experimental [inline SVG slide](https://marpit.marp.app/inline-svg).

The advanced backgrounds support [multiple backgrounds](https://marpit.marp.app/image-syntax?id=multiple-backgrounds), [split backgrounds](https://marpit.marp.app/image-syntax?id=split-backgrounds), and [image filters for background](https://marpit.marp.app/image-syntax?id=image-filters).

### [Multiple backgrounds](https://marpit.marp.app/image-syntax?id=multiple-backgrounds)

```markdown
![bg](https://fakeimg.pl/800x600/0288d1/fff/?text=A)
![bg](https://fakeimg.pl/800x600/02669d/fff/?text=B)
![bg](https://fakeimg.pl/800x600/67b8e3/fff/?text=C)Copy to clipboardErrorCopied
```

[![Multiple backgrounds](https://raw.githubusercontent.com/marp-team/marpit/main/docs/assets/image-syntax/multiple-bg.png)](https://marpit.marp.app/assets/image-syntax/multiple-bg.png)

These images will arrange in a horizontal row.

#### [Direction keyword](https://marpit.marp.app/image-syntax?id=direction-keyword)

You may change alignment direction from horizontal to vertical, by using `vertical` direction keyword.

```markdown
![bg vertical](https://fakeimg.pl/800x600/0288d1/fff/?text=A)
![bg](https://fakeimg.pl/800x600/02669d/fff/?text=B)
![bg](https://fakeimg.pl/800x600/67b8e3/fff/?text=C)Copy to clipboardErrorCopied
```

[![Multiple backgrounds with vertical direction](https://raw.githubusercontent.com/marp-team/marpit/main/docs/assets/image-syntax/multiple-bg-vertical.png)](https://marpit.marp.app/assets/image-syntax/multiple-bg-vertical.png)

### [Split backgrounds](https://marpit.marp.app/image-syntax?id=split-backgrounds)

The `left` or `right` keyword with `bg` keyword make a space for the background to the specified side. It has a half of slide size, and the space of a slide content will shrink too.

```markdown
![bg left](https://picsum.photos/720?image=29)

# Split backgrounds

The space of a slide content will shrink to the right side.Copy to clipboardErrorCopied
```

[![Split backgrounds](https://raw.githubusercontent.com/marp-team/marpit/main/docs/assets/image-syntax/split-background.jpg)](https://marpit.marp.app/assets/image-syntax/split-background.jpg)

Multiple backgrounds will work well in the specified background side.

```markdown
![bg right](https://picsum.photos/720?image=3)
![bg](https://picsum.photos/720?image=20)

# Split + Multiple BGs

The space of a slide content will shrink to the left side.Copy to clipboardErrorCopied
```

[![Split + Multiple BGs](https://raw.githubusercontent.com/marp-team/marpit/main/docs/assets/image-syntax/split-multiple-bg.jpg)](https://marpit.marp.app/assets/image-syntax/split-multiple-bg.jpg)

This feature is similar to [Deckset’s Split Slides](https://docs.decksetapp.com/English.lproj/Media/01-background-images.html#split-slides).

Marpit uses a last defined keyword in a slide when `left` and `right` keyword is mixed in the same slide by using multiple backgrounds.

#### [Split size](https://marpit.marp.app/image-syntax?id=split-size)

Marpit can specify split size for background by percentage like `left:33%`.

```markdown
![bg left:33%](https://picsum.photos/720?image=27)

# Split backgrounds with specified sizeCopy to clipboardErrorCopied
```

[![Split backgrounds with specified size](https://raw.githubusercontent.com/marp-team/marpit/main/docs/assets/image-syntax/split-bg-with-size.jpg)](https://marpit.marp.app/assets/image-syntax/split-bg-with-size.jpg)

[PREVIOUS\\
\\
Directives](https://marpit.marp.app/directives)

[NEXT\\
\\
Fragmented list](https://marpit.marp.app/fragmented-list)