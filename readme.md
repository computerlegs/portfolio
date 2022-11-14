# Josh Reinhardt Portfolio Website
A portfolio website created as a student at Australian Institute of Technology Coder Academy.

Working version available at:   
GitHub repository available at: https://github.com/computerlegs/portfolio  
Presentation video available at:   

## Purpose  

## Functionality & Features

### Google Fonts

I used Google Font 'Open Sans' by adding a link to the header of each HTML document:

```html
<link href="https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,300;0,400;0,500;0,600;0,700;0,800;1,300;1,400;1,500;1,600;1,700;1,800&display=swap" rel="stylesheet"> 
```

Then, I created a style rule with a 'font-family' property set to the value 'Open Sans' and applied it to the selector 'html'.

```css
html {
    font-family: "Open Sans", Arial;
}
```

### Responsive HTML & CSS Navigation
Since this project uses HTML and CSS only, the navigation needed to rely on an HTML input with two states: the check box.

To make navigation simple and easy on mobile devices I implemented a hamburger style navigation menu that uses the pseudo class 'checked'. 

The toggle for the menu is a check box that is re-styled with CSS to look like the 'hamburger' style navigation icon. A checkbox type input was added using HTML with an ID applied to the input, and a class applied to the label.

 ```html
<input id="menu-toggle" type="checkbox"/>
<label class='menu-button-container' for="menu-toggle">
<div class='menu-button'></div>
</label>
 ```
 
Because the check box has two states, it can display content in two ways. This allows the menu to be displayed differently before and after a user presses it. The icon can also be styled between a 'hamburger' and a 'cross' using CSS and then animated between these two states with the property 'transform' and value 'rotate'. Below you can see the rotation transform in CSS as the input changes into the state 'checked'.

```css
#menu-toggle:checked + .menu-button-container .menu-button::before {
    margin-top: 0px;
    transform: rotate(405deg);
}
#menu-toggle:checked + .menu-button-container .menu-button::after {
    margin-top: 0px;
    transform: rotate(-405deg);
}
```

Media queries dictate when the 'hamburger' icon displays using a media query set at max width of 700px:

```css
.menu-button-container {
    display: none;
```

```css
@media (max-width: 700px) {
    .menu-button-container {
      display: flex;
    }
}
```

Media queries in combination with the 'checked' pseudo class dictate how list items are displayed depending on screen size and the state of the hamburger toggle. The tilde (~) symbol makes it so that only 'menu li' class list items following 'menu-toggle' ID items in the 'checked' state are styled. This is what makes the nav menu display as a drop down list when the checkbox is clicked.

```css
@media (max-width: 700px) {
    #menu-toggle ~ .menu li {
      height: 0;
      margin: 0;
      padding: 0;
      border: 0;
      transition: height 400ms cubic-bezier(0.23, 1, 0.32, 1);
    }
    #menu-toggle:checked ~ .menu li {
      border: 1px solid rgb(184, 184, 184);
      height: 2.5em;
      padding: 0.5em;
      transition: height 400ms cubic-bezier(0.23, 1, 0.32, 1);
    }
}
```

### Responsive header area with intro text and call to action buttons

This header uses flex box to position intro text and two different coloured call to action buttons. Elements are aligned at the bottom of the container using the property 'align-items' and value 'flex-end'.

```css
header-container {
    display: flex;
    align-items: flex-end;
    justify-content: center;
}
```
The header area changes height and font-size based on viewport sizes. 

It is made with flexbox in two columns which allows the call to action buttons to move underneith the hero text on smaller width viewports.

This header is designed for every sort of viewport, including desktops, tablets, mobile phones and even landscape oriented mobile phone viewports. Below is the CSS for landscape oriented mobile sized viewports:

```css
@media (max-height: 500px) {
    .home-header {
        width: 100%;
        height: 100px;
        display: flex;
        flex-direction: row;
        justify-content: center;
        margin-top: 150px;
    }
    .home-header p {
        font-size: 1em;
    }
    .home-header-container {
        padding-bottom: 10px;
    }
}
```
### Font Awesome Icons
Font Awesome is the second most used 'font' on the internet. It facilitates scaleable, CSS based graphic sprites to be used as icons throughout a website. Icons behave as text and are styled through CSS rule sets in the same way.

Font Awesome is loaded in the html head as a .js script:

```html
<script src="https://kit.fontawesome.com/d5fab9e2ad.js" crossorigin="anonymous"></script>
```

Then placed onto the page using the 'i' element:

```html
<i class="fa-brands fa-github social-icons"></i>
```

I used the built-in animation effects which required in-line CSS on their custom variable:

```html
<i class="icons fa-regular fa-envelope fa-beat" style="--fa-animation-iteration-count: 1;"></i>
```

## Sitemap

## Screenshots

## Target Audience

## Tech stack