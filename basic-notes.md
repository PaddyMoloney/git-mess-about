## Week 3 - Introduction to CSS - Basic Notes

### Box Model

The box model is the main idea behind the styling and design of HTML and CSS pages. It defines the way things appear on a page and interact with other objects.

Each object (content) lives in a box, that box can have padding, a border, and margins.

![](https://screenshot.click/29-26-g808z-0mqj6.jpg)

These traits can be set individually or collectively in a couple of different ways, but each piece of content has them, even if they're all set to 0 or are essentially invisible.

Chrome dev tools has a good representation of this when you inspect elements.

![](https://screenshot.click/29-28-w0ize-kdjna.jpg)

After adding some margin, padding, and border styling, this appears differently.
 - Margin is the spacing between the object and its neighbours.
 - Border is between the margin and padding of the object.
 - Padding is between the content and the border.
 - Content will adjust to constraints of these styling properties.

![](https://screenshot.click/29-34-r8iji-xli9n.jpg)

There are multiple ways to set the styling and sizing for box model elements
  - `margin: 25px`
  - `margin: 25px 50px` - This will define top/bottom and right/left
  - `margin: 25px 50px 10px` - This will define top, right/left, bottom
  - `margin: 25px 40px 50px 10px` - This will define top, right, bottom, left

You can also define each with their own property like `margin-top` or `padding-right` for example.

[Box Model MDN Reference](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Box_model)<br>
[Box Model W3 Reference](https://www.w3schools.com/css/css_boxmodel.asp)

### Syntax Requirements

- Styling a tag is done by just naming the tag
- Styling a class or id are done by prepending a `.` or `#` respectively.
- Following that you wrap all properties in a set of curly braces `{ }`
- Write the property and then the values separated with a colon (:) `property: value`
- Each line must end with a semi-colon (;) `property: value;`

```
tag {
  property: value;
}

.class {
  property: value;
}

#id {
  property: value;
}
```

- You can group selectors together by separating them with a comma ,

```
html, body, h1, a, p, #description {
  property: value;
}
```

- You can also Chain together tags, classes, and ids in a single declaration to use more refined styling.

```
#list-things-i-like a {
  color: black;
}
```

- This will make any a tags that exist within my description id element black instead of the default
  browser styling they'd normally have. All other a tags on the page would remain unchanged.

**Default:**

![](https://screenshot.click/29-09-3fvdd-rpnp5.jpg)

**Styled:**

![](https://screenshot.click/29-10-35rw6-mecas.jpg)

**Clearer Example:**

![](https://screenshot.click/29-13-1lo3i-xhlhw.jpg)

### Priority of Styling and Inheritance:

CSS renders from the top down, meaning the last element or property read will be the style applied. For this reason when adjusting CSS it's simplest to just add it to the bottom of the page.

```
body {
  color: black;
}

#description {
  color: blue;
}

#description {
  color: orange;
}
```

There are two things of note here. Firstly, inheritance. Every text element on the page will be black except anything within the `#description`. This is because everything exists within the `body` tag, and will inherit styles from that one declaration. The text content in the `#description` will be orange because of the order of styling. The last value for the `color` property in the `#description` is orange, so the blue is ignored.

[Syntax Requirements MDN Reference](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Syntax)<br>
[Syntax Requirements W3 Reference](https://www.w3schools.com/css/css_syntax.asp)

### Size Units

% - Percent. This will render an element at the specified percentage of the page at the time of loading.
  This means that it is a non-responsive after the page has been loaded.
px - Pixels. This will be a specific unchanging size once rendered and is relative to the viewing device.
em - Relative sizing to the size of the element. So doing something like 2em for a font-size property
  means that the style will be 2 times the current size of the element.
rem - Similar to em but relative to the root element.

These are the main ones you'll use (mostly just %, px, em) but there is also vw, vh, vmin, and vmax. These
are units based on the viewport size itself. More commonly if you're going to be concerned about this
for responsive design you'll just use media queries and set specifics values that way.

[Size Units MDN Reference](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Values_and_units)<br>
[Size Unit W3 Reference](https://www.w3schools.com/cssref/css_units.asp)

---

[MDN Selector Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)<br>
[W3 Selector Reference](https://www.w3schools.com/cssref/css_selectors.asp)
