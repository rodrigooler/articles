---
title: Using Mixins with SCSS to Create Breakpoints
published: true
description: Enhancing the organization of responsive CSS with mixins and SCSS
tags: CSS, SCSS, Mixins, ResponsiveDesign
---

![sass](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/sz97k9suaryv0xn9v6r0.jpg)


**Table of Contents**

- [Introduction](#introduction)
- [What are Breakpoints?](#what-are-breakpoints)
- [Creating a Mixin for Breakpoints](#creating-a-mixin-for-breakpoints)
- [Using the Breakpoint Mixin](#using-the-breakpoint-mixin)
- [HTML Example](#html-example)
- [Conclusion](#conclusion)

---

### Introduction

One of the main challenges in web development is creating a responsive design that perfectly adapts to all types of devices. In this context, Sass (Syntactically Awesome Stylesheets), and more specifically, SCSS (Sassy CSS), have proven to be powerful tools for efficient control of CSS styles. One of the most useful features of SCSS is the ability to create mixins, which are reusable blocks of code.

---

### What are Breakpoints?

Breakpoints are points where the content of a website or application responds with layout changes to adapt to different screen sizes. They are essential for adjusting the appearance of a site to mobile devices, tablets, and desktops.

---

### Creating a Mixin for Breakpoints

SCSS allows the creation of mixins to encapsulate styles that will be reused. Let's see how to create a mixin for breakpoints:

```scss
@mixin breakpoint($point) {
  @if $point == small {
    @media (max-width: 600px) { @content; }
  }
  @elseif $point == medium {
    @media (max-width: 900px) { @content; }
  }
  @elseif $point == large {
    @media (max-width: 1200px) { @content; }
  }
}
```

This mixin allows you to specify different styles for three different breakpoints: small, medium, and large. The `@content` allows you to pass style blocks to the mixin, which will be applied at the specified breakpoint.

---

### Using the Breakpoint Mixin

Now that we've created our mixin, let's use it. For example, we might want to change the background color of a div when the screen is smaller than 600px (small):

```scss
.div-example {
  background-color: blue;

  @include breakpoint(small) {
    background-color: red;
  }
}
```

In this example, the div will have a blue background on screens larger than 600px. However, when the screen is smaller than 600px, the mixin will apply the style inside the `breakpoint(small)` block, changing the background color to red.

---

### HTML Example

Now, applying this to HTML, we have:

```html
<div class="div-example">This is an example of a responsive design div.</div>
```

With our SCSS compiled to CSS and correctly included on the page, the example div will respond according to the screen sizes we defined earlier.

---

### Conclusion

The use of mixins with SCSS to create breakpoints is an effective strategy for managing responsive CSS. It helps keep your code clean, readable, and easy to maintain, while providing an optimized viewing experience for users, regardless of the device they are using.

Remember, however, that each project is unique and may require different numbers or values of breakpoint. Adapt this strategy to your specific needs and always remember to test your design on different devices to ensure a consistent and enjoyable user experience.

using mixins with scss to create breakpoints