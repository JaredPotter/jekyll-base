## 1. (Setup) `bundle init`

Creates Gemfile

## 2. Add `gem "jekyll"` to Gemfile

## 3. Run `bundle` to install Jekyll

Generates a `Gemfile.lock`

## 4. Create an `index.html` file w/ base HTML5 and h1 "Hello, World"

## 5. Build / Serve

build -> `bundle exec jekyll build`

Generates `_site` folder containing your production site

serve -> `bundle exec jekyll serve`

Starts a dev server w/ hot-reloading for nice DX

http://localhost:4000

## 6. (Liquid) objects, tags, and filters

`{{ page.title }}` Object

`{% if page.show_ %}` Tags

`{{ "Hi" | capitalize }}` Filters

Update Hello World
to this
`<h1>{{ "Hello World!" | downcase }}</h1>`

## 7. (Front Matter) Set variables for page

Add to top of `index.html`

```
---
# front matters
title: Home - Jared Potter
---
```

## 8. (Layouts)

Create a folder called `_layouts`

and create a `default.html` file.

```
<!doctype html>
<html>
  <head>
    <meta charset="utf-8">
    <title>{{ page.title }}</title>
  </head>
  <body>
    {{ content }}
  </body>
</html>
```

And update `index.html` to

```
---
# front matters
layout: default
title: Home - Jared Potter
---
<h1>
    {{ "Hello World!" | downcase }}
</h1>
```

## 9. (Includes) Allows content to be included from other files stored in `_includes` directory

Create `_includes` folder

Create `navigation.html`

```
<nav>
  <a href="/">Home</a>
  <a href="/blog.html">Blog</a>
</nav>
```

Inside `_layouts/default.html`

Change body to

```
  <body>
    {% include navigation.html %}
    {{ content }}
  </body>
```

Update `_includes/navigation.html` to add highlighting

```
<nav>
  <a href="/" {% if page.url == "/" %}style="color: red;"{% endif %}>
    Home
  </a>
  <a href="/blog.html" {% if page.url == "/blog.html" %}style="color: red;"{% endif %}>
    Blog
  </a>
</nav>
```

## 10. (Data Files)

todo: finish

## 11. (Assets)

todo: finish

## 12. (Blogging)

todo: finish

## 13. (Collections)

todo: finish

## 14. (Deployment)
