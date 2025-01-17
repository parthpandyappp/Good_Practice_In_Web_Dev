# Good_Practice_In_Web_Dev

// structure of the blog

1. what are the good practices?
2. what will it change?
3. tell me some examples.

## What is good practice?

To make sure quality user experience, it is necessary that your website displayed correctly across all the device. In order to achive this, we need to write code which is scalable and gives the same output for all the devices.

## what will it change?

<!-- more -->

## Tell me Some examples

Here you go...

1. ### **Don’t Use Divs for Everything**

Most of the time, when creating elements, we tend to use `div` element to wrap the header, footer, or navbar. When screen reader or similar assistive technology use to read webpage, it can not translate that `div` element to header section or main section or footer section. So instead of doing that, try writing semantic tags like `<main>`, `<nav>`, `<header>`, `<section>`, `<article>` etc.

Below is an example code for how sementic websites should look like.

```HTML
<html>
    <head>
        ...
    </head>
    <body>
        <nav>
            ...
        </nav>
        <main>
            <header>
                ...
            </header>
            <section>
                ...
            </section>
        </main>
        <footer>
            ...
        </footer>
    </body>
</html>
```

---

2. ### **Using The Right Doctype**

Doctype defines which version of HTML you are suing in your website. It helps web broswer to understand html version and render the web pages accordingly. A wrong declaration of doctype can lead to break the website in some browsers.

Always use right declaration for doctype. For html5 correct doctype is mentioned below.

_TIP : doctype declaration is not case sensitive._

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Title of the document</title>
  </head>

  <body>
    The content of the document......
  </body>
</html>
```

---

3. ### **Mention the language attribute**

Language attribute helps in the correct pronunciation of sentences when browsers are using screen readers. Screen readers generally load the language library in which they want to pronounce. However, insufficient language attributes can lead to selecting the default language as English and mispronouncing the word.

Add lang attribute in `<html>` to use the power of screen readers.

```html
<html lang="en">
  ...
</html>
```

---

4. ### **Have an alt**

What to do when you are showing your website and image failed to load on your friends phone? Have an alt, yes you read it right have an `alt` attribute in `<img>` element. `alt` attributes used as placeholders when your image is failed to load. So next time dont forget to _have an alt_.

Here is how you add an alt attribute.

```html
<img alt="Audits set-up in Chrome DevTools" src="..." />
```

**Tips for writing alt**

- `alt` text should give the intent, purpose, and meaning of the image.
- Blind users should get as much information from alt text as a sighted user gets from the image.
- Avoid non-specific words like "chart", "image", or "diagram".

---

5. ### **Incorrect aspect ratio**

remeber when you are writing media query for diffrent screen sizes and you are trying combinations of diffrent height and width? THat when we sometimes mess up with aspect ration of images.

To avoid the situation change height and width in percentage or use CDN( content delivery network) to load images from.

![comparision of correction and incorrect aspect ratio side by side](https://i.imgur.com/OEGEh8Z.png)

---

6. ### **Unsafe links to cross-origin destiantions**

If your page uses `target="_blank"` to link other website to your page, you need to add `rel="noopener"` or `rel="noreferrer"` attribute in anchor element.
If you use `target="_blank"` in your links, other pages can access your `window` object with `window.opener` property, which may lead to redirect page to mallicious url.

use below mwntioned method to avoid this.

```html
<a href="https://examplepetstore.com" target="_blank" rel="noopener">
  Example Pet Store
</a>
```

---

7. ### **Front-end JavaScript libraries with known security vulnerabilities**

Libraries are used to add prewritten code that can solve our task. however, the code in these libraries is sometimes vulnarable, which can inject vulnarability in your site. So if there are any known vaulnarabity in your javascript libraries, update them to latest.

You can use built in tools like lighthouse or use [snyk database for known vaulnaribilities](https://snyk.io/vuln?packageManager=all).

---

8. ### **Use Meaningful Title Tags**

Title tags help make a web page search enigne friendly. Text inside title tags comes on google search results and web browsers tabs.

example :

```html
<title>Six Revisions - Web Development and Design Information</title>
```

---

9. ### **Use Descriptive Meta Tags**

Meta tags gives information about your web page to search engines and crawlers. More meaningfull description means more hits on the search engine and leading more traffic to your website.

for example, descriptive meta tags below will show info when searched on web pages.

```html
<meta
  name="description"
  content="Six Revisions is a blog that shares useful information about web development and design, dedicated to people who build websites."
/>
```

## ![Descriptive Meta Tags](https://i.imgur.com/VnIJDrU.png)

---

10. ### **Minify and Unify CSS,JS**

CSS files or external libraries take time load making web page slow to load. In order to make them bit faster, use single master css file and minify the css file removing unnessecery space and comments which web browsers doesnt need to understand.

Also make sure you are using trusted minifier, some online service for html editor was found to be injecting their own code to top rank them for seo optimization.

[here](https://casparwre.de/blog/seo-scam/) is an blog post about it.

---

11. ### **Use Lower Case Markup**

using a lower case to write HTML elements is an standard practice. Capitilize the html wont effect on your web page render but it will definatly make your code less readable.

#### Bad Practice

```html
<div>
  <img src="images/sample.jpg" alt="sample" />
  <a href="#" title="TEST">test</a>
  <p>some sample text</p>
</div>
```

#### Good Practice

```html
<div id="test">
  <img src="images/sample.jpg" alt="sample" />
  <a href="#" title="test">test</a>
  <p>some sample text</p>
</div>
```

---

12. ### **Write Consistently Formatted Code(use preetier)**

Writing a piece of code for software means tons of hours maintaining it. With this much time spending on maintaining the code we need tools to improve readability and increase the team work. Thats where the code formatter like prettier comes in, They help use with readability, enhance team work and save our time and energy.

These tools intregate with code editors easilty and can work in background without our involvement.
One of the famous code formatter is [prettier](https://prettier.io/), it supports major code editor and connects with them seamlessly.

---

13. ### **Document your code**

Writing a long code include months of maintainance with it. With lot of team mates doing the submodules, new team member can take a while to understand code. Even some of us forgeets what we wrote after some months. to avoid this situation, it is best to write comments in the section of code.

Here is a example of good code with comments,

```html
<!DOCTYPE html>
<html>
  <head>
    <!-- Document title -->
    <title>Title of the document</title>
  </head>

  <body>
    <!-- hero image -->
    <section>
      <img src="images/sample.jpg" alt="sample" />
    </section>

    <!-- Test link button -->
    <section>
      <a href="#" title="TEST">test</a>
    </section>
    <!-- Hero Content -->
    <section>
      <p>some sample text</p>
    </section>
  </body>
</html>
```

---

## References

- https://www.w3schools.com/tags/tag_doctype.asp
- https://web.dev/image-aspect-ratio/
- https://www.webfx.com/blog/web-design/20-html-best-practices-you-should-follow/
