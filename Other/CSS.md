# CSS Introduction

CSS is the language we use to style a Web page, CSS stands for Cascading Style Sheets.

## Why Use CSS?

CSS is used to define styles for your web pages, including the design, layout and variations in display for different devices and screen sizes.

## Fast look at CSS Properties Table

Text Properties:

| Property        | What it Does                                                           |
| --------------- | ---------------------------------------------------------------------- |
| letter-spacing  | Controls the amount of space between each letter in a section of text. |
| line-height     | Controls the amount of vertical space between lines of text            |
| text-align      | Controls the alignment for a section of text                           |
| text-decoration | Controls what the text looks like                                      |
| text-indent     | Controls the indentation of the first line in a section of text        |
| text-transform  | Changes the case of a section of text                                  |
| vertical-align  | Controls the vertical alignment of a section of text                   |
| word-spacing    | Controls the amount of space between words                             |

Font Properties:

| Property     | What it Does                                |
| ------------ | ------------------------------------------- |
| font-family  | Controls the type of font shown on the page |
| font-size    | Controls the size of the font               |
| font-style   | Controls the style of the font              |
| font-size    | Controls the size of the font               |
| font-variant | Controls the variant of the font            |
| font-weight  | Controls the boldness of the font           |

Color/Background Properties:

| Property              | What it Does                                        |
| --------------------- | --------------------------------------------------- |
| color                 | Controls the color of the text                      |
| background-attachment | Controls the scrolling of the background            |
| background-color      | Controls the color of the background                |
| background-image      | Allows you to set a background image                |
| background-repeat     | Allows different patterns of background repetition  |
| background-position   | Controls the position of the background on the page |

Box Properties:

| Property                           | What it Does                                                    |
| ---------------------------------- | --------------------------------------------------------------- |
| width                              | Controls the width of a section                                 |
| height                             | Controls the height of a section                                |
| border-color                       | Controls the border color of a section                          |
| border-style                       | Controls the style of a border                                  |
| border-width                       | Controls the width of a border                                  |
| border-top,bottom,left,right-width | Controls the width of a border side                             |
| margin-top,bottom,left,right       | Controls the width of a margin from the specified side          |
| padding-top,bottom,left,right      | Controls the amount of padding from the specified side          |
| float                              | Controls the floating of a section                              |
| clear                              | Defines whether a section disallows other sections on its sides |

---

Classification Properties:

| Property    | What it Does                                     |
| ----------- | ------------------------------------------------ |
| white-space | Controls the white space formatting of a section |
| display     | Controls the display of a section                |
| visibility  | Controls the visibility of an element            |
| z-index     | Controls the layering of an element              |

## CSS Syntax

<center><img src="/Other/css%20Images%20Reference/1.png" alt="Picture" style="align=center" /></center>

- The selector - points to the ==HTML element== you want to style.
- The declaration block - contains one or more declarations separated by semicolons. Each includes a CSS property name and a value, separated by a colon.

### CSS Selectors

CSS selectors are used to "find" (or select) the HTML elements you want to style.

We can divide CSS selectors into five categories:

- Simple selectors (select elements based on name, id, class) : Example for id `#para1 { text-align: center;}`. Example for class `.center { text-align: center;}`
  > Note: An id name cannot start with a number!
- Combinator selectors (select elements based on a specific relationship between them). Example `p.center { text-align: center; color: red;}` or `<p class="center large">This paragraph refers to two classes.</p>`
  > The CSS Universal Selector is `*`.
  > You can always do grouped the selectors : Example `h1, h2, p { text-align: center; color: red;}`
- Pseudo-class selectors (select elements based on a certain state)
- Pseudo-elements selectors (select and style a part of an element) : Example `p - Selects all <p> elements`
- Attribute selectors (select elements based on an attribute or attribute value)

---

### How To Add CSS

There are three ways of inserting a style sheet:

1. External CSS (as an another file with .css format)
2. Internal CSS (use all the CSS codes right in HTML before body)
3. Inline CSS (using it on the go every where)

- off-course you always want to use External CSS for cleaner coding.

> If some properties have been defined for the same selector (element) in different style sheets, the value from the last read style sheet will be used.

---

### CSS Comments

Comments are used to explain the code. Comments are ignored by browsers.
Example `/* This is a single-line comment */ p { color: red;}`.

---

### CSS Colors

Colors are specified using predefined color names, or RGB, HEX, HSL, RGBA, HSLA values. In CSS, a color can be specified by using a predefined color name:
CSS/HTML support [140 standard color names.!](https://www.w3schools.com/colors/colors_names.asp).

<center><img src="/Other/css%20Images%20Reference/2.png" alt="Picture" style="align=center" /></center>

- CSS Background Color (`background-color`) - will be coded like this Example : `<h1 style="background-color:DodgerBlue;">Hello World</h1>`
- CSS Text Color (`color`) - will be coded like this Example : `<h1 style="color:Tomato;">Hello World</h1>`
- CSS Border Color (`border`) - will be coded like this Example : `<h1 style="border:2px solid Tomato;">Hello World</h1>`
  Demonstration of the different border styles:

```css
p.dotted {
  border-style: dotted;
}
p.dashed {
  border-style: dashed;
}
p.solid {
  border-style: solid;
}
p.double {
  border-style: double;
}
p.groove {
  border-style: groove;
}
p.ridge {
  border-style: ridge;
}
p.inset {
  border-style: inset;
}
p.outset {
  border-style: outset;
}
p.none {
  border-style: none;
}
p.hidden {
  border-style: hidden;
}
p.mix {
  border-style: dotted dashed solid double;
}
```

Result:

<center><img src="/Other/css%20Images%20Reference/3.png" alt="Picture" style="align=center" /></center>

- The `border-color` property - is used to set the color of the four borders.
  > The `border` property is a shorthand property for the following individual border properties: `border-width, border-style, border-color`
- The `border-radius` property - is used to add rounded borders to an element.

---

- CSS background-image (`background-image`) - specifies an image to use as the background of an element. Example : `background-image: url("paper.gif");` Can also use (`background-repeat: repeat-x; or repeat-y; or no-repeat;`) for repeating. CSS background-position (`background-position`) is used to specify the position of the background image. Example : `background-position: right top;`

> CSS RGB Colors - In CSS, a color can be specified as an RGB value, using this formula: rgb(red-255, green-255, blue-255, alpha-1).
> CSS HEX Colors - A hexadecimal color is specified with: `#RRGGBB`, where the RR (red), GG (green) and BB (blue) hexadecimal integers specify the components of the color.
> CSS HSL Colors - In CSS, a color can be specified using hue, saturation, and lightness (HSL) in the form: hsl(hue-0 Till 360, saturation-100%, lightness-100%)

- CSS background-attachment (`background-attachment`) - specifies whether the background image should scroll or be fixed (will not scroll with the rest of the page). Example : `background-attachment: fixed; or scroll;`
- CSS Background Shorthand (`background`) - it is also possible to specify all the background properties in one single property. Example : `background: #ffffff url("img_tree.png") no-repeat right top;`
