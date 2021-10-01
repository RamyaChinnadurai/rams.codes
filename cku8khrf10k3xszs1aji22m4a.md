## 5 Tips for CSS responsive design


### **Choose Mobile-First Approach For responsive design**

The best approach for responsive design is to design a mobile version of your website first. 

This allows you to see how the images, text, logos, and other elements will look on smaller screens. 

If they display without problems, then you shouldn’t have any problems adapting your design to larger screens.

### Responsive starts with this meta tag

The first line of code to get started with responsive design is to be placed in the head section of the page.  You must start with Responsive Header, placing this code inside the head of the HTML page.

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

### Concepts covered 

1. min()
2. max() 
3. clamp()
4. box-sizing: border-box
5. overflow: hidden 

---

### 1. Minimum ( min )

`min` selects the smallest (most negative) value from a list of comma-separated expressions.

For example, in the case of: `min(1rem, 50%, 10vw)`, the browser calculates which of these relative units is the smallest, and uses that value as the actual value.

![min().gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1633103141911/m__aXL0mB.gif)
    
###### Reference - [web.dev](https://web.dev/min-max-clamp/) Try out this in  [codepen ](https://codepen.io/ramyachinnadurai/pen/OJgGyZL) 
    

---

### 2. Maximum ( Max ) 

The `max()` function selects the largest value from a list of comma-separated expressions.

Example: `max(50vw, 400px),` the browser determines which one is either the largest value respectively.

 
![max.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1633103696817/SBbSk_Vco.gif)

###### Reference - [web.dev](https://web.dev/min-max-clamp/) Try out this in  [codepen ](https://codepen.io/ramyachinnadurai/pen/PojgPMq)


---

### 3. Clamping values ( Clamp ) 

`clamp()` is the combination of the `min()` and `max()` functions, accepting three parameters:

1. the minimum value,
2. the preferred value, and
3. the maximum value

For example: `clamp(45ch, 50%, 75ch)`This allows for the browser to determine the width of the paragraph. It will set the width to 50% unless 50% is smaller than 45ch, at which point 45ch will be selected, and visa versa for if 50% is wider than 75ch. 

![clamp.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1633103886384/PEbv9DR9q.gif)

###### Reference - [web.dev](https://web.dev/min-max-clamp/) Try out this in  [codepen ](https://codepen.io/ramyachinnadurai/pen/vYZMLYo)

---

### 4. Box Sizing 

One of the God properties of CSS, to overcome your responsive frustrations is box-sizing. It is an essential property for responsive website development. 

#### 1. Content box 

  The size of the box gets elaborate based on the content. When the site is viewed on mobile, the content box grows based on the content which makes the site scroll.

#### 2. Border-box

If you use border-box on an element with a width set in per cent, it will take padding into account, so you’ll no longer need to adjust the width. 

Needless to say, this trick works best for mobile websites and browsers with CSS3 support.


![box-sizing.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1633103943997/xly0dpGGj.gif)

###### Reference - [Pocket Gopher](https://codepen.io/pocket-gopher/pen/JNMbJQ) Try out this in  [codepen ](https://codepen.io/ramyachinnadurai/pen/jOwRWML)


---

### 5. **Overflow Properties**

`Overflow: hidden` is a handy CSS property that is helpful in many cases in addition to responsive design. 

Instead of clearing divs, you can clear containers by simply setting the overflow value to hidden. 

`Overflow: hidden` makes value hidden instead of scrolling the content. 


![overflow.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1633104016384/kbFTRMVuQ.gif)

###### Try out this in [codepen ](https://codepen.io/ramyachinnadurai/pen/ExXbJGN).

---


## Additional tip 

### Responsive Images

HTML offers the <picture> element that allows us to specify the exact image resource that will be rendered based on the media query we add. 

Instead of having one image (usually a large, high-resolution version) sent to all screen sizes and scaling it to the viewport width, we specify a set of images to serve in specific situations.

```css
<picture>
  <source media="(max-width:1000px)" srcset="picture-lg.png">
  <source media="(max-width:600px)" srcset="picture-mid.png">
  <source media="(max-width:400px)" srcset="picture-sm.png">
  <img src="picture.png" alt="picture"">
</picture>
```

In this example, picture.png is the full-size image. 

From there, we define the next-largest version of the image, picture-lg.png, and the size reduces in descending order until the smallest version, picture-sm.png. 

Note that we’re still using media queries in this approach, but it’s the <picture> element itself that is driving the responsive behaviour rather than defining breakpoints in the CSS.

---

### References 

1. [https://web.dev/min-max-clamp/](https://web.dev/min-max-clamp/) 
2. [https://www.freecodecamp.org/news/css-properties-examples/](https://www.freecodecamp.org/news/css-properties-examples/)
3. [https://corpocrat.com/2015/11/03/10-cool-css-tricks-for-responsive-design/](https://corpocrat.com/2015/11/03/10-cool-css-tricks-for-responsive-design/)
4. [https://www.pixafy.com/blog/5-useful-css-tips-for-responsive-design/](https://www.pixafy.com/blog/5-useful-css-tips-for-responsive-design/)
5. [https://css-tricks.com/beyond-media-queries-using-newer-html-css-features-for-responsive-designs/](https://css-tricks.com/beyond-media-queries-using-newer-html-css-features-for-responsive-designs/)

---

Thanks for taking your time and reading this article, if you find this useful kindly like this article and follow me [Ramya Chinnadurai](https://twitter.com/code_rams) on Twitter. 
Feel free to connect me for sharing your ideas and suggestions.