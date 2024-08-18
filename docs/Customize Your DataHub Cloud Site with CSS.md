---
title: Customize Your DataHub Cloud Site with CSS
---

## Introduction

In this tutorial, we're going to explore how you can personalise the appearance of your DataHub Cloud site. By the end of this tutorial, you'll learn how to use a `custom.css` file to adjust existing styles and how to add and style a simple hero to your landing page.

### What You'll Need

- GitHub account and basic knowledge of GitHub UI (especially editing and adding files)
- A [DataHub Cloud](https://datahub.io/) site you want to customise.
- Basic knowledge of CSS (or more, depending on what you want to achieve)
- Basic knowledge of browser developer tools.

## Part 1: Adjusting Default Styles with `custom.css`

Here is an example landing page of a site published with DataHub Cloud that we're going to style. You can use any of your DataHub Cloud sites.

![[./assets/css-tutorial-1.png]]

Here is the underlying markdown content:

```md
---
title: My Musings & Memories 🧘‍♀️🏄‍♀️🏔️
description: "Welcome to my personal corner of the web, where I'll be sharing my thoughts, travel experiences, coding projects, and much more!"
date: 2024-04-24]
---

## Recent Posts

- [[/life-lessons-learned|Life Lessons Learned]]
- [[/travel-thailand#Bangkok at Night|Travel to Thailand]]
- [[/blog/javascript-tips|Let's Talk JavaScript]]

## Featured Content

> [!info] Don't forget to check:
> [[/blog/chasing-auroras-norway|Chasing Auroras in Norway]]

---

### Photo of the Week

![[auroras.jpeg]]

---

...
```

### Step 1: Create the `custom.css` File

In the root of your site's GitHub repository, create a file named `custom.css`. 

> [!important]
> If you're site is published from a subfolder of your repository (i.e. you've specified "Root Directory" config field), the `custom.css` file should be placed in that subfolder.

### Step 2: Change Background Colour & Heading Fonts

Now, let's change the background colour and heading fonts a bit.

Add the following CSS rules in your `custom.css` file and commit your changes. Then, go to your DataHub Cloud dashboard and **sync your site**.

```css
/* Change heading fonts and colors */
.bg-background {
    background: #f9f6f1 !important;
}

h1, h2, h3, h4, h5, h6 {
    font-family: "Lucida Console", "Courier New", monospace !important;
    font-weight: bold !important;
}

h1, h4 {
    color: #d30c7b !important;
}

h2, h5 {
    color: #ba5a31 !important;
}

h3, h6 {
    color: #508484 !important;
}
```

> [!note]
> Note, that we needed to override the existing styles with `!important ` rule. This may not be needed each time, but if you're trying to tweak some styles and there is no effect, you may need to use it.

Here is the end result on our example page. Pretty nice, huh?

![[./assets/css-tutorial-2.png]]

### Step 3: Style Anything You Want

This was just a basic example of tweaking css on your DataHub Cloud site. But you can style virtually anything you can see on your page. You just need to find out how to properly "select" the HTML element you want to style in your `custom.css`. 

> [!note] Disclaimer
> This is not a tutorial on CSS and CSS selectors, so you need to do your own research here 😉

## Part 2: Adding a Simple HTML Hero

Did you know that you can include HTML tags in your markdown? If not, let me show you how.
Then, you'll be able to use the knowledge from Part 1 and style those elements too!

Let's try replacing the current header (title, description, and date) in our example with a simple hero element.

#### Step 1: Add a Simple HTML Hero

Let's replace the current frontmatter with the following HTML snippet:

```html
<div class="hero">
    <h1 class="hero-title">My Musings & Memories<br/>🧘‍♀️🏄‍♀️🏔️</h1>
    <p class="hero-description">Welcome to my personal corner of the web, where I'll be sharing my thoughts, travel experiences, coding projects, and much more!</p>
    <a href="/blog" class="hero-button">See my blog</a>
</div>
```

The markdown file now looks like this:

```md
<div class="hero">
    <h1 class="hero-title">My Musings & Memories 🧘‍♀️🏄‍♀️🏔️</h1>
    <p class="hero-description">Welcome to my personal corner of the web, where I'll be sharing my thoughts, travel experiences, coding projects, and much more!</p>
    <a href="/blog" class="hero-button">See my blog</a>
</div>

## Recent Posts

- [[/life-lessons-learned|Life Lessons Learned]]
- [[/travel-thailand#Bangkok at Night|Travel to Thailand]]
- [[/blog/javascript-tips|Let's Talk JavaScript]]

## Featured Content

> [!info] Don't forget to check:
> [[/blog/chasing-auroras-norway|Chasing Auroras in Norway]]

---

### Photo of the Week

![[auroras.jpeg]]

---
```

Now, commit your changes.

### Step 2: Style Your Hero with `custom.css`

Back in your `custom.css` file, add the following styles (or other!) for your custom hero section:

```css
...

.hero {
  background-color: #508484;
  height: 500px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  color: #fff;
  padding: 0 36px;
}

.hero-title {
  font-size: 4rem;
    color: #E35AA6 !important;
    margin-bottom: 0px;
}

.hero-description {
  font-size: 1.5rem;
  margin-bottom: 30px;
}

.hero-button {
  background-color: #fff;
  color: #333;
  padding: 10px 20px;
  border-radius: 5px;
  text-decoration: none;
  font-weight: bold;
  transition: all 0.3s ease-in-out;
}

.hero-button:hover {
  background-color: #D679AC;
  color: #fff;
}
```

Once again, commit your changes. Now, head to your DataHub Cloud dashboard and **sync your site**. Now you can refresh your browser and you should see your landing page with the styled hero. Our example looks like this:

![[./assets/css-tutorial-3.png]]

You can also add this extra hack to make the hero break out of the parent container and span the whole site width:

```css
.hero {
  ...
  margin: 0 calc(min(28rem - 1.5rem - 50vw, 0px));
  margin-top: -3rem;
}
```

![[./assets/css-tutorial-4.png]]

## Conclusion

Congratulations! You've just learned how to customize the appearance of your DataHub Cloud site using a `custom.css` file for subtle and not-so-subtle tweaks of your sites style. Explore, experiment, and most importantly, have fun designing your site.

---

If you encounter any issues or have questions, the DataHub Cloud community and support team are here to help.

Happy styling!


