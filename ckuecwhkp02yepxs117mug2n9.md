## The CSS ::before and ::after

Hey there! Welcome back again to my blog. If you are trying out some CSS arts, then today would be a great day for you. You would learn some handy properties and selectors in CSS that would be greatly helpful. Let's discuss the content property and how to use it along with ::before and ::after  [pseudo-classes](https://ramyachinnadurai.in/css-pseudo-elements-and-css-pseudo-classes-demystified). 

Most times you would see ```content: ""``` found in the ```::before``` and ```::after``` pseudo-elements. But the content property has many useful applications.

It's time to dive in!

---

### What is the content property and how to use it along with before and after selector? 

The ```content``` property in CSS defines the content of an element. 

The ```::before```  selector inserts something before the content of each selected element(s).

The ```::after``` selector to insert something after the content.

---

### Example of CSS ::before and ::after Selector

```
div::before {
  content: "before";
}
div::after {
  content: "after";
}

```
---
### What are the values accepted in content?

First, let's take a look at all of the accepted values of the content property.

- ```normal```:  This is the default value. Computes to ```none``` when used with pseudo-elements.

- ```none```: A pseudo-element will not be generated.

- ```<string>```:  Sets the content to the string specified. 
This string can contain Unicode escape sequences. For example, the copyright symbol: ```\\000A9```.

- ```<image>```: Sets the content to an image or gradient using ```url()``` or ```linear-gradient()```.

- ```open-quote``` | ```close-quote```: Sets the content to the appropriate quote character referenced from the quotes property.

- ```no-open-quote``` | ```no-close-quote```: Removes a quote from the selected element, but still increments or decrements the nesting level referenced from the quotes property.

- ```attr(*attribute*)```: Sets the content as the string value of the selected elements selected attribute.

- ```counter()```: Sets the content as the value of a ```counter```, usually a number.

---

Let's see some of the accepted values with examples. 

### 1. Content with image

Images can be used with the content property. This is fairly straightforward. Here is an example that uses both:

```
 content: url(//unsplash.it/2000/200);
  display: block;
  width: 100%;
  height: 200px;
  overflow: hidden;
```


%[https://codepen.io/ramyachinnadurai/pen/VwWJGLd]


For accessibility, there is also an option to add alternate text for the image. This feature is not fully supported though.

---

### 2. Content with String 

One of the most basic examples would be the use of adding *string* content before or after an element. 

In this example, we'll add a link symbol before a link and add the URL for the link after it.

```
a::before {
	content: "\\1F517 ";
}
a::after {
	content: " (" attr(href) ")";
}
```

Notice the space after the Unicode character in the ::before pseudo-element and the before the first parenthesis in the ::after pseudo-element. This will create space between these and the parent element.

Alternatively, you could add padding or margin to the pseudo-elements to add separation.


%[https://codepen.io/ramyachinnadurai/pen/MWoMqOm]

---

### 3. Content with an open quote and close quote 

```
p::before {
  content: open-quote;
}
p::after {
  content: close-quote;
}

```

%[https://codepen.io/ramyachinnadurai/pen/RwgzYym]


---

### 4. Content with attribute ( attr ) 

Attributes can be used to pass content from HTML into the CSS content property. 

A perfect use case for this is a tooltip. You can add a title attribute to an element in HTML to have a simple, built-in tooltip on hover. 

But to customize this, we can use a data attribute on our HTML tag and then use the content property to add a tooltip.

In this example, we use the attribute data-tooltip from our HTML element to pass the value into our tooltip. For the pointer of the tooltip, we set the content to "", as content is required to render a ::before or ::after pseudo-element.

```
.tooltip::after {
  content: attr(data-tooltip);
}
```

%[https://codepen.io/ramyachinnadurai/pen/oNwrPPJ]

---

### 5. Content with counters() 

The counter() CSS function returns a string representing the current value of the named counter. In the following example, we have an ordered list that we will add content using a counter.

```
ol {
  counter-reset: exampleCounter;
}
li {
  counter-increment: exampleCounter;
}
li::after {
  content: "[" counter(exampleCounter) "] == ["
    counter(exampleCounter, upper-roman) "]";
}
```

%[https://codepen.io/ramyachinnadurai/pen/ExXBeMp]


---

### Thanks for Reading!

The best use for content IMO is to use it for updating bulk elements. If you want to add an icon before every link on your site, it would be much easier to add it through the content property than to add it to every element in the HTML document.

Here comes an end with ```CSS ::before```, ```::after``` and ```content``` property. 

Hope you enjoyed this article and learned something new. 

Thanks for taking the time to read this article. If you found this article useful do follow me on  [Twitter](https://twitter.com/code_rams) for more interesting tips in form of tweets and feel free to contact me anytime to discuss or share your ideas. 

---

### References 

1. [https://www.w3schools.com/cssref/sel_before.asp](https://www.w3schools.com/cssref/sel_before.asp)
2. [https://www.w3schools.com/cssref/sel_after.asp](https://www.w3schools.com/cssref/sel_after.asp)
3. [https://css-tricks.com/almanac/selectors/a/after-and-before/](https://css-tricks.com/almanac/selectors/a/after-and-before/)
4. [https://www.freecodecamp.org/news/css-before-and-after-how-to-use-the-content-property/](https://www.freecodecamp.org/news/css-before-and-after-how-to-use-the-content-property/)

---