## Week 3 - Introduction to CSS - Intermediate Notes

### Pseudo classes

A pseudo class is a way of defining styling for the state of an element or object on a page. A common use of this is with styling links so default browser styles don't conflict with your own colour or styling choices.

Default styling will look familiar...

![](https://screenshot.click/08-38-iqiav-n6xbh.jpg)

But that doesn't exactly look professional or clean on a page that might have an entirely different colour scheme, so we can use CSS selectors to target the tag and a pseudo class for it to do what we want with it. The formatting for a psuedo class will look like:

```
selector:pseudo-class {
    property:value;
}
```

So in our example above if we want to have all links stick with black text colour so they don't stand out too much, but appear different when visited we can do something like this:

```
a:link {
  color: black;
}

a:visited {
  color: red;
}
```

This is what allows us to get really specific with styling as there are a lot of pseudo classes that you can style independently depending on what item you're trying to select.

Results in:

![](https://screenshot.click/08-06-bl708-oi1pj.jpg)

Some of the more common pseudo classes you'll use when dealing with anchor tags (links) are `visited`, `hover`, and `active`.

These get much more advanced and involved and actually allow you to do things like target specific children or parents of an element to style them differently than others (think alternating colours on rows of a table). There are also pseudo elements which can be targeted, but those are even more in depth than we require here. Specifics and listings can be found on the W3 reference page below.

[Pseudo Classes MDN Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)<br>
[Pseudo Classes W3 Reference](https://www.w3schools.com/css/css_pseudo_classes.asp)

### Media Queries For Responsive Design

Media queries were introduced in CSS3 and have greatly aided in allowing for responsive web design. As considerations for almost all websites need to be made for tablet, mobile, and even smaller resolution users, using a media query to determine the size of the viewport and adjust styling accordingly is pretty critical responsive design practice.

By defining styling for `@media` with specific paramaters and specifications, you can hide or adjust styling of elements on a page based on viewport (browser window) size.

Take this header example below. At a size of 1390 this is how it looks:

![](https://screenshot.click/08-02-137wh-8jh3t.jpg)

But if I start to bring it in without responsive design in mind it gets pretty congested.

![](https://screenshot.click/08-04-a4yu9-vqf9d.jpg)

So what we can do in this case is actually hide the element that has that header contact information. In the case of my code this is `#header-contact`. We can add a media query to change the display style when the viewport is below a certain pixel count.

```
@media (max-width: 1389px) {
  #header-contact { display: none; }
}
```

By adding the above code to our stylesheet the `#header-contact` element will have its style set to `display: none`, which effectively hides it. We now have a more responsive design setup for smaller screen sizes.

![](https://screenshot.click/08-07-hvs0o-bkvlv.jpg)

This barely scratches the surface of what can be accomplished with media queries, but is a good starting point for what we need. Responsive design is something that should be given full consideration if your webpage is accessible to any devices as mobile usage is incredibly prevalent and your website might not scale appropriately.

[Media Queries MDN Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/@media)<br>
[Media Queries W3 Reference](https://www.w3schools.com/css/css3_mediaqueries.asp)<br>
[Responsive Web Design MDN](https://developer.mozilla.org/en-US/Apps/Progressive/Responsive/responsive_design_building_blocks) (pretty in depth)<br>
[Responive Web Design W3 Info](https://www.w3schools.com/css/css_rwd_intro.asp)
