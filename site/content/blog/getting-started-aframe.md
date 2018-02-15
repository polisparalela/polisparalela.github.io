---
title: "Getting started with A-Frame"
author: "trys"
date: 2016-08-17 16:37:30
excerpt: A-Frame is a brilliant new framework bringing Virtual Reality (VR) to the web.
blog/categories: 
 - web-design
---

[A-Frame](http://aframe.io/) is a brilliant new framework bringing Virtual Reality (VR) to the web. Headed up by the [Mozilla VR Team](https://mozvr.com/), it has lowered the barrier of entry to this exciting new industry, letting anyone with a bit of HTML knowledge get involved.

As we’re all caught up in Olympic fever at the moment, I decided to recreate the famous logo in A-Frame. Want to see the finished result? [Check it out](https://trys.github.io/aframe/2/). Want to make it yourself? Open up your preferred text editor and follow along!

## Getting the page ready

You can get started with A-Frame by including a humble script tag in your page. The current release of the framework can be downloaded [here](https://aframe.io/releases/0.2.0/aframe.js).

## The first ring

A-Frame shapes are made up of custom HTML elements referred to as ‘primitives’ in [their documentation](https://aframe.io/docs/0.2.0/primitives/). We’ll be using three to begin with:

1. <code>a-scene</code>
1. <code>a-box</code>
1. <code>a-torus</code>


The <code>a-scene</code> element is the global container for the page but we don’t need to worry about that too much.

<code>a-box</code> is the simplest of primitives. It creates a cube or rectangle with a size dictated by the width and height attributes. The beauty of A-Frame’s HTML-based design is that elements can be nested just like any other HTML element. This means we can use our <code>a-box</code> primitive as a <code>div</code>. We can then perform group-based changes to this element, rather than making the changes on all child elements individually.

But back to the task in hand, we’re making Olympic rings so we’ll need a ring shape. The <code>a-torus</code> primitive is the ideal candidate for this. Instead of width and height, we’re going to use radius and radius-tubular to dictate how large the torus will be. As with all primitives, we can use the position and color attributes to control both where the element appears relative to the parent primitive, and what colour the shape should be.

With that in mind, we can build our first ring.

[code type="markup" src="aframe/1.html"]

![](images/blog/1.jpg)

And there we have it, a beautifully shaded, 3D ring in just 3 HTML elements! Now try clicking and dragging around your page, the element is in 3D space and will pan around your fixed camera position - all in the browser without writing a single line of Javascript!

Right, let’s step it up a notch:

## Five rings

We’ll duplicate the current torus five times, change their backgrounds and put them into position:

[code type="markup" src="aframe/2.html"]

![](images/blog/2.jpg)

Not bad, although we could do with interlinking the rings a bit. This can be achieved using the rotation property. By alternating 10deg and -10deg rotations, we can get a pretty accurate representation of the rings.

[code type="markup" src="aframe/3.html"]

![](images/blog/3.jpg)

## Panoramic background

The final touch is to add a panoramic background of Rio de Janeiro to really set the scene. To achieve this, we’ll add two more elements:

1. <code>a-sky</code>
1. <code>a-assets</code>


<code>a-sky</code> does what it says on the tin, it lets us fill the sky with colour or an image. Although we could simply put a src attribute on the element itself, we may find on a slower connection that the page is ready to render before the image has downloaded. For a website, that would be a good thing but for our grand-reveal VR experience, I’d prefer to get all assets ready to load before the browser displays the page.

Enter the <code>a-assets</code> primitive. This element lets us preload assets required for a page and it won’t load the page without them. For our use-case, we’ll nest an <code>img</code> tag with our background image and then reference it by ID on our <code>a-sky</code> element.

[code type="markup" src="aframe/4.html"]

![](images/blog/4.jpg)

And that’s it! In less than 100 lines of HTML and no Javascript, we’ve got a pretty impressive VR experience. It’s fully compatible with Google Cardboard and if you load the page up on your mobile, you can spin around the in the 3D world without clicking and dragging. Want to see the finished result? [Check it out](https://trys.github.io/aframe/2/).

