---
title: "Hugo if .IsHome"
slug: hugo-if-is-home
date: 2022-12-08
tags:
- hugo
- code
---

Let's say you want a menu on your frontpage, and when you click on a post, the single post page shows a different menu.

This is partials/header.html

```
<header>
  
  {{ if .IsHome }}
  
  <nav>
    <a href="/" class="logo">hello.</a>
    <a href="/about">about</a>
    <a href="/uses">uses</a>
  </nav>

  {{ else }}
  
  <nav>
    <a href="/">&#8592;</a>
  </nav>

  {{ end }}

</header>
```

What happens here, is that the {{ if .IsHome }} checks if you are on the homepage. If so, it shows you the menu. The menu that is displayed under the {{ else }} line, is the menu that is shown when you are **not** on the homepage.
