## A guide to HTML5 semantic Elements

Whenever I start any new website, I just simply starts with ```<div>``` to structure the HTML. But recently I came to know about these semantic tags to structure the website. I was like, oh wait, what all these tags? why should I use it 🤯 ? 

Then started my research about these semantic elements, and was like oh god! why I missed this these many days. So thought to share my learnings about these helpful tags.

---
### What is semantic and non-semantic elements? 

```Semantic elements = elements with a meaning.``` 

A semantic element clearly describes its meaning to both the browser and the developer.

Examples of non-semantic elements: ```<div>``` and ```<span>``` - Tells nothing about its content.

Examples of semantic elements: ```<form>```, ```<table>```, and ```<article>``` - Clearly defines its content.

---

### All good, So why should I use semantic elements? 

![readable.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1633192787172/qSjQwp8Hc.png)

#### 1. It's easier to read 

This is probably the first thing you will notice when looking at the first block of code using semantic elements. 
This is a small example, but as a programmer, you can be reading through hundreds or thousands of lines of code. 
The easier it is to read and understand that code, the easier it makes your job.

#### 2. It has greater accessibility

We are not the only one that finds semantic elements easier to understand. 
**Search engines** and **assistive technologies** (like screen readers for users with a sight impairment) are also able to better understand the context and content of your website, meaning a better experience for your users.

#### 3. It leads to more consistent code 

When creating a header using non-semantic elements, different programmers might write this as ```<div class="header">```, ```<div id="header">```, ```<div class="head">```, or simply ```<div>```. 
There are so many ways that you can create a header element, and they all depend on the personal preference of the programmer. 
By creating a standard semantic element, it makes it easier for everyone.

---

### Some semantics tags to define different parts of a web page:

<table>
  <tr>
<td>
<ul>
          <li>```<article>```</li>
          <li>```<aside>```</li>
          <li>```<details>```</li>
          <li>```<figcaption>```</li>
          <li>```<figure>```</li>
          <li>```<footer>```</li>
          <li>```<header>```</li>
          <li>```<main>```</li>
          <li>```<mark>```</li>
          <li>```<nav>```</li>
          <li>```<section>```</li>
          <li>```<summary>```</li>
          <li>```<time>```</li>
</ul>
</td>

<td>
![Screenshot 2021-10-02 at 10.25.33 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1633193752505/kpdfqMiEs.png)
  </td>
  </tr>
 </table>

---

## Let's discuss some confusing similar tags! 

### 1. ```<section>``` and ```<article>```

“What’s the difference?”, you may ask. 
Both these elements are used for sectioning content, and yes, they can definitely be used interchangeably. It’s a matter of in which situation. 

HTML4 offered only one type of container element, which is ```<div>```. 

While this is still used in HTML5, HTML5 provided us with ```<section>``` and ```<article>``` in a way to replace ```<div>```.

The ```<section>``` and ```<article>``` elements are conceptually similar and interchangeable. To decide which of these you should choose, take note of the following:

1. An article is intended to be independently reusable.
2. A section is a thematic grouping of content.


```
<section>
  <p>Top Stories</p>
  <section>
    <p>News</p>
    <article>Story 1</article>
    <article>Story 2</article>
    <article>Story 3</article>
  </section>
  <section>
    <p>Sport</p>
    <article>Story 1</article>
    <article>Story 2</article>
    <article>Story 3</article>
  </section>
</section>
``` 
---

### 2. ```<header>``` and ```<hgroup>```
The ```<header>``` element is generally found at the top of a document, a section, or an article and usually contains the main heading and some navigation and search tools.


```
<header>
  <h1>Company A</h1>
  <ul>
    <li><a href="/home">Home</a></li>
    <li><a href="/about">About</a></li>
    <li><a href="/contact">Contact us</a></li>
  </ul>
  <form target="/search">
    <input name="q" type="search" />
    <input type="submit" />
  </form>
</header>
``` 

The ```<hgroup>``` element should be used where you want the main heading with one or more subheadings.

```
<hgroup>
  <h1>Heading 1</h1>
  <h2>Subheading 1</h2>
  <h2>Subheading 2</h2>
</hgroup>
```

REMEMBER, that the ```<header>``` element can contain any content, but the ```<hgroup>``` element can only contain other headers, that is ```<h1>``` to ```<h6>``` and including ```<hgroup>```.

---

### 3. ```<figure>``` and ```<figcaption>```
```<figure>``` is for wrapping your image content around it, and ```<figcaption>``` is to caption your image.


```
<figure>
  <img src="https://en.wikipedia.org/wiki/File:Shadow_of_Mordor_cover_art.jpg" alt="Shadow of Mordor" />
  <figcaption>Cover art for Middle-earth: Shadow of Mordor</figcaption>
</figure>
``` 

---

### 4. ```<cite>``` and ```<mark>```

The ```<cite>``` element is used to describe a reference to a cited creative work and must include the title of that work. The reference may be in an abbreviated form according to context-appropriate conventions related to citation metadata.

```
<figure>
    <blockquote>
        <p>It was a bright cold day in April, and the clocks were striking thirteen.</p>
    </blockquote>
    <figcaption>First sentence in <cite><a href="http://www.george-orwell.org/1984/0.html">Nineteen Eighty-Four</a></cite> by George Orwell (Part 1, Chapter 1).</figcaption>
</figure>
```

The ```<mark>``` element represents text which is marked or highlighted for reference or notation purposes, due to the marked passage's relevance or importance in the enclosing context.

```
<p>Search results for "salamander":</p>
<hr>
<p>Several species of <mark>salamander</mark> inhabit the temperate rainforest of the Pacific Northwest.</p>
<p>Most <mark>salamander</mark>s are nocturnal, and hunt for insects, worms, and other small creatures.</p>
```
---

### 5. ```<meter>``` and ```<progress>```

The ```<meter>``` element represents either a scalar value within a known range or a fractional value.

```
<label for="fuel">Fuel level:</label>

<meter id="fuel"
       min="0" max="100"
       low="33" high="66" optimum="80"
       value="50">
    at 50/100
</meter>

```

The ```<progress>``` element displays an indicator showing the completion progress of a task, typically displayed as a progress bar.

```
<label for="file">File progress:</label>

<progress id="file" max="100" value="70"> 70% </progress>
````

 Unlike the ```<meter>``` element, the minimum value is always 0 for ```<progress>```, and the min attribute is not allowed for the ```<progress>``` element.

---

### References
 
1. [https://www.w3schools.com/html/html5_semantic_elements.asp](https://www.w3schools.com/html/html5_semantic_elements.asp)
2. [https://developer.mozilla.org/en-US/docs/Web/HTML/Element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)
3. [https://www.freecodecamp.org/news/semantic-html5-elements/](https://www.freecodecamp.org/news/semantic-html5-elements/)

---

Thanks for taking your time and read this article. If you found this article useful, just give a like and follow me on [Twitter](https://twitter.com/code_rams). Feel free to contact us anytime to discuss or share ideas.


- 
