## CSS Pseudo-elements and CSS Pseudo-classes Demystified

Hey there, today I picked the topic CSS Pseudo-elements and Pseudo-classes, You may ask why? it's because I little bit confused with the pseudo-elements and pseudo-class. So I just want to make clear about this today and thought to share my learnings here. 

Pseudo-elements and Pseudo-classes are some of the cool concepts of CSS. So learning it will surely help you when you want to design with CSS.

---

### So what is Pseudo-element?

A CSS pseudo-element is used to style specified parts of an element.

For example, it can be used to:

- Style the first letter, or line, of an element
- Insert content before, or after, the content of an element

#### Syntax

The syntax of pseudo-elements:

```
selector::pseudo-element {
  property: value;
}
```

---
### And what are Pseudo-classes?

A pseudo-class is used to define a special state of an element.

For example, it can be used to:

- Style an element when a user mouses over it
- Style visited and unvisited links differently
- Style an element when it gets focus

#### Syntax

The syntax of pseudo-classes:

```
selector:pseudo-class {
  property: value;
}
```
---

### Can you find the difference in syntax? 


>  Notice the double colon notation - ::first-line versus :first-line

>  The single-colon notation for pseudo-classes and double-colon notation used for pseudo-elements in CSS3. 

> This was an attempt from W3C to distinguish between pseudo-classes and pseudo-elements.

---

### Examples of CSS Pseudo Elements

<table>
<tr>
<td>
Selector
</td>
<td>
Example
</td>
<td>
Description
</td>
</tr>

<tr>
<td>
::after
</td>
<td>
p::after
</td>
<td>
Insert something after the content of each ```<p>``` element
</td>
</tr>

<tr>
<td>
::before
</td>
<td>
p::before
</td>
<td>
Insert something before the content of each ```<p>``` element
</td>
</tr>

<tr>
<td>
::first-letter
</td>
<td>
p::first-letter
</td>
<td>
Selects the first letter of each ```<p>``` element
</td>
</tr>

<tr>
<td>
::first-line
</td>
<td>
p::first-line
</td>
<td>
Selects the first line of each ```<p>``` element
</td>
</tr>

<tr>
<td>
::marker
</td>
<td>
::marker
</td>
<td>
Selects the markers of list items
</td>
</tr>

<tr>
<td>
::selection
</td>
<td>
p::selection
</td>
<td>
Selects the portion of an element that is selected by a user
</td>
</tr>

</table>

---

### Examples of CSS Pseudo Classes

<table>
<tr>
<td>
Selector
</td>
<td>
Example
</td>
<td>
Example description
</td>
</tr>

<tr>
<td>
:active
</td>
<td>
a:active
</td>
<td>
Selects the active link
</td>
</tr>

<tr>
<td>
:checked
</td>
<td>
input:checked
</td>
<td>
Selects every checked ```<input>``` element
</td>
</tr>

<tr>
<td>
:disabled
</td>
<td>
input:disabled
</td>
<td>
Selects every disabled ```<input>``` element
</td>
</tr>

<tr>
<td>
:empty
</td>
<td>
p:empty
</td>
<td>
Selects every ```<p>``` element that has no children
</td>
</tr>

<tr>
<td>
:enabled
</td>
<td>
input:enabled
</td>
<td>
Selects every enabled ```<input>``` element
</td>
</tr>

<tr>
<td>
:first-child
</td>
<td>
p:first-child
</td>
<td>
Selects every ```<p>``` elements that is the first child of its parent
</td>
</tr>

<tr>
<td>
:first-of-type
</td>
<td>
p:first-of-type
</td>
<td>
Selects every ```<p>``` element that is the first ```<p>``` element of its parent
</td>
</tr>

<tr>
<td>
:focus
</td>
<td>
input:focus	
</td>
<td>
Selects the ```<input>``` element that has focus
</td>
</tr>

<tr>
<td>
:hover
</td>
<td>
a:hover	
</td>
<td>
Selects links on mouse over
</td>
</tr>

<tr>
<td>
:in-range	
</td>
<td>
input:in-range	
</td>
<td>
Selects ```<input>``` elements with a value within a specified range
</td>
</tr>


<tr>
<td>
:invalid	
</td>
<td>
input:invalid	
</td>
<td>
Selects all ```<input>``` elements with an invalid value
</td>
</tr>

<tr>
<td>
:lang(language)	
</td>
<td>
p:lang(it)	
</td>
<td>
Selects every ```<p>``` element with a lang attribute value starting with "it"
</td>
</tr>

<tr>
<td>
:last-child	
</td>
<td>
p:last-child	
</td>
<td>
Selects every ```<p>``` elements that is the last child of its parent
</td>
</tr>

<tr>
<td>
:last-of-type	
</td>
<td>
p:last-of-type	
</td>
<td>
Selects every ```<p>``` element that is the last ```<p>``` element of its parent
</td>
</tr>

<tr>
<td>
:link
</td>
<td>
a:link	
</td>
<td>
Selects all unvisited links
</td>
</tr>

<tr>
<td>
:not(selector)
</td>
<td>
	:not(p)
</td>
<td>
	Selects every element that is not a ```<p>``` element
</td>
</tr>

<tr>
<td>
:nth-child(n)	
</td>
<td>
p:nth-child(2)
</td>
<td>
Selects every ```<p>``` element that is the second child of its parent
</td>
</tr>

<tr>
<td>
:nth-last-child(n)	
</td>
<td>
p:nth-last-child(2)
</td>
<td>
	Selects every ```<p>``` element that is the second child of its parent, counting from the last child
</td>
</tr>


<tr>
<td>
:nth-last-of-type(n)	
</td>
<td>
p:nth-last-of-type(2)	
</td>
<td>
Selects every ```<p>``` element that is the second ```<p>``` element of its parent, counting from the last child
</td>
</tr>

<tr>
<td>
:nth-of-type(n)	
</td>
<td>
p:nth-of-type(2)	
</td>
<td>
Selects every ```<p>``` element that is the second ```<p>``` element of its parent
</td>
</tr>

<tr>
<td>
:only-of-type
<td>
	p:only-of-type	
</td>
</td>
<td>
Selects every ```<p>``` element that is the only ```<p>``` element of its parent
</td>
</tr>

<tr>
<td>
:only-child	
<td>
	p:only-child	
</td>
</td>
<td>
Selects every ```<p>``` element that is the only child of its parent
</td>
</tr>


<tr>
<td>
:optional	
<td>
input:optional	
</td>
</td>
<td>
Selects ```<input>``` elements with no "required" attribute
</td>
</tr>

<tr>
<td>
:out-of-range	
<td>
input:out-of-range	
</td>
</td>
<td>
Selects ```<input>``` elements with a value outside a specified range
</td>
</tr>

<tr>
<td>
:read-only	
<td>
input:read-only	
</td>
</td>
<td>
Selects ```<input>``` elements with a "readonly" attribute specified
</td>
</tr>

<tr>
<td>
:read-write	
<td>
input:read-write
</td>
</td>
<td>
	Selects ```<input>``` elements with no "readonly" attribute
</td>
</tr>

<tr>
<td>
:required
<td>
	input:required
</td>
</td>
<td>
		Selects ```<input>``` elements with a "required" attribute specified
</td>
</tr>

<tr>
<td>
:root	
<td>
	root	
</td>
</td>
<td>
	Selects the document's root element
</td>
</tr>

<tr>
<td>
:target	
<td>
#news:target	
</td>
</td>
<td>
Selects the current active #news element (clicked on a URL containing that anchor name)
</td>
</tr>

<tr>
<td>
:valid	
<td>
input:valid	
</td>
</td>
<td>
Selects all ```<input>``` elements with a valid value	
</td>
</tr>

<tr>
<td>
:visited	
<td>
a:visited	
</td>
</td>
<td>
Selects all visited links
</td>
</tr>

</table>

---

### References 
1. [https://www.w3schools.com/css/css_pseudo_elements.asp](https://www.w3schools.com/css/css_pseudo_elements.asp)
2. [https://www.w3schools.com/css/css_pseudo_classes.asp](https://www.w3schools.com/css/css_pseudo_classes.asp)
3. [https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Pseudo-classes_and_pseudo-elements](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Pseudo-classes_and_pseudo-elements)

---
Hope you get an idea about pseudo-elements and pseudo-classes. Thanks for taking your time and read this article. If you found this article useful follow me on  [Twitter](https://twitter.com/code_rams). Feel free to contact me anytime to discuss or share your ideas.