---
title: "A Post with a Full-Width Hero Image"
date: 2026-04-16T14:00:00Z
draft: false
tags: ["Design", "Images"]
image: "/images/cover.png"
---

This post demonstrates how to feature a beautiful, full-width hero image at the top of your article.

By simply setting the `image` parameter in your post's frontmatter, the theme automatically picks it up and renders it prominently before your content begins. 

## The Frontmatter

To achieve this, your frontmatter should look like this:

```yaml
---
title: "A Post with a Full-Width Hero Image"
date: 2026-04-16T14:00:00Z
draft: false
tags: ["Design", "Images"]
image: "/images/cover.png"
---
```

Our images are stored in a common global directory at `static/images/`. The theme does the heavy lifting of styling the referenced image beautifully across the full width of the viewport, giving your blog a polished, modern aesthetic.
