---
title: "Handling Local Images in Hugo"
date: 2026-04-16T12:00:00Z
draft: false
tags: ["Hugo", "Images", "Tutorial"]
---

One of the most common ways to manage images in Hugo is by using the global `static/` directory.

By putting all of your images in the `static/images` folder, you can keep a centralized repository of all site media, making it easy to reuse the same images across multiple different posts!

## Example: A Local Image

Here is an image of a sleek server rack that is stored locally in the `static/images` directory:

![A modern server rack with glowing blue LED lights](/images/server-rack.png)

### How it works

The structure of the site looks like this:

```text
├── content/
│   └── posts/
│       └── handling-local-images.md  <-- This file
└── static/
    └── images/
        └── server-rack.png           <-- The image shown above
```

In the markdown file, we simply reference the image by its absolute path relative to the `static/` folder:

```markdown
![A modern server rack with glowing blue LED lights](/images/server-rack.png)
```

Hugo automatically serves files from the `static/` directory at the root URL path when building the site. It's that easy!
