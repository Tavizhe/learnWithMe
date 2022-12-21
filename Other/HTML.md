# HTML Introduction

HTML (Hyper Text Markup Language) is the standard markup language for creating Web pages Also describes the structure of a Web page.
HTML consists of a series of elements that tell the browser how to display the content.
as example: "this is a heading", "this is a paragraph", "this is a link", etc.

---

## HTML Documents

All HTML documents must start with a document type declaration: `<!DOCTYPE html>`.The `<!DOCTYPE>` declaration represents the document type, and helps browsers to display web pages correctly.
The HTML document itself begins with `<html>` and ends with `</html>`.
The visible part of the HTML document is between `<body>` and `</body>`.

### HTML Headings

HTML headings are defined with the `<h1>` to `<h6>` tags. `<h1>` defines the most important heading. `<h6>` defines the least important heading.

### HTML Paragraphs

HTML paragraphs are defined with the `<p>` tag.

#### HTML Display

You cannot be sure how HTML will be displayed.
Large or small screens, and resized windows will create different results.
With HTML, you cannot change the display by adding extra spaces or extra lines in your HTML code.
The browser will automatically remove any extra spaces and lines when the page is displayed.

#### HTML Horizontal Rules

The `<hr>` element is used to separate content (or define a change) in an HTML page (as shape of line breaker).

#### HTML Line Breaks

Use `<br>` if you want a line break (a new line) without starting a new paragraph.

#### The HTML `<pre>` element

The text inside a `<pre>` element is displayed in a fixed-width font (usually Courier), and it preserves both spaces and line breaks.

```html
<pre>
  My Bonnie lies over the ocean.

  My Bonnie lies over the sea.
</pre>
```

### HTML Links

HTML links are defined with the `<a>` tag. Example:
`<a href="https://www.w3schools.com">This is a link</a>`
The link's destination is specified in the href attribute. Attributes are used to provide additional information about HTML elements.

- A link does not have to be text. A link can be an image or any other HTML element!

#### The target Attribute

By default, the linked page will be displayed in the current browser window. To change this, you must specify another target for the link.

The **target** attribute specifies where to open the linked document Also can have one of the following values:

1. `_self` - Default. Opens the document in the same window/tab as it was clicked
2. `_blank` - Opens the document in a new window or tab
3. `_parent` - Opens the document in the parent frame
4. `_top` - Opens the document in the full body of the window

- Absolute URLs (a full web address)
- Relative URLs (A local link (a link to a page within the same website) is specified with a relative URL (without the "https://www" part))

> How to Use an Image as a Link:

```html
<a href="default.asp">
  <img src="smiley.gif" alt="HTML tutorial" style="width:42px;height:42px;" />
</a>
```

#### Link to an Email Address

Use mailto: inside the href attribute to create a link that opens the user's email program (to let them send a new email). Example:
`<a href="mailto:someone@example.com">Send email</a>`

#### Create Bookmarks

Bookmarks can be useful if a web page is very long. To create a bookmark - first create the bookmark, then add a link to it. When the link is clicked, the page will scroll down or up to the location with the bookmark as example below:

```html
<!--First, use the id attribute to create a bookmark:-->
<h2 id="C4">Chapter 4</h2>
<!--Then, add a link to the bookmark ("Jump to Chapter 4"), from within the same page:-->
<a href="#C4">Jump to Chapter 4</a>
```

- You can also add a link to a bookmark on another page: `<a href="html_demo.html#C4">Jump to Chapter 4</a>`

### HTML Images

HTML images are defined with the `<img>` tag. The source file (src), alternative text (alt), width, and height are provided as attributes. Example:

`<img src="w3schools.jpg" alt="W3Schools.com" width="104" height="142">`

#### Image Maps

The HTML `<map>` tag defines an image map. An image map is an image with clickable areas. The areas are defined with one or more `<area>` tags.

```html
<img src="workplace.jpg" alt="Workplace" usemap="#workmap" />

<map name="workmap">
  <area
    shape="rect"
    coords="34,44,270,350"
    alt="Computer"
    href="computer.htm"
  />
  <area shape="rect" coords="290,172,333,250" alt="Phone" href="phone.htm" />
  <area shape="circle" coords="337,300,44" alt="Coffee" href="coffee.htm" />
</map>
```

##### The Areas

A clickable area is defined using an `<area>` element.

- Shape: You must define the shape of the clickable area, and you can choose one of these values:

1. rect - defines a rectangular region (he coordinates for shape="rect" come in pairs, one for the x-axis and one for the y-axis.)
   Example: the coordinates 34,44 is located 34 pixels from the left margin and 44 pixels from the top:
   <center><img src="/Other/Html%20Images%20Reference/1.png" alt="Picture" style="align=center" /></center>
2. circle - defines a circular region (first locate the coordinates of the center of the circle: 337,300 Then specify the radius of the circle: 44 pixels)
   Example:
    <center><img src="/Other/Html%20Images%20Reference/2.png" alt="Picture" style="align=center" /></center>
3. poly - defines a polygonal region (contains several coordinate points, which creates a shape formed with straight lines (a polygon).)
   Example:
   <center><img src="/Other/Html%20Images%20Reference/3.png" alt="Picture" style="align=center" /></center>
   So The coordinates come in pairs, one for the x-axis and one for the y-axis like:

   ```html
   <area
     shape="poly"
     coords="140,121,181,116,204,160,204,222,191,270,140,329,85,355,58,352,37,322,40,259,103,161,128,147"
     href="croissant.htm"
   />
   ```

4. default - defines the entire region

You must also define some coordinates to be able to place the clickable area onto the image.

## HTML Elements

The HTML element is everything from the start tag to the end tag.

> Nested HTML Elements : HTML elements can be nested (this means that elements can contain other elements).
> All HTML documents consist of nested HTML elements.

- The `<html>` element is the root element and it defines the whole HTML document.
- It has a start tag `<html>` and an end tag `</html>`.
- Then, inside the `<html>` element there is a `<body>` element.
- HTML is Not Case Sensitive.

> **The lang Attribute**: You should always include the lang attribute inside the `<html>` tag, to declare the language of the Web page. This is meant to assist search engines and browsers. The following example specifies English as the language and United States as the country:

```html
<!DOCTYPE html>
<html lang="en-US">
  <body>
    ...
  </body>
</html>
```

> **The title Attribute**: The title attribute defines some extra information about an element as a tooltip.

- Always Use Lowercase Attributes And Always Quote Attribute Values. BTW Double quotes around attribute values are the most common in HTML.

---

## HTML Styles

The HTML style attribute is used to add styles to an element, such as color, font, size, and more.

### Background Color and Image

The CSS background-color property defines the background color for an HTML element. use the HTML style attribute and the CSS background-image property.

### Text Color

The CSS color property defines the text color for an HTML element:

### Fonts

The CSS font-family property defines the font to be used for an HTML element:

```html
<h1 style="font-family:verdana;">This is a heading</h1>
```

### Text Size

The CSS font-size property defines the text size for an HTML element:

### Text Alignment

The CSS text-align property defines the horizontal text alignment for an HTML element:

```html
<h1 style="text-align:center;">Centered Heading</h1>
```

---

## HTML Text Formatting

HTML Formatting Elements
Formatting elements were designed to display special types of text:

```html
<b>
  - Bold text
  <strong>
    - Important text (*The HTML <strong> element defines text with strong importance. The content inside is typically displayed in bold*).
    <i>
      - Italic text (*The <i> tag is often used to indicate a technical term, a phrase from another language, a thought, a ship name, etc.*)
      <em>
        - Emphasized text (*The HTML <em> element defines emphasized (a word from another language that has special meaning) text. The content inside is typically displayed in italic.*)
        <mark>
          - Marked text (*defines text that should be marked or highlighted*)
          <small>
            - Smaller text
            <del>
              - Deleted text (*Browsers will usually strike a line through deleted text*)
              <ins>
                - Inserted text (*Browsers will usually underline inserted text*)
                <sub> - Subscript text(*Subscript text appears half a character below the normal line, and is sometimes rendered in a smaller font. Subscript text can be used for chemical formulas, like H2O*) <sup> - Superscript text(* Superscript text appears half a character above the normal line, and is sometimes rendered in a smaller font. Superscript text can be used for footnotes, like WWW[1]*)</sup></sub></ins
              ></del
            ></small
          ></mark
        ></em
      ></i
    ></strong
  ></b
>
```

## HTML Quotation and Citation (taghdirname) Elements

- The HTML `<blockquote>` element defines a section that is quoted from another source.The HTML `<q>` tag defines a short quotation.

- HTML `<abbr>` for Abbreviations (ekhtesar). Example:

```html
<p>
  The <abbr title="World Health Organization">WHO</abbr> was founded in 1948.
</p>
```

- HTML `<address>` for Contact Information that defines the contact information for the author/owner of a document or an article.
- HTML `<cite>` for Work Title: The HTML `<cite>` tag defines the title of a creative work (e.g. a book, a poem, a song, a movie, a painting, a sculpture, etc.).The text in the `<cite>` element usually renders in italic. Example:

```html
<p><cite>The Scream</cite> by Edvard Munch. Painted in 1893.</p>
```

- HTML `<bdo>` for Bi-Directional Override (bar aks nevisi) : is used to override the current text direction.

---

## HTML Comment Tag

You can add comments to your HTML source by using the following syntax:
`<!-- Write your comments here -->`

- Also Comments can be used to hide content. You can also hide more than one line. Everything between the `<!--` and the `-->` will be hidden from the display.

---

## HTML Colors

HTML colors are specified with predefined color names, or with RGB, HEX, HSL, RGBA, or HSLA values.

### Color Names

In HTML, a color can be specified by using a color name like Tomato, Orange, DodgerBlue, MediumSeaGreen, Gray, SlateBlue, Violet, LightGray. HTML supports 140 standard color names. [Check Here](https://www.w3schools.com/colors/colors_names.asp). BTW we can colorize borders too.
`<h1 style="border:2px solid Tomato;">Hello World</h1>`

### Color Values

colors can also be specified using RGB values, HEX values, HSL values, RGBA values, and HSLA values like:

1. rgb(255, 99, 71)
2. #ff6347
3. hsl(9, 100%, 64%)
4. rgba(255, 99, 71, 0.5)
5. hsla(9, 100%, 64%, 0.5)

---

## HTML `<picture>` Element

The HTML `<picture>` element allows you to display different pictures for different devices or screen sizes.

```html
<picture>
  <source media="(min-width: 650px)" srcset="img_food.jpg" />
  <source media="(min-width: 465px)" srcset="img_car.jpg" />
  <img src="img_girl.jpg" />
</picture>
```

## Favicon in HTML

A favicon image is displayed to the left of the page title in the browser tab, like this:

 <center><img src="/Other\Html Images Reference\img_favicon.png" alt="Favicon" style="align=center" /></center>
 Example:

```html
<head>
  <title>My Page Title</title>
  <link rel="icon" type="image/x-icon" href="/images/favicon.ico" />
</head>
```

## HTML Tables

A table in HTML consists of table cells inside rows and columns. Each table cell is defined by a `<td>` and a `</td>` tag (td stands for table data).also Each table row starts with a `<tr>` and ends with a `</tr>` tag (tr stands for table row).

### Table Headers

Sometimes you want your cells to be table header cells. In those cases use the `<th>` tag instead of the `<td>` tag (th stands for table header).

Example:

```html
<table>
  <tr>
    <th>Person 1</th>
    <th>Person 2</th>
    <th>Person 3</th>
  </tr>
  <tr>
    <td>Emil</td>
    <td>Tobias</td>
    <td>Linus</td>
  </tr>
  <tr>
    <td>16</td>
    <td>14</td>
    <td>10</td>
  </tr>
</table>
```

### Add a Border

To add a border, use the CSS border property on table, th, and td elements:

```css
table,
th,
td {
  border: 1px solid black;
  border-collapse: collapse; // avoiding doubler borders
}
th,
td {
  border-radius: 10px; // Round Table Borders
}
```

- Dotted Table Borders also available in these forms (dotted, dashed, solid, double, groove, ridge, inset, outset, none, hidden).

---

### HTML Table Sizes

HTML tables can have different sizes for each column, row or the entire table. Use the style attribute with the width or height properties to specify the size of a table, row or column. Example:

<center><img src="/Other\Html Images Reference\4.png" alt="Favicon" style="align=center" /></center>

```html
<table style="width:100%">
  <tr>
    <th>Firstname</th>
    <th>Lastname</th>
    <th>Age</th>
  </tr>
  <tr style="height:200px">
    <td>Jill</td>
    <td>Smith</td>
    <td>50</td>
  </tr>
  <tr>
    <td>Eve</td>
    <td>Jackson</td>
    <td>94</td>
  </tr>
</table>
```

### HTML Table Headers

HTML tables can have headers for each column or row, or for many columns/rows.

<center><img src="/Other\Html Images Reference\5.png" alt="Favicon" style="align=center" /></center>

By default, table headers are bold and centered So To left-align the table headers, use the CSS text-align property.

```css
th {
  text-align: left;
}
```

- Header for Multiple Columns: use the colspan attribute on the `<th>` element.

<center><img src="/Other\Html Images Reference\6.png" alt="Favicon" style="align=center" /></center>

Example:

```html
<table>
  <tr>
    <th colspan="2">Name</th>
    <th>Age</th>
  </tr>
  <tr>
    <td>Jill</td>
    <td>Smith</td>
    <td>50</td>
  </tr>
  <tr>
    <td>Eve</td>
    <td>Jackson</td>
    <td>94</td>
  </tr>
</table>
```

- Table Caption: You can add a caption that serves as a heading for the entire table.
  `<caption>Monthly savings</caption>`

### HTML Table Padding & Spacing

HTML tables can adjust the padding inside the cells, and also the space between the cells.

<center><img src="/Other\Html Images Reference\7.png" alt="Favicon" style="align=center" /></center>

Example:

```css
th,
td {
  padding-top: 10px;
  padding-bottom: 20px;
  padding-left: 30px;
  padding-right: 40px;
  border-spacing: 30px;
}
```

### HTML Table Colspan & Rowspan

HTML tables can have cells that span over multiple rows and/or columns.

<center><img src="/Other\Html Images Reference\8.png" alt="Favicon" style="align=center" /></center>

- To make a cell span more than one column, use the colspan attribute.

  ```html
  <table>
    <tr>
      <th colspan="2">Name</th>
      <th>Age</th>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Smith</td>
      <td>43</td>
    </tr>
    <tr>
      <td>Eve</td>
      <td>Jackson</td>
      <td>57</td>
    </tr>
  </table>
  ```

- To make a cell span more than one row, use the rowspan attribute.

  ```html
  <table>
    <tr>
      <th>Name</th>
      <td>Jill</td>
    </tr>
    <tr>
      <th rowspan="2">Phone</th>
      <td>555-1234</td>
    </tr>
    <tr>
      <td>555-8745</td>
    </tr>
  </table>
  ```

### HTML Table Styling

Zebra Stripes:

<center><img src="/Other\Html Images Reference\9.png" alt="Favicon" style="align=center" /></center>

```css
tr:nth-child(even) {
  background-color: #d6eeee;
}
```

Vertical Zebra Stripes:

<center><img src="/Other\Html Images Reference\10.png" alt="Favicon" style="align=center" /></center>

```css
td:nth-child(even),
th:nth-child(even) {
  background-color: #d6eeee;
}
```

_You can combine the styling from the two examples above and you will have stripes on every other row and every other column._

- Horizontal Dividers

<center><img src="/Other\Html Images Reference\11.png" alt="Favicon" style="align=center" /></center>

```css
tr {
  border-bottom: 1px solid #ddd;
}
```

- Hoverable Table:

<center><img src="/Other\Html Images Reference\12.png" alt="Favicon" style="align=center" /></center>

```css
tr {
  tr:hover {
    background-color: #d6eeee;
  }
}
```

### HTML Table Colgroup

The `<colgroup>` element is used to style specific columns of a table. If you want to style the two first columns of a table, use the `<colgroup>` and `<col>` elements.

<center><img src="/Other\Html Images Reference\13.png" alt="Favicon" style="align=center" /></center>

```html
<table>
  <colgroup>
    <col span="2" style="background-color: #D6EEEE" />
  </colgroup>
  <tr>
    <th>MON</th>
    <th>TUE</th>
    <th>WED</th>
    <th>THU</th>
    ...
  </tr>
</table>
```

**Remember**:

- The `<colgroup>` element should be used as a container for the column specifications.
- Each group is specified with a `<col>` element.
- The span attribute specifies how many columns that get the style.
- The style attribute specifies the style to give the columns.

### HTML Lists

- [Unordered HTML List](/Other/HTML.md): starts with the `<ul>` tag. Each list item starts with the `<li>`. (The list items will be marked with bullets (small black circles))

> The CSS list-style-type property is used to define the style of the list item marker. It can have one of the following values:
>
> - disc - Sets the list item marker to a bullet (default)
> - circle - Sets the list item marker to a circle
> - square - Sets the list item marker to a square
> - none - The list items will not be marked

```html
<ul style="list-style-type:square;">
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ul>
```

- [Ordered HTML List](/Other/HTML.md): starts with the `<ol>` tag. Each list item starts with the `<li>` tag. (The list items will be marked with numbers)

> The type attribute of the `<ol>` tag, defines the type of the list item marker:
>
> - type="1" - The list items will be numbered with numbers (default)
> - type="A" - The list items will be numbered with uppercase letters
> - type="a" - The list items will be numbered with lowercase letters
> - type="I" - The list items will be numbered with uppercase roman numbers
> - type="i" - The list items will be numbered with lowercase roman numbers

```html
<ol type="A">
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ol>
```

#### HTML Description Lists

A description list is a list of terms, with a description of each term. The `<dl>` tag defines the description list, the `<dt>` tag defines the term (name), and the `<dd>` tag describes each term:

Example:

```html
<dl>
  <dt>Coffee</dt>
  <dd>- black hot drink</dd>
  <dt>Milk</dt>
  <dd>- white cold drink</dd>
</dl>
```

---

## display value

Every HTML element has a default display value, depending on what type of element it is.
There are two display values: block and inline.

### Block-level Elements

always starts on a new line, and the browsers automatically add some space (a margin) before and after the element. A block-level element always takes up the full width available.

Here are the block-level elements in HTML:

| `<address>` | `<article>` | `<aside>` | `<blockquote>` | `<canvas>` | `<dd>`       | `<div>`  |
| ----------- | ----------- | --------- | -------------- | ---------- | ------------ | -------- |
| `<dl>`      | `<dt>`      | `<hr>`    | `<figcaption>` | `<figure>` | `<footer>`   | `<form>` |
| `<h1>-<h6>` | `<header>`  | `<li>`    | `<main>`       | `<nav>`    | `<noscript>` | `<hr>`   |
| `<ol>`      | `<p>`       | `<pre>`   | `<section>`    | `<table>`  | `<tfoot>`    | `<ul>`   |
| `<video>`   |             |           |                |            |              |          |

### Inline Elements

An inline element does not start on a new line. An inline element only takes up as much width as necessary.

Here are the inline elements in HTML:

| `<a>`      | `<abbr>`     | `<acronym>` | `<b>`     | `<bdo>`    | `<big>`    | <`br`>  |
| ---------- | ------------ | ----------- | --------- | ---------- | ---------- | ------- |
| `<button>` | `<cite>`     | `<code>`    | `<dfn>`   | `<em>`     | `<i>`      | `<img>` |
| `<input>`  | `<kbd>`      | `<label>`   | `<map>`   | `<object>` | `<output>` | `<q>`   |
| `<samp>`   | `<script>`   | `<select>`  | `<small>` | `<span>`   | `<strong>` | `<sub>` |
| `<sup>`    | `<textarea>` | `<time>`    | `<tt>`    | `<var>`    |            |         |
