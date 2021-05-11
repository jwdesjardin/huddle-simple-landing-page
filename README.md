# Frontend Mentor - Huddle landing page with single introductory section solution

This is a solution to the [Huddle landing page with single introductory section challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/huddle-landing-page-with-a-single-introductory-section-B_2Wvxgi0). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the page depending on their device's screen size
- See hover states for all interactive elements on the page

### Screenshot

![](./README_imgs/desktop-screenshot.jpg)

### Links

- Solution URL: [Github Repo](https://github.com/jwdesjardin/huddle-simple-landing-page)
- Live Site URL: [Huddle Landing Page](https://jwdesjardin.github.io/huddle-simple-landing-page/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties and SCSS
- CSS Grid and Felxbox
- Mobile-first workflow
- BEM Convention
- Keyframe animations


### What I learned

#### BEM - Block Element Modifier Convention

I used this convention in naming my classes to keep my CSS organized. Each block got a name such as TEXT-CONTENT and then the elements within that block would get the class name of TEXT-CONTENT_element. 

```html
<div class='TEXT-CONTENT'>
  <h2 class='TEXT-CONTENT_heading'>Build The Community Your Fans Will Love</h2>
  <p class='TEXT-CONTENT_p'>Huddle re-imagines the way we build communities...</p>
  <button class='TEXT-CONTENT_button'>Register</button>
</div>
```

#### CSS Grid and Flexbox

One of the main challenges of this project is to find a way to make the main image and text content to be side my side on desktop sized screens and stacked on top of each other on mobile sized screens.

<img src="./README_imgs/desktop-design-marked.jpg" alt="desktop columns" width="400">
<img src="./README_imgs/mobile-design-marked.jpg" alt="mobile columns" width="100">


The first method i used was the flex-column method. In the mobile view I created a flexbox with the direction of column and the widths of the children take up 100% of the screen. In the media query for desktop screens and larger i would switch the direction to row and the percentages of the children to 50% giving the desired responsive effect. 

```css
.flex-column {
  display: flex;
  flex-direction: column;
}

.IMAGE {
  width: 100%;
}

.TEXT-CONTENT {
  width: 100%;
}
```
then within the desktop and larger media query... 
```css
.flex-column {
  flex-direction: row;
}

.IMAGE {
  width: 50%;
}

.TEXT-CONTENT {
  width: 50%;
}
```

While this method works I prefer to use CSS grid to make this responsive. The Grid method is more clear and will allow us to scale the number of columns without adding more lines of code. 

```css
.desktop-2cols {
  display: grid;
  grid-template-columns: repeat(1, 1fr);
}

.IMAGE {
  width: 100%;
}

.TEXT-CONTENT {
  width: 100%;
}
```

then within the desktop and larger media query... 

```css
.desktop-2cols {
  grid-template-columns: repeat(1, 1fr);
}
```

### Continued development

I want to continue to document challenges and successes that i come across in my projects on github, slack and twitter. I also want to continue to look at my solutions and refactor them before moving on to the next project. I think there is a lot of learning happening in the refactoring stages of development. 

### Useful resources

- [BEM Convention](https://en.bem.info/methodology/css/) - This helped me pick up the basics of BEM before I started. This method is good to know and if I am not using a UI library CSS Modules, Styled-Components or something similar then i will be using this to keep my class names in order.


## Author

- Website - [Joey Desjardin](https://www.joeydesjardin.com)
- Frontend Mentor - [@jwdesjardin](https://www.frontendmentor.io/profile/jwdesjardin)
- Twitter - [@joey_desjardin](https://twitter.com/joey_desjardin)

