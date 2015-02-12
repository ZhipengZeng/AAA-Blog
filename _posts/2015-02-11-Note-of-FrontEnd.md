---
layout: post
title: Note of FrontEnd (keep updating)
category: Programming
tag: [ CSS,  HTML, Note ]
---

## Here is a collection of some frontend's tricks (keep updating)

1. (11/02/2015) `margin-top` is not working for `<span>` element? (From [here](https://stackoverflow.com/questions/11700985/margin-top-not-working-for-span-element/11700999#11700999?newreg=eb8146d53dde4accaadf5b0e1c86aa6e))  

	*	**Solution: Make your `<span>` element, `display: inline-block;` or `display: block;`.**

	*	Unlike `<div>`, `<p>` which are Block Level elements which can take up margin on all sides. `<span>` cannot as it's an Inline element which takes up margins **horizontally** only.  

	*	Margin properties specify the width of the margin area of a box. The `margin` shorthand property sets the margin for all four sides while the other margin properties only set their respective side. These properties apply to all elements, but vertical margins will not have any effect on non-replaced inline elements.  
	
	*	I would suggest you to use `display: inline-block;` as it will be inline as well as block. Making it `block` only will result your element to render on another line, as block level elements take 100% of horizontal space on the page, unless they are made inline-block or they are floated to left or right.


2. (11/02/2015) CSS: set background image with opacity  (From [here](http://stackoverflow.com/questions/4183948/css-set-background-image-with-opacity))

	{% highlight css %}
	#example{
	background-image:url(image's link);
}
	{% endhighlight %}

	{% highlight css %}
#example{                                                    // this is solution
	position:relative;                                                 
}
#example:after{
	content:"";
	display:block;
	position:absolute;
	top:0;
	left:0;
	background-image:url(image's link);
	width:100%;
	height:100%;
	opacity:0.2;
	z-index:-1;
}
	{% endhighlight %}

Note, this will not work with an `<img>` tag. Instead, use a `<span>`, set the main element as `inline-block`, add a `:before` for the background image (copy from `:after`), then change the `:after` to use the foreground image and set `opacity` as 1.
