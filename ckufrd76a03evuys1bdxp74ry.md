## 10+ Unknown but Useful HTML tags

Hey there! a few days back we discussed, what is  [semantic HTML](https://ramyachinnadurai.in/a-guide-to-html5-semantic-elements) and how can we use it to increase readability and accessibility for Search engines. As an extension of that  [article](https://ramyachinnadurai.in/a-guide-to-html5-semantic-elements), let's discuss some useful but unknown HTML tags to use in our code. 

Let's crack this!

---


### 1. ```<ins>``` and ```<del>```

If you're wanting to display editing revisions with markup, ```<ins>``` and ```<del>```is just the ticket. As the name implies, ```<ins>``` highlights what's been added to the document with an underline, and ```<del>``` shows what's been taken out with a strikethrough.

%[https://codepen.io/ramyachinnadurai/pen/yLXmXwL]

---

### 2. ```<fieldset> ``` and ```<legend>```

The ```<fieldset>``` tag is used to group related elements in a form. It draws a box around the related elements. 
The ```<legend>``` tag defines a caption for the ```<fieldset>``` element.

%[https://codepen.io/ramyachinnadurai/pen/NWgQgJJ]

---

### 3. ```<acronym>```

The ```<acronym>``` tag is a way to define or further explain a group of words. When you hover over text that has the ```<acronym>``` tag used, a box appears below with the text from the title tag.

%[https://codepen.io/ramyachinnadurai/pen/xxrvLOL]


---

### 4. ```<abbr>```
The ```<abbr>``` tag is much similar to the ```<acronym>``` tag, except the ```<abbr>``` tag is only used to define abbreviated words. 

Just like ```<acronym>```, you define a title within the tag. When a visitor hovers over the abbreviated text, the full definition appears below. The ```<abbr>``` tag is rarely used, but the benefits are many for screen readers, spellcheckers and search engines.

%[https://codepen.io/ramyachinnadurai/pen/dyRxzOe]

---

### 5. ```<mark>``` 
Yet another interesting and useful tag. Suppose, you want to highlight some text in your HTML document, you don’t have to write some extra lines of CSS. 
All you need to do is, wrap your text in the ```<mark>``` tag. You will see a nice yellow background below your text. 


%[https://codepen.io/ramyachinnadurai/pen/JjJgyvL]

---

### 6. ```<details>```

By default, content within the ```<details>``` tags are hidden but can be shown by clicking on it. Each element should display a summary of what it’s about when it’s hidden. 

%[https://codepen.io/ramyachinnadurai/pen/VwWozBV]

---

### 7. ```<wbr>```

The ```<wbr>``` tag can be used to show a possible word break. Sometimes you have a word that’s so long that the web browser automatically breaks it up. Using the ```<wbr>``` tag gives the browser a specific place to break up a word if it’s necessary.

%[https://codepen.io/ramyachinnadurai/pen/GREVvzV]

---

### 8. ```<dfn>``` 

The ```<dfn>```  tag stands for the "defining element", and it specifies a term that is going to be defined within the content.

The nearest parent of the ```<dfn>``` tag must also contain the definition/explanation for the term.

The term inside the ```<dfn>```  tag can be any of the following:

1. Just as the content of the ```<dfn>``` element
2. Or, with the title attribute added

%[https://codepen.io/ramyachinnadurai/pen/PojMKrw]

---
### 9. ```<address>```

The ```<address>``` tag defines the contact information for the author/owner of a document or an article.

The contact information can be an email address, URL, physical address, phone number, social media handle, etc.

The text in the ```<address>``` element usually renders in italic, and browsers will always add a line break before and after the <address> element.

%[https://codepen.io/ramyachinnadurai/pen/GREVMKK]

---

### 10. time 

The ```<time>``` tag defines a specific time (or DateTime).

The DateTime attribute of this element is used to translate the time into a machine-readable format so that browsers can offer to add date reminders through the user's calendar, and search engines can produce smarter search results.

%[https://codepen.io/ramyachinnadurai/pen/qBjePWQ]

---
### Thanks for Reading 

Hope you enjoyed this article and learned something new.

Thanks for taking the time to read this article. If you found this article useful do follow me on  [Twitter](https://twitter.com/code_rams) for more interesting tips in form of tweets & threads. Feel free to contact me anytime to discuss or share your ideas. 

---

### References 
1. [https://www.w3schools.com/html/html5_semantic_elements.asp](https://www.w3schools.com/html/html5_semantic_elements.asp)
2. [https://www.w3schools.com/tags/tag_address.asp](https://www.w3schools.com/tags/tag_address.asp)
3. [https://developer.mozilla.org/en-US/docs/Web/HTML/Element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)

---