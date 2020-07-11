---
title: Style your inline SVG with TailwindCSS
description: Change size, color  and other properties of any inline SVG with TailwindCSS.
img: style-svg-tailwind/style-svg-tailwind-3.png
alt: Recursos gratuitos para desarrollo web
tags: ['webdev', 'tailwind']
author: 
  name: Jesus Velazquez
  bio: Pro Stack Overflow copy-paster
  img: images/avatar.png
---
# Style your inline SVG with TailwindCSS

First thing you need to do is have your svg in line, let's take this half empty battery example from [Zondicons](http://www.zondicons.com/icons.html)

![Adjust SVG width and height](style-svg-tailwind/battery-half.svg)

Or, in its code version:
```html[]
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20"><path d="M0 6c0-1.1.9-2 2-2h16a2 2 0 0 1 2 2v8a2 2 0 0 1-2 2H2a2 2 0 0 1-2-2V6zm2 0v8h16V6H2zm1 1h4v6H3V7zm5 0h4v6H8V7z"/></svg>
```

## Size
Since `<svg>` is an HTML tag, we can add classes to it. Let's add some width and height to it, notice the _class_ argument:
```html[]
<svg class="w-8 h-8" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20"><path d="M0 6c0-1.1.9-2 2-2h16a2 2 0 0 1 2 2v8a2 2 0 0 1-2 2H2a2 2 0 0 1-2-2V6zm2 0v8h16V6H2zm1 1h4v6H3V7zm5 0h4v6H8V7z"/></svg>
```
This will output:
![Adjust SVG width and height](style-svg-tailwind/style-svg-tailwind-1.png)


In this case, we have a sqared _viewBox_ property on the svg, as indicated in	`viewBox="0 0 20 20"`. That means we could simply specify the width or height, and the image will scale up/down. Let's see an example:

```html[]
<svg class="w-12" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20"><path d="M0 6c0-1.1.9-2 2-2h16a2 2 0 0 1 2 2v8a2 2 0 0 1-2 2H2a2 2 0 0 1-2-2V6zm2 0v8h16V6H2zm1 1h4v6H3V7zm5 0h4v6H8V7z"/></svg>
```
![Adjust SVG width](./style-svg-tailwind//style-svg-tailwind-2.png)

For non squared svgs, you may need to adjust the witdh/height accordingly, to keep the aspect ratio.

## Color
To change the color of the SVG, we need to add first the _fill-current_ Tailwind directive, like this
```html[]
<svg class="fill-current w-12" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20"><path d="M0 6c0-1.1.9-2 2-2h16a2 2 0 0 1 2 2v8a2 2 0 0 1-2 2H2a2 2 0 0 1-2-2V6zm2 0v8h16V6H2zm1 1h4v6H3V7zm5 0h4v6H8V7z"/></svg>
```
This will make the SVG fill property take the color of the text in the parent container, useful if you have a dark theme for your website, it will be automatically adjusted when you switch the color of your text.
![Set SVG fill to parent's text color](style-svg-tailwind/style-svg-tailwind-3.png)

Now you can add any color, the same way you would add color to a text:
```html[]
<svg class="fill-current text-red-600 w-12" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20"><path d="M0 6c0-1.1.9-2 2-2h16a2 2 0 0 1 2 2v8a2 2 0 0 1-2 2H2a2 2 0 0 1-2-2V6zm2 0v8h16V6H2zm1 1h4v6H3V7zm5 0h4v6H8V7z"/></svg>
```
![Set SVG fill red 600](style-svg-tailwind/style-svg-tailwind-4.png)

## Pseudoclasses
Yes, you guessed it, we can add any pseudoclasses as in any html element in tailwind, let's try _hover_, for instance, lets make the previous red battery green on hover
```html[]
<svg class="fill-current text-red-600 hover:text-gray-600 w-12" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20"><path d="M0 6c0-1.1.9-2 2-2h16a2 2 0 0 1 2 2v8a2 2 0 0 1-2 2H2a2 2 0 0 1-2-2V6zm2 0v8h16V6H2zm1 1h4v6H3V7zm5 0h4v6H8V7z"/></svg>
```
![Set SVG fill red 600](style-svg-tailwind/style-svg-tailwind-5.png)

You could do the same thing for any other pseudoclass or screen breakpoint in Tailwind.


I hope this was helpful!
