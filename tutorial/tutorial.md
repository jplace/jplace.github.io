# Personal Website Workshop

Personal websites are a fun way to express yourself on the Internet. Plus, they're great for learning web development.

In this tutorial, you will make a [GitHub Page](https://pages.github.com), but this advice is applicable to static sites hosted anywhere.

## Getting started

Make a repository and git init it.

```bash
mkdir jplace.github.io
cd jplace.github.io
git init
```

Create a file called _index.html_. Put some HTML scaffolding in it.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <title>Title goes here</title>
    <style>
      /* css goes here */
    </style>
  </head>
  <body>
    <!-- HTML goes here -->
    <div>Hello, world!</div>
  </body>
</html>
```

Serve the HTML using Python's SimpleHTTPServer. This Python module accepts HTTP requests and responds with file contents matching the requested path.

```bash
python -m SimpleHTTPServer 7999
```

View your site in a browser at [http://localhost:7999/](http://localhost:7999/). Reload the site to see new edits to your HTML.

## Deploying to GitHub

You will need to create a new repository named _username_.github.io, where _username_ is your GitHub username. If the first part of the repository doesn’t exactly match your username, it won’t work, so make sure to get it right.

Create a new repository [here](https://github.com/new).

Commit. Then, follow the instructions to **push an existing repository from the command line**.

```bash
git add --all
git commit -m "First commit"
git remote add origin https://github.com/jplace/jplace.github.io.git
git push -u origin master
```

GitHub will automatically update your hosted site everytime you push to _origin/master_.

## Designing the site

Decide what your site should look like. This is the fun part, but it's also the hardest part.

New web developers often try to design and code at the same time. Don't do this! Coding is hard enough. Draw out your design first (on paper or in your mind).

### Sourcing ideas

Google "personal website design ideas". There's no shortage of examples out there. Find one or two simple ones you like. It's very easy to change color schemes, pick new fonts, or tweak layout.

If you are new to web development, ship something simple first. Put your name, a link to your resume, and a link to any social media. It'll be hard enough to make this look good. If you enjoy working on it, redesign with more content in the future!

If you have previous experience, consider something more ambitious. Include a blurb about yourself, a picture, and links to work you've done. Any work is worth linking to! Written pieces, GitHub projects, music productions, etc.

If you don't want to design your own site, I recommend copying mine: [https://jplace.github.io/](https://jplace.github.io/). View the source of the page or see [my repository](https://github.com/jplace/jplace.github.io/).

### Layout

In HTML, each element has a _display_ value. Make sure you understand the difference between [block and inline](https://www.w3schools.com/html/html_blocks.asp) before starting to code.

Your layout will be almost entirely block elements. You will use inline elements to style text or horizantally-align links.

The layout of elements can be enhanced with modern CSS features: [flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox) and [grid](https://hacks.mozilla.org/2017/10/an-introduction-to-css-grid-layout-part-1/). Reading about them can be tedious and confusing. [Flexbox Froggy](https://flexboxfroggy.com/) and [Grid Garden](http://cssgridgarden.com/) are games to teach you these concepts.

Tip: if you need to vertically-center something, use flexbox or grid.

### Colors

Intelligent use of color is important to a site. I use [Colormind](http://colormind.io/bootstrap/) to generate color schemes. I like that it explains how to use the colors effectively!

You can google "color scheme generators" for other ideas.

### Fonts

I recommend picking just a single font for your site. You can pick two fonts if you want one for headers (like your name) and one for all other text on the page.

[Web safe fonts](https://www.w3schools.com/cssref/css_websafe_fonts.asp) outlines the normal fonts used in websites. These are a very safe bet.

If you're feeling adventurous, [Google fonts](https://fonts.google.com) has tons of more unusual ones to chose from. To use these, include a link to your chosen font in the `<head>` of your page.

```html
<head>
  <link
    href="https://fonts.googleapis.com/css?family=Roboto&display=swap"
    rel="stylesheet"
  />
</head>
```

### Icons

I love [iconmonstr](https://iconmonstr.com/) for free icons. I get my social media badges and little pieces of flair here.

When you can, I recommend using SVGs that are Base64-encode.

```html
<img
  src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij48cGF0aCBkPSJNMjQgNC41NTdjLS44ODMuMzkyLTEuODMyLjY1Ni0yLjgyOC43NzUgMS4wMTctLjYwOSAxLjc5OC0xLjU3NCAyLjE2NS0yLjcyNC0uOTUxLjU2NC0yLjAwNS45NzQtMy4xMjcgMS4xOTUtLjg5Ny0uOTU3LTIuMTc4LTEuNTU1LTMuNTk0LTEuNTU1LTMuMTc5IDAtNS41MTUgMi45NjYtNC43OTcgNi4wNDUtNC4wOTEtLjIwNS03LjcxOS0yLjE2NS0xMC4xNDgtNS4xNDQtMS4yOSAyLjIxMy0uNjY5IDUuMTA4IDEuNTIzIDYuNTc0LS44MDYtLjAyNi0xLjU2Ni0uMjQ3LTIuMjI5LS42MTYtLjA1NCAyLjI4MSAxLjU4MSA0LjQxNSAzLjk0OSA0Ljg5LS42OTMuMTg4LTEuNDUyLjIzMi0yLjIyNC4wODQuNjI2IDEuOTU2IDIuNDQ0IDMuMzc5IDQuNiAzLjQxOS0yLjA3IDEuNjIzLTQuNjc4IDIuMzQ4LTcuMjkgMi4wNCAyLjE3OSAxLjM5NyA0Ljc2OCAyLjIxMiA3LjU0OCAyLjIxMiA5LjE0MiAwIDE0LjMwNy03LjcyMSAxMy45OTUtMTQuNjQ2Ljk2Mi0uNjk1IDEuNzk3LTEuNTYyIDIuNDU3LTIuNTQ5eiIvPjwvc3ZnPg=="
/>
```

### Style tweaks

There's many details that make a site look professional.

#### Box shadows

[Box shadows](https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow) add texture to your flat site. I recommend applying them to images.

```css
box-shadow: 2px 2px 5px grey;
```

#### Line height

The CSS `line-height` property dictates the spaces between lines of text. Increase the line height for subtext that's part of a header.

```html
<h1>Jordan Place</h1>
<p style="line-height: 1.5;">
  At work, I think a lot about how to write code that isn't scary to change
  often. At home, I think a lot about pop music.
</p>
```

#### Gradients

CSS gradients add texture to your site. I suggest [cssgradient.io](https://cssgradient.io/) for designing them.

#### Responsive Design

If your site's CSS supports small screen sizes, add this `<meta>` tag to `<head>`. If it doesn't, omit this tag: mobile devices will try their best to size the webpage so that it looks good.

```html
<head>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
</head>
```

## Other approaches

Some web developers prefer not to write raw CSS. Instead, they adopt CSS frameworks, static site generators, or website builders.

### CSS Frameworks

In my opinion, these are quite hard to use if you don't already know CSS. But, try them out and see if you can make them useful!

#### Light-weight

Light-weight frameworks provide helpers for "common" things in CSS. They lead you to good, responsive designs without dictating how your site should look.

- [tachyons](https://tachyons.io/)
- [skeleton](http://getskeleton.com/)
- [tailwind](https://tailwindcss.com/)
- [bulma](https://bulma.io/)

#### Heavy-weight

Heavy-weight frameworks provide components you'll need to make a site. These include cards, buttons, nav, etc. They very much dictate how your site will look.

- [Bootstrap](https://getbootstrap.com/)
- [Materialize](https://materializecss.com/)
- [Primer](https://primer.style/css/)

### Static site generators

A "static site generator" is a piece of software that injects custom content into an HTML template. It outputs HTML files to be served from your github.io site.

Static site generators are most commonly used for blogs. They generate a page for each blog post without the developer having to maintain HTML on each page individually. They are generally useful for sites with lots of content.

If your personal website will have lots on content, try out [Jekyll with GitHub Pages](https://help.github.com/en/articles/about-github-pages-and-jekyll). You can adopt a pre-made themes for Jekyll to avoid having to write HTML or CSS at all.

### Website builders

You can also google "free website builders" to find drag-n-drop tools for building sites. I have no prior experience with these, so I cannot recommend any.
