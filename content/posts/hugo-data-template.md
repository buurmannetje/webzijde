---
title: "Hugo Data Template"
slug: hugo-data-template
date: 2023-02-27
tags:
- hugo
- code
---

Hugo has a great option to create a list in YAML format and then show that data in a template. Here is the simplest way to do this.

For this example I am creating a list of movies I've watched.

We need 3 files:

- /content/movies.md
- /data/watched.yml
- /themes/your_theme/layouts/shortcodes/movies-list.html

**/content/movies.md** is the actual **/movies** page on the website that you visit to see the list. So this page can have an intro and some images if you like. It's as simple as crating a normal content page in Hugo, as long as you put this string somewhere in the page: ```{{< movies-list >}}```

### /data/watched.yml
```
- title: "Requiem for a Dream"
  date: "03.01.2023"
  rating: ★★★★

- title: "The Batman"
  date: "01.01.2023"
  rating: ★★★
```

### themes/your_theme_name/layouts/shortcodes/movies-list.html
```
{{ range .Site.Data.watched }}
<movies>
  <div>{{.date}}</div>
  <div>{{.title}}</div>
  <div>{{.rating}}</div>
</movies>
{{ end }}
```
