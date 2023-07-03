# HTML Introduction

HTML (Hyper Text Markup Language) is the standard markup language for creating Web pages Also describes the structure of a Web page.
HTML consists of a series of elements that tell the browser how to display the content.
as Example: "this is a heading", "this is a paragraph", "this is a link", etc.

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
`<a href="mailto:someone@Example.com">Send email</a>`

#### Create Bookmarks

Bookmarks can be useful if a web page is very long. To create a bookmark - first create the bookmark, then add a link to it. When the link is clicked, the page will scroll down or up to the location with the bookmark as Example below:

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
   <center><img src="/HTML/Html%20Images%20Reference/1.png" alt="Picture" style="align=center" /></center>
2. circle - defines a circular region (first locate the coordinates of the center of the circle: 337,300 Then specify the radius of the circle: 44 pixels)
   Example:
    <center><img src="/HTML/Html%20Images%20Reference/2.png" alt="Picture" style="align=center" /></center>
3. poly - defines a polygonal region (contains several coordinate points, which creates a shape formed with straight lines (a polygon).)
   Example:
   <center><img src="/HTML/Html%20Images%20Reference/3.png" alt="Picture" style="align=center" /></center>
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

> **The lang Attribute**: You should always include the lang attribute inside the `<html>` tag, to declare the language of the Web page. This is meant to assist search engines and browsers. The following Example specifies English as the language and United States as the country:

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

 <center><img src="/HTML\Html Images Reference\img_favicon.png" alt="Favicon" style="align=center" /></center>
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
  border-collapse: collapse; /* avoiding doubler borders */
}
th,
td {
  border-radius: 10px; /* Round Table Borders */
}
```

- Dotted Table Borders also available in these forms (dotted, dashed, solid, double, groove, ridge, inset, outset, none, hidden).

---

### HTML Table Sizes

HTML tables can have different sizes for each column, row or the entire table. Use the style attribute with the width or height properties to specify the size of a table, row or column. Example:

<center><img src="/HTML\Html Images Reference\4.png" alt="Favicon" style="align=center" /></center>

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

<center><img src="/HTML\Html Images Reference\5.png" alt="Favicon" style="align=center" /></center>

By default, table headers are bold and centered So To left-align the table headers, use the CSS text-align property.

```css
th {
  text-align: left;
}
```

- Header for Multiple Columns: use the colspan attribute on the `<th>` element.

<center><img src="/HTML\Html Images Reference\6.png" alt="Favicon" style="align=center" /></center>

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

<center><img src="/HTML\Html Images Reference\7.png" alt="Favicon" style="align=center" /></center>

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

<center><img src="/HTML\Html Images Reference\8.png" alt="Favicon" style="align=center" /></center>

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

<center><img src="/HTML\Html Images Reference\9.png" alt="Favicon" style="align=center" /></center>

```css
tr:nth-child(even) {
  background-color: #d6eeee;
}
```

Vertical Zebra Stripes:

<center><img src="/HTML\Html Images Reference\10.png" alt="Favicon" style="align=center" /></center>

```css
td:nth-child(even),
th:nth-child(even) {
  background-color: #d6eeee;
}
```

_You can combine the styling from the two Examples above and you will have stripes on every other row and every other column._

- Horizontal Dividers

<center><img src="/HTML\Html Images Reference\11.png" alt="Favicon" style="align=center" /></center>

```css
tr {
  border-bottom: 1px solid #ddd;
}
```

- Hoverable Table:

<center><img src="/HTML\Html Images Reference\12.png" alt="Favicon" style="align=center" /></center>

```css
tr {
  tr:hover {
    background-color: #d6eeee;
  }
}
```

### HTML Table Colgroup

The `<colgroup>` element is used to style specific columns of a table. If you want to style the two first columns of a table, use the `<colgroup>` and `<col>` elements.

<center><img src="/HTML\Html Images Reference\13.png" alt="Favicon" style="align=center" /></center>

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

- [Unordered HTML List](/HTML/HTML.md): starts with the `<ul>` tag. Each list item starts with the `<li>`. (The list items will be marked with bullets (small black circles))

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

- [Ordered HTML List](/HTML/HTML.md): starts with the `<ol>` tag. Each list item starts with the `<li>` tag. (The list items will be marked with numbers)

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

---

## HTML class Attribute

- Multiple HTML elements can share the same class.

The class attribute is often used to point to a class name in a style sheet. It can also be used by a JavaScript to access and manipulate elements with the specific class name.

Example:

```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      .city {
        background-color: tomato;
        color: white;
        border: 2px solid black;
        margin: 20px;
        padding: 20px;
      }
    </style>
  </head>
  <body>
    <div class="city">
      <h2>London</h2>
      <p>London is the capital of England.</p>
    </div>
  </body>
</html>
```

- JavaScript can access elements with a specific class name with the getElementsByClassName() method.

## HTML id Attribute

The HTML id attribute is used to specify a unique id for an HTML element. so it can't be used for multiple elements. Although usage of id is the same as class the difference is The id name is case sensitive!

### HTML Bookmarks with ID and Links

HTML bookmarks are used to allow readers to jump to specific parts of a webpage. In order to use this function, id have an excellent place.

Example:

```html
<!-- First, create a bookmark with the id attribute: -->
<h2 id="C4">Chapter 4</h2>
<!-- Then, add a link to the bookmark ("Jump to Chapter 4"), from within the same page: -->
<a href="#C4">Jump to Chapter 4</a>
```

## HTML **Iframes**

An HTML iframe is used to display a web page within a web page. As Syntax goes:
`<iframe src="url" title="description"></iframe>`

## HTML - The Head Element

The HTML `<head>` element is a container for the following elements: `<title>`, `<style>`, `<meta>`, `<link>`, `<script>`, and `<base>`.

The `<head>` element is a container for metadata (some information about data on the current page).

- Metadata is not displayed.

- `<title>` - element defines the title of the document. The title must be text-only, and it is shown in the browser's title bar or in the page's tab.
- `<style>` - element is used to define style information for a single HTML page.
- `<link>` - element defines the relationship between the current document and an external resource.

## The HTML `<meta>` Element

The `<meta>` element is typically used to specify the character set, page description, keywords, author of the document, and viewport settings.

Examples:

```html
<!-- Define the character set used: -->
<meta charset="UTF-8" />

<!-- Define keywords for search engines: -->
<meta name="keywords" content="HTML, CSS, JavaScript" />

<!-- Define a description of your web page: -->
<meta name="description" content="Free Web tutorials" />

<!-- Define the author of a page: -->
<meta name="author" content="John Doe" />

<!-- Refresh document every 30 seconds: -->
<meta http-equiv="refresh" content="30" />

<!-- Setting the viewport to make your website look good on all devices: -->
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

On last Example:

> The width=device-width part sets the width of the page to follow the screen-width of the device (which will vary depending on the device).
> The initial-scale=1.0 part sets the initial zoom level when the page is first loaded by the browser.

## The HTML `<base>` Element

The `<base>` element specifies the base URL and/or target for all relative URLs in a page.
The `<base>` tag must have either an href or a target attribute present, or both.
There can only be one single `<base>` element in a document!

Example:
Specify a default URL and a default target for all links on a page:

```html
<head>
  <base href="https://www.w3schools.com/" target="_blank" />
</head>

<body>
  <img src="images/stickman.gif" width="24" height="39" alt="Stickman" />
  <a href="tags/tag_base.asp">HTML base Tag</a>
</body>
```

## HTML Layout Elements

HTML has several semantic elements that define the different parts of a web page like:

1. `<header>` - Defines a header for a document or a section
2. `<nav>` - Defines a set of navigation links
3. `<section>` - Defines a section in a document
4. `<article>` - Defines an independent, self-contained content
5. `<aside>` - Defines content aside from the content (like a sidebar)
6. `<footer>` - Defines a footer for a document or a section
7. `<details>` - Defines additional details that the user can open and close on demand
8. `<summary>` - Defines a heading for the
9. `<details>` element>

### HTML Layout Techniques

There are four different techniques to create multicolumn layouts. Each technique has its pros and cons:

- CSS framework - If you want to create your layout fast, you can use bootstrap, ... .
- CSS float property - you just need to remember how the float and clear properties work. Disadvantages: Floating elements are tied to the document flow, which may harm the flexibility.
- CSS flexbox - Use of flexbox ensures that elements behave predictably when the page layout must accommodate different screen sizes and different display devices.
- CSS grid - grid-based layout system, with rows and columns, making it easier to design web pages without having to use floats and positioning.

---

## HTML Responsive Web Design

Responsive web design is about creating web pages that look good on all devices!
A responsive web design will automatically adjust for different screen sizes and viewports.

### Setting The Viewport

To create a responsive website, add the following `<meta>` tag to all your web pages:
`<meta name="viewport" content="width=device-width, initial-scale=1.0">`

<center><img src="/HTML\Html Images Reference\14.png" alt="Favicon" style="align=center" /></center>

### Responsive Images

If the CSS width property is set to 100%, the image will be responsive and scale up and down. If the **max-width** property is set to **100%**, the image will scale down if it has to, but **never scale up to be larger than its original size**.

#### Show Different Images Depending on Browser Width

The HTML `<picture>` element allows you to define different images for different browser window sizes.
Example:

```html
<!-- after you change browser window it will change the picture to another. -->
<picture>
  <source srcset="img_smallflower.jpg" media="(max-width: 600px)" />
  <source srcset="img_flowers.jpg" media="(max-width: 1500px)" />
  <source srcset="flowers.jpg" />
  <img src="img_smallflower.jpg" alt="Flowers" />
</picture>
```

## Responsive Text Size

The text size can be set with a "vw" unit, which means the "viewport width".
`<h1 style="font-size:10vw">Hello World</h1>`

## Media Queries

In addition to resize text and images, it is also common to use media queries in responsive web pages.With media queries you can define completely different styles for different browser sizes.
Example:

normal pc or laptop view:

<center><img src="/HTML/Html%20Images%20Reference/3.png" alt="Picture" style="align=center" />
</center>

in mobile view:

<center><img src="/HTML/Html%20Images%20Reference/3.png" alt="Picture" style="align=center" /></center>

code of last Example:

```css
<style>
.left, .right {
  float: left;
  width: 20%; /* The width is 20%, by default */
}
.main {
  float: left;
  width: 60%; /* The width is 60%, by default */
}
/* Use a media query to add a breakpoint at 800px: */
@media screen and (max-width: 800px) {
  .left, .main, .right {
    width: 100%; /* The width is 100%, when the viewport is 800px or smaller */
  }
}
</style>
```

---

## HTML Computer Code Elements

HTML contains several elements for defining user input and computer code.The HTML `<code>` element is used to define a piece of computer code. The content inside is displayed in the browser's default monospace font.

> `<code>` element does not preserve extra whitespace and line-breaks. To fix this, you can put the `<code>` element inside a `<pre>` element.

- HTML `<kbd>` For Keyboard Input - Example: `<p>Save the document by pressing <kbd>Ctrl + S</kbd></p>`
- The HTML `<samp>` element is used to define sample output from a computer program. The content inside is displayed in the browser's default monospace font.

```html
<p>Message from my computer:</p>
<p>
  <samp>File not found.<br />Press F1 to continue</samp>
</p>
```

- The HTML `<var>` element is used to define a variable in programming or in a mathematical expression. The content inside is typically displayed in italic.

---

## What are Semantic Elements? (elemanhaye ba mani)

A semantic element clearly describes its meaning to both the browser and the developer.

Examples of **non-semantic elements**: `<div>` and `<span>` - Tells nothing about its content.
Examples of **semantic elements**: `<form>`, `<table>`, and `<article>` - Clearly defines its content.

## Semantic Elements in HTML

Many web sites contain HTML code like: `<div id="nav">` `<div class="header">` `<div id="footer">` to indicate navigation, header, and footer.

In HTML there are some semantic elements that can be used to define different parts of a web page:

`<article>`
`<aside>`
`<details>`
`<figcaption>`
`<figure>`
`<footer>`
`<header>`
`<main>`
`<mark>`
`<nav>`
`<section>`
`<summary>`
`<time>`

<center><img src="/HTML/Html%20Images%20Reference/17.png" alt="Picture" style="align=center" /></center>

### HTML `<section>` Element

The `<section>` element defines a section in a document. According to W3C's HTML documentation:
"A section is a thematic grouping of content, typically with a heading."

Examples of where a `<section>` element can be used:

1. Chapters
2. Introduction
3. News items
4. Contact information

Example:

```html
<section>
  <h1>WWF</h1>
  <p>
    The World Wide Fund for Nature (WWF) is an international organization
    working on issues regarding the conservation, research and restoration of
    the environment, formerly named the World Wildlife Fund. WWF was founded in
    1961.
  </p>
</section>

<section>
  <h1>WWF's Panda symbol</h1>
  <p>
    The Panda has become the symbol of WWF. The well-known panda logo of WWF
    originated from a panda named Chi Chi that was transferred from the Beijing
    Zoo to the London Zoo in the same year of the establishment of WWF.
  </p>
</section>
```

### HTML `<article>` Element

The `<article>` element specifies independent, self-contained content. An article should make sense on its own, and it should be possible to distribute it independently from the rest of the web site.

Examples of where the `<article>` element can be used:

1. Forum posts
2. Blog posts
3. User comments
4. Product cards
5. Newspaper articles

Example:

```html
<article>
  <h2>Google Chrome</h2>
  <p>
    Google Chrome is a web browser developed by Google, released in 2008. Chrome
    is the world's most popular web browser today!
  </p>
</article>

<article>
  <h2>Mozilla Firefox</h2>
  <p>
    Mozilla Firefox is an open-source web browser developed by Mozilla. Firefox
    has been the second most popular web browser since January, 2018.
  </p>
</article>

<article>
  <h2>Microsoft Edge</h2>
  <p>
    Microsoft Edge is a web browser developed by Microsoft, released in 2015.
    Microsoft Edge replaced Internet Explorer.
  </p>
</article>
```

#### Nesting `<article>` in `<section>` or Vice Versa?

you will find HTML pages with `<section>` elements containing `<article>` elements, and `<article>`elements containing `<section>` elements.

### HTML `<header>` Element

The `<header>` element represents a container for introductory content or a set of navigational links.
A `<header>` element typically contains:

1. one or more heading elements (`<h1>` - `<h6>`)
2. logo or icon
3. authorship information

> You can have several `<header>` elements in one HTML document.

a very possible Example:

```html
<article>
  <header>
    <h1>What Does WWF Do?</h1>
    <p>WWF's mission:</p>
  </header>
  <p>
    WWF's mission is to stop the degradation of our planet's natural
    environment, and build a future in which humans live in harmony with nature.
  </p>
</article>
```

### HTML `<footer>` Element

The `<footer>` element defines a footer for a document or section.
A `<footer>` element typically contains:

1. authorship information
2. copyright information
3. contact information
4. sitemap
5. back to top links
6. related documents

> You can have several `<footer>` elements in one document.

### HTML `<nav>` Element

The `<nav>` element defines a set of navigation links _Though_ _NOT_ all links of a document should be inside a `<nav>` element. The `<nav>` element is intended only for major blocks of navigation links.necessary for screen readers and for disabled users.

Example:

```html
<nav>
  <a href="/html/">HTML</a> | <a href="/css/">CSS</a> |
  <a href="/js/">JavaScript</a> |
  <a href="/jquery/">jQuery</a>
</nav>
```

### HTML `<aside>` Element

The `<aside>` element defines some content aside from the content it is placed in (like a sidebar).

Example:

```html
<html>
  <head>
    <style>
      aside {
        width: 30%;
        padding-left: 15px;
        margin-left: 15px;
        float: right;
        font-style: italic;
        background-color: lightgray;
      }
    </style>
  </head>
  <body>
    <p>
      My family and I visited The Epcot center this summer. The weather was
      nice, and Epcot was amazing! I had a great summer together with my family!
    </p>

    <aside>
      <p>
        The Epcot center is a theme park at Walt Disney World Resort featuring
        exciting attractions, international pavilions, award-winning fireworks
        and seasonal special events.
      </p>
    </aside>

    <p>
      My family and I visited The Epcot center this summer. The weather was
      nice, and Epcot was amazing! I had a great summer together with my family!
    </p>
    <p>
      My family and I visited The Epcot center this summer. The weather was
      nice, and Epcot was amazing! I had a great summer together with my family!
    </p>
  </body>
</html>
```

### HTML `<figure>` and `<figcaption>` Elements (kholase matlab ya aks)

The `<figure>` tag specifies self-contained content, like illustrations, diagrams, photos, code listings, etc.

The `<figcaption>` tag defines a caption for a `<figure>` element. The `<figcaption>` element can be placed as the first or as the last child of a `<figure>` element.

- The `<img>` element defines the actual image/illustration.

Example:

```html
<figure>
  <img src="pic_trulli.jpg" alt="Trulli" />
  <figcaption>Fig1. - Trulli, Puglia, Italy.</figcaption>
</figure>
```

---

## HTML Style Guide

A consistent, clean, and tidy HTML code makes it easier for others to read and understand your code.

- Always Declare Document Type: `<!DOCTYPE html>`
- Use Lowercase Element Names: `<body> <p> This is a paragraph. </p> </body>`
- Close All HTML Elements even simple ones: `<section> <p>This is a paragraph.</p> </section>`
- Use Lowercase Attribute Names: `<a href="https://www.w3schools.com/html/">Visit our HTML tutorial</a>`
- Always Quote Attribute Values: `<table class="striped">`
- Always Specify alt, width, and height for Images: `<img src="html5.gif" alt="HTML5" style="width:128px;height:128px">`
- space-less is easier to read and groups entities better together: `<link rel="stylesheet" href="styles.css">`
- Avoid Long Code Lines.
- Do not add blank lines, spaces, or indentations without a reason.
- For readability, add blank lines to separate large or logical code blocks.
- For readability, add two spaces of indentation. Do not use the tab key.
  Example:

```html
<body>
  <h1>Famous Cities</h1>

  <h2>Tokyo</h2>
  <p>
    Tokyo is the capital of Japan, the center of the Greater Tokyo Area, and the
    most populous metropolitan area in the world.
  </p>

  <h2>London</h2>
  <p>
    London is the capital city of England. It is the most populous city in the
    United Kingdom.
  </p>

  <h2>Paris</h2>
  <p>
    Paris is the capital of France. The Paris area is one of the largest
    population centers in Europe.
  </p>
</body>
```

- Never Skip the `<title>` Element for your document: `<title> HTML Style Guide and Coding Conventions </title>`
- Do'nt forget `<html>`, `<body>` and `<head>`.
- Add the lang and charset Attribute: `<html lang="en-us"> <head> <meta charset="UTF-8"> <title>Page Title </title> </head>`

---

## HTML Entities and symbols

- A commonly used entity in HTML is the non-breaking space: 10`&nbsp;`km/h -> 10 km/h

| Result | Description                        | Entity Name | Entity Number |
| ------ | ---------------------------------- | ----------- | ------------- |
|        | non-breaking space                 | `&nbsp;`    | `&#160;`      |
| <      | less than                          | `&lt;`      | `&#60;`       |
| >      | greater than                       | `&gt;`      | `&#62;`       |
| &      | ampersand                          | `&amp;`     | `&#38;`       |
| "      | double quotation mark              | `&quot;`    | `&#34;`       |
| '      | single quotation mark (apostrophe) | `&apos;`    | `&#39;`       |
| ¢      | cent                               | `&cent;`    | `&#162;`      |
| £      | pound                              | `&pound;`   | `&#163;`      |
| ¥      | yen                                | `&yen;`     | `&#165;`      |
| €      | euro                               | `&euro;`    | `&#8364;`     |
| ©      | copyright                          | `&copy;`    | `&#169;`      |
| ®      | registered trademark               | `&reg;`     | `&#174;`      |

- Entity names are case sensitive.

[Full Currency Reference](https://www.w3schools.com/charsets/ref_utf_currency.asp), [Full Arrows Reference](https://www.w3schools.com/charsets/ref_utf_arrows.asp), [Full Symbols Reference](https://www.w3schools.com/charsets/ref_utf_symbols.asp).

### Emoji Characters

Emojis are characters from the UTF-8 alphabet.
Example:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
  </head>
  <body>
    <h1>My First Emoji</h1>

    <p>&#128512;</p>
  </body>
</html>
```

[HTML Emoji Reference](https://www.w3schools.com/charsets/ref_emoji.asp).

### HTML Encoding (Character Sets)

The HTML5 specification encourages web developers to use the UTF-8 character set, which covers almost all of the characters and symbols in the world!

### HTML Uniform Resource Locators (URL Encode)

A URL is another word for a web address. A URL can be composed of words (e.g. w3schools.com), or an Internet Protocol (IP) address (e.g. 192.68.20.50).

A web address like `https://www.w3schools.com/html/default.asp` follows these syntax rules:
`scheme://prefix.domain:port/path/filename`

Explanation:

- scheme - defines the type of Internet service (most common is http or https)
- prefix - defines a domain prefix (default for http is www)
- domain - defines the Internet domain name (like w3schools.com)
- port - defines the port number at the host (default for http is 80)
- path - defines a path at the server (If omitted: the root directory of the site)
- filename - defines the name of a document or resource.

### Common URL Schemes

| Scheme | Short for                          | Used for                        |
| ------ | ---------------------------------- | ------------------------------- |
| http   | HyperText Transfer Protocol        | Common web pages. Not encrypted |
| https  | Secure HyperText Transfer Protocol | Secure web pages. Encrypted     |
| ftp    | File Transfer Protocol             | Downloading or uploading files  |
| file   |                                    | A file on your computer         |

#### URL Encoding

URLs can only be sent over the Internet using the ASCII character-set. If a URL contains characters outside the ASCII set, the URL has to be converted using URL encoding.
**URL encoding replaces non-ASCII** characters **with a "%" followed by hexadecimal digits**.
URLs cannot contain spaces. **URL encoding** normally **replaces a space with** a plus (+) sign, or **%20**.
[URL Encoding Reference](https://www.w3schools.com/tags/ref_urlencode.asp).

## What is XHTML?

XHTML is a stricter, more XML-based version of HTML.stands for E**X**tensible **H**yper**T**ext **M**arkup **L**anguage.
XHTML was developed to make HTML more extensible and flexible to work with other data formats (such as XML). In addition, browsers ignore errors in HTML pages, and try to display the website even if it has some errors in the markup. So XHTML comes with a much stricter error handling.

### The Most Important Differences from HTML

- <!DOCTYPE> is mandatory.
- The xmlns attribute in `<html>` is mandatory.
- `<html>`, `<head>`, `<title>`, and `<body>` are mandatory.
- Elements must always be properly nested.
- Elements must always be closed.
- Elements must always be in lowercase.
- Attribute names must always be in lowercase.
- Attribute values must always be quoted.
- Attribute minimization is forbidden.

---

## HTML Forms

An HTML form is used to collect user input. The user input is most often sent to a server for processing.

<center><img src="/HTML/Html%20Images%20Reference/18.png" alt="Picture" style="align=center" /></center>

- List of All `<form>` _Attributes_

| Attribute      | Description                                                                                             |
| -------------- | ------------------------------------------------------------------------------------------------------- |
| accept-charset | Specifies the character encodings used for form submission                                              |
| action         | Specifies where to send the form-data when a form is submitted                                          |
| autocomplete   | Specifies whether a form should have autocomplete on or off                                             |
| enctype        | Specifies how the form-data should be encoded when submitting it to the server (only for method="post") |
| method         | Specifies the HTTP method to use when sending form-data                                                 |
| name           | Specifies the name of the form                                                                          |
| novalidate     | Specifies that the form should not be validated when submitted                                          |
| rel            | Specifies the relationship between a linked resource and the current document                           |
| target         | Specifies where to display the response that is received after submitting the form                      |

- HTML Form Elements

| Tag          | Description                                                |
| ------------ | ---------------------------------------------------------- |
| `<form>`     | Defines an HTML form for user input                        |
| `<input>`    | Defines an input control                                   |
| `<textarea>` | Defines a multiline input control (text area)              |
| `<label>`    | Defines a label for an `<input>` element                   |
| `<fieldset>` | Groups related elements in a form                          |
| `<legend>`   | Defines a caption for a `<fieldset>` element               |
| `<select>`   | Defines a drop-down list                                   |
| `<optgroup>` | Defines a group of related options in a drop-down list     |
| `<option>`   | Defines an option in a drop-down list                      |
| `<button>`   | Defines a clickable button                                 |
| `<datalist>` | Specifies a list of pre-defined options for input controls |
| `<output>`   | Defines the result of a calculation                        |

- The `<form>` Element - used to create an HTML form for user input. `<form>` element is a container for different types of input elements, such as: text fields, checkboxes, radio buttons, submit buttons, etc.
- The HTML `<input>` element is the most used form element.can be displayed in many ways, depending on the **type** attribute.
  |Type| Description|
  |--|--|
  |`<input type="text">`| Displays a single-line text input field|
  |`<input type="radio">`| Displays a radio button (for selecting one of many choices)|
  |`<input type="checkbox"`>| Displays a checkbox (for selecting zero or more of many choices)|
  |`<input type="submit">`| Displays a submit button (for submitting the form)|
  |`<input type="button"`>`| Displays a clickable button|

### Label element

- The `<label>` tag defines a label for many form elements. The **for** attribute of the `<label>` tag should be equal to the **id** attribute of the `<input>` element to bind them together.
  > The `<label>` element is useful for screen-reader users, because the screen-reader will read out loud the label when the user focus on the input element.
- default width of an input field is 20 characters.
  Example:

```html
<form>
  <label for="fname">First name:</label><br />
  <input type="text" id="fname" name="fname" /><br />
  <label for="lname">Last name:</label><br />
  <input type="text" id="lname" name="lname" />
</form>
```

### Radio Buttons

The `<input type="radio">` defines a radio button. Radio buttons let a user select ONE of a limited number of choices.
Example:

```html
<p>Choose your favorite Web language:</p>

<form>
  <input type="radio" id="html" name="fav_language" value="HTML" />
  <label for="html">HTML</label><br />
  <input type="radio" id="css" name="fav_language" value="CSS" />
  <label for="css">CSS</label><br />
  <input type="radio" id="javascript" name="fav_language" value="JavaScript" />
  <label for="javascript">JavaScript</label>
</form>
```

<center><img src="/HTML/Html%20Images%20Reference/19.png" alt="Picture" style="align=center" /></center>

### Checkboxes

The `<input type="checkbox">` defines a checkbox. Checkboxes let a user select ZERO or MORE options of a limited number of choices.
Example:

```html
<form>
  <input type="checkbox" id="vehicle1" name="vehicle1" value="Bike" />
  <label for="vehicle1"> I have a bike</label><br />
  <input type="checkbox" id="vehicle2" name="vehicle2" value="Car" />
  <label for="vehicle2"> I have a car</label><br />
  <input type="checkbox" id="vehicle3" name="vehicle3" value="Boat" />
  <label for="vehicle3"> I have a boat</label>
</form>
```

<center><img src="/HTML/Html%20Images%20Reference/20.png" alt="Picture" style="align=center" /></center>

### The Submit Button

The `<input type="submit">` defines a button for submitting the form data to a form-handler. The form-handler is typically a file on the server with a script for processing input data.

- The form-handler is specified in the form's **action** attribute.

Example:

```html
<form action="/action_page.php">
  <label for="fname">First name:</label><br />
  <input type="text" id="fname" name="fname" value="John" /><br />
  <label for="lname">Last name:</label><br />
  <input type="text" id="lname" name="lname" value="Doe" /><br /><br />
  <input type="submit" value="Submit" />
</form>
```

- Notice that each input field must have a name attribute to be submitted. If the name attribute is omitted, the value of the input field will not be sent at all.

<center><img src="/HTML/Html%20Images%20Reference/21.png" alt="Picture" style="align=center" /></center>

### The **action** attribute

- The **action** attribute defines the action to be performed when the form is submitted.
  In the example below, the form data is sent to a file called "action_page.php". This file contains a server-side script that handles the form data:

```html
<form action="/action_page.php">
  <label for="fname">First name:</label><br />
  <input type="text" id="fname" name="fname" value="John" /><br />
  <label for="lname">Last name:</label><br />
  <input type="text" id="lname" name="lname" value="Doe" /><br /><br />
  <input type="submit" value="Submit" />
</form>
```

### The **target** attribute

The **target** attribute specifies [where to display the response that is received after submitting](./HTML.md) the form.

The target attribute values:
|Value| Description|
|--|--|
|\_blank| The response is displayed in a new window or tab|
|\_self |The response is displayed in the current window|
|\_parent| The response is displayed in the parent frame|
|\_top| The response is displayed in the full body of the window|
|framename| The response is displayed in a named iframe|

Example: `<form action="/action_page.php" target="_blank">`

- The method attribute specifies the HTTP method to be used when submitting the form data. The form-data can be sent as URL variables (with `method="get"`) or as HTTP post transaction (with `method="post"`).
  > The default HTTP method when submitting form data is GET. Example: `<form action="/action_page.php" method="get">`, `<form action="/action_page.php" method="post">`

#### Notes on GET

1. Appends the form data to the URL, in name/value pairs
2. NEVER use GET to send sensitive data! (the submitted form data is visible in the URL!) Use Post Method instead.
3. The length of a URL is limited (2048 characters)
4. Useful for form submissions where a user wants to bookmark the result
5. GET is good for non-secure data, like query strings in Google

#### Notes on POST

1. Appends the form data inside the body of the HTTP request (the submitted form data is not shown in the URL)
2. POST has no size limitations, and can be used to send large amounts of data.
3. Form submissions with POST cannot be bookmarked

### The Autocomplete Attribute

The autocomplete attribute specifies whether a form should have autocomplete on or off. When autocomplete is on, the browser automatically complete values based on values that the user has entered before.
Example: `<form action="/action_page.php" autocomplete="on">`

### The Novalidate Attribute

The novalidate attribute is a boolean attribute. When present, it specifies that the form-data (input) should not be validated when submitted.
Example: `<form action="/action_page.php" novalidate>`

### HTML Form Elements

The HTML `<form>` element can contain one or more of the following form elements:

- `<input>` - One of the most used form element.
- `<label>` - defines a label for several form elements.
- `<select>` - defines a drop-down list. Example:

```html
<!-- 
The <option> elements defines an option that can be selected.
By default, the first item in the drop-down list is selected.
-->
<label for="cars">Choose a car:</label>
<select id="cars" name="cars">
  <option value="volvo">Volvo</option>
  <option value="saab">Saab</option>

  <!--
  To define a pre-selected option, add the selected attribute to the option: 
  -->
  <option value="fiat" selected>Fiat</option>
  <!--
  Use the multiple attribute to allow the user to select more than one value:
  -->
  <option value="audi" multiple>Audi</option>
</select>
```

- `<textarea>` defines a multi-line input field (a text area). Example:

```html
<textarea name="message" rows="10" cols="30">
The cat was playing in the garden.
</textarea>
<!--
The rows attribute specifies the visible number of lines in a text area.
The cols attribute specifies the visible width of a text area.
-->
```

- `<button>` defines a clickable button. Example: `<button type="button" onclick="alert('Hello World!')">Click Me!</button>`
- `<fieldset>` - is used to group related data in a form And `<legend>` defines a caption for the `<fieldset>` Example:

```html
<form action="/action_page.php">
  <fieldset>
    <legend>Personals:</legend>
    <label for="fname">First name:</label><br />
    <input type="text" id="fname" name="fname" value="John" /><br />
    <label for="lname">Last name:</label><br />
    <input type="text" id="lname" name="lname" value="Doe" /><br /><br />
    <input type="submit" value="Submit" />
  </fieldset>
</form>
```

<center><img src="/HTML/Html%20Images%20Reference/22.png" alt="Picture" style="align=center" /></center>

- `<datalist>`, `list` - specifies a list of pre-defined options for an `<input>` element. Users will see a drop-down list of the pre-defined options as they input data. The **list** attribute of the `<input>` element, must refer to the **id** attribute of the `<datalist>` element.

Example:

```html
<form action="/action_page.php">
  <input list="browsers" />
  <datalist id="browsers">
    <option value="Internet Explorer"></option>
    <option value="Firefox"></option>
    <option value="Chrome"></option>
    <option value="Opera"></option>
    <option value="Safari"></option>
  </datalist>
</form>
```

- `<output>` - represents the result of a calculation (like one performed by a script but not a good way!).

---

### HTML Input Types

> The default value of the type attribute is "text"

Here are the different input types you can use in HTML:

- `<input type="text">` - defines a single-line text input field.
- `<input type="button">` - defines a button. `<input type="button" onclick="alert('Hello World!')" value="Click Me!">`
- `<input type="checkbox">` - defines a checkbox.
- `<input type="color">` - used for input fields that should contain a color. (pops up color picker from browser itself)
- `<input type="date">` - input fields that should contain a date. (pops up date picker from browser itself). You can also use the min and max attributes to add restrictions to dates:

```html
<form>
  <label for="datemax">Enter a date before 1980-01-01:</label>
  <input type="date" id="datemax" name="datemax" max="1979-12-31" /><br /><br />
  <label for="datemin">Enter a date after 2000-01-01:</label>
  <input type="date" id="datemin" name="datemin" min="2000-01-02" />
</form>
```

- `<input type="datetime-local">` - specifies a date and time input field, with no time zone. (pops up date picker from browser itself).
- `<input type="email">` - input fields that should contain an e-mail address. (the e-mail address can be automatically validated when submitted)

> Some smartphones recognize the email type, and add ".com" to the keyboard to match email input.

- `<input type="file">` - defines a file-select field and a "Browse" button for file uploads. Example:

```html
<form>
  <label for="my-file">Select a file:</label>
  <input type="file" id="my-file" name="my-file" />
</form>
```

- `<input type="hidden">` - defines a hidden input field (not visible to a user).
  > A hidden field lets web developers include data that cannot be seen or modified by users when a form is submitted.
  > A hidden field often stores what database record that needs to be updated when the form is submitted.

Note: While the value is not displayed to the user in the page's content, it is visible (and can be edited) using any browser's developer tools or "View Source" functionality. Do not use hidden inputs as a form of security!

Example:

```html
<input type="hidden" id="custId" name="custId" value="3487" />
```

- `<input type="image">` - defines an image as a submit button. The path to the image is specified in the src attribute. (**Does't inputs image to form!**)
- `<input type="month">` - allows the user to select a month and year. (pops up date picker from browser itself)
- `<input type="number">` - defines a numeric input field. Example:

```html
<form>
  <label for="quantity">Quantity (between 1 and 5):</label>
  <input type="number" id="quantity" name="quantity" min="1" max="5" />
</form>
```

- `<input type="password">` - defines a password field.
- `<input type="radio">` - defines a radio button.
- `<input type="range">` - defines a control for entering a number whose exact value is not important. Default range is 0 to 100. However, you can set restrictions on what numbers are accepted with the min, max, and step attributes
- `<input type="reset">` - defines a reset button that will reset all form values to their default values.`<input type="submit" value="Submit"> <input type="reset">`
- `<input type="search">` - is used for search fields (a search field behaves like a regular text field).
- `<input type="submit">` - defines a button for submitting form data. `<input type="submit" value="Submit(namayesh)">`
- `<input type="tel">` - input fields that should contain a telephone number. Example:

```html
<form>
  <label for="phone">Enter your phone number:</label>
  <input
    type="tel"
    id="phone"
    name="phone"
    pattern="[0-9]{3}-[0-9]{2}-[0-9]{3}"
  />
</form>
```

- `<input type="time">` - allows the user to select a time (no time zone).(pops up time picker from browser itself)
- `<input type="url">` - input fields that should contain a URL address. the url field can be automatically validated when submitted.
  > Some smartphones recognize the url type, and adds ".com" to the keyboard to match url input.
- `<input type="week">` - allows the user to select a week and year.(pops up date picker from browser itself)

### Input Restrictions

Here is a list of some common input restrictions:

| Attribute | Description                                                                                                    |
| --------- | -------------------------------------------------------------------------------------------------------------- |
| checked   | Specifies that an input field should be pre-selected when the page loads (for type="checkbox" or type="radio") |
| disabled  | Specifies that an input field should be disabled                                                               |
| max       | Specifies the maximum value for an input field                                                                 |
| maxlength | Specifies the maximum number of character for an input field                                                   |
| min       | Specifies the minimum value for an input field                                                                 |
| pattern   | Specifies a regular expression to check the input value against                                                |
| readonly  | Specifies that an input field is read only (cannot be changed)                                                 |
| required  | Specifies that an input field is required (must be filled out)                                                 |
| size      | Specifies the width (in characters) of an input field                                                          |
| step      | Specifies the legal number intervals for an input field                                                        |
| value     | Specifies the default value for an input field                                                                 |

> Note: Input restrictions are not foolproof, and JavaScript provides many ways to add illegal input. To safely restrict input, it must also be checked by the receiver (the server)!

### HTML Input Attributes

- The input `readonly` attribute specifies that an input field is read-only. user can tab to it, highlight it, and copy the text from it. The value of a read-only input field will be sent when submitting the form!
  Example: `<input type="text" id="fname" name="fname" value="John" readonly><br>`
- The input `disabled` attribute specifies that an input field should be disabled. A disabled input field is unusable and un-clickable. The value of a disabled input field will not be sent when submitting the form!
  Example: `<input type="text" id="fname" name="fname" value="John" disabled><br>`
- The input `size` attribute specifies the visible width, in characters, of an input field. The default value for size is 20.
  > Note: The size attribute works with the following input types: text, search, tel, url, email, and password.

Example: `<input type="text" id="fname" name="fname" size="50"><br>`

- The input `maxlength` attribute specifies the maximum number of characters allowed in an input field.
  > Note: When a maxlength is set, the input field will not accept more than the specified number of characters. However, this attribute does not provide any feedback.

Example: `<input type="text" id="pin" name="pin" maxlength="4" size="4">`

- The input `min` and `max` attributes specify the minimum and maximum values for an input field. The min and max attributes work with the following input types: number, range, date, datetime-local, month, time and week.
  > Tip: Use the max and min attributes together to create a range of legal values.

Example:

```html
<form>
  <label for="datemax">Enter a date before 1980-01-01:</label>
  <input type="date" id="datemax" name="datemax" max="1979-12-31" /><br /><br />

  <label for="datemin">Enter a date after 2000-01-01:</label>
  <input type="date" id="datemin" name="datemin" min="2000-01-02" /><br /><br />

  <label for="quantity">Quantity (between 1 and 5):</label>
  <input type="number" id="quantity" name="quantity" min="1" max="5" />
</form>
```

- The input `pattern` attribute specifies a [regular expression](https://www.w3schools.com/js/js_regexp.asp) that the input field's value is checked against, when the form is submitted. The pattern attribute works with the following input types: text, date, search, url, tel, email, and password.
  > Tip: Use the global title attribute to describe the pattern to help the user.

Example:

```html
<form>
  <label for="country_code">Country code:</label>
  <input
    type="text"
    id="country_code"
    name="country_code"
    pattern="[A-Za-z]{3}"
    title="Three letter country code"
  />
</form>
```

- The input `placeholder` attribute specifies a short hint that describes the expected value of an input field (a sample value or a short description of the expected format). The short hint is displayed in the input field before the user enters a value. The placeholder attribute works with the following input types: text, search, url, tel, email, and password.
  Example:

```html
<form>
  <label for="phone">Enter a phone number:</label>
  <input
    type="tel"
    id="phone"
    name="phone"
    placeholder="123-45-678"
    pattern="[0-9]{3}-[0-9]{2}-[0-9]{3}"
  />
</form>
```

- The input `required` attribute specifies that an input field must be filled out before submitting the form. The required attribute works with the following input types: text, search, url, tel, email, password, date pickers, number, checkbox, radio, and file.
  Example: `<input type="text" id="username" name="username" required>`
- The input `step` attribute specifies the legal number intervals for an input field. Example: if step="3", legal numbers could be -3, 0, 3, 6, etc. The step attribute works with the following input types: number, range, date, datetime-local, month, time and week. Example: `<input type="number" id="points" name="points" step="3">`
- The input `autofocus` attribute specifies that an input field should automatically get focus when the page loads.
  Example:

```html
<form>
  <label for="fname">First name:</label><br />
  <input type="text" id="fname" name="fname" autofocus /><br />
  <label for="lname">Last name:</label><br />
  <input type="text" id="lname" name="lname" />
</form>
```

### HTML Input `form*` Attributes

- The `input form` attribute specifies the form the `<input>` element belongs to. The value of this attribute must be equal to the id attribute of the `<form>` element it belongs to.

Example:
An input field located outside of the HTML form (but still a part of the form)

```html
<form action="/action_page.php" id="form1">
  <label for="fname">First name:</label>
  <input type="text" id="fname" name="fname" /><br /><br />
  <input type="submit" value="Submit" />
</form>

<label for="lname">Last name:</label>
<input type="text" id="lname" name="lname" form="form1" />
```

- The `input formaction` or form action attribute specifies the URL of the file that will process the input when the form is submitted. Note: This attribute overrides the action attribute of the `<form>` element. The formaction attribute works with the following input types: submit and image.

Example:
An HTML form with two submit buttons, with different actions

```html
<form action="/action_page.php">
  <label for="fname">First name:</label>
  <input type="text" id="fname" name="fname" /><br /><br />
  <label for="lname">Last name:</label>
  <input type="text" id="lname" name="lname" /><br /><br />
  <input type="submit" value="Submit" />
  <input type="submit" formaction="/action_page2.php" value="Submit as Admin" />
</form>
```

- The `input formenctype` or form encrypt attribute specifies how the form-data should be encoded when submitted (only for forms with **method="post"**). The formenctype attribute works with the following input types: submit and image.
  > Note: This attribute overrides the enctype attribute of the `<form>` element.

Example:
A form with two submit buttons. The first sends the form-data with default encoding, the second sends the form-data encoded as "multipart/form-data"

```html
<form action="/action_page_binary.asp" method="post">
  <label for="fname">First name:</label>
  <input type="text" id="fname" name="fname" /><br /><br />
  <input type="submit" value="Submit" />
  <input
    type="submit"
    formenctype="multipart/form-data"
    value="Submit as Multipart/form-data"
  />
</form>
```

- The `input formmethod` or form method attribute defines the HTTP method for sending form-data to the action URL. works with the following input types: submit and image. The form-data can be sent as Get method or Post Method.
  > Note: This attribute overrides the method attribute of the `<form>` element.

Example:
A form with two submit buttons. The first sends the form-data with method="get". The second sends the form-data with method="post".

```html
<form action="/action_page.php" method="get">
  <label for="fname">First name:</label>
  <input type="text" id="fname" name="fname" /><br /><br />
  <label for="lname">Last name:</label>
  <input type="text" id="lname" name="lname" /><br /><br />
  <input type="submit" value="Submit using GET" />
  <input type="submit" formmethod="post" value="Submit using POST" />
</form>
```

- The `input formtarget` or form target attribute specifies a name or a keyword that indicates where to display the response that is received after submitting the form. works with the following input types: submit and image.
  > Note: This attribute overrides the target attribute of the `<form>` element.

Example:
A form with two submit buttons, with different target windows:

```html
<form action="/action_page.php">
  <label for="fname">First name:</label>
  <input type="text" id="fname" name="fname" /><br /><br />
  <label for="lname">Last name:</label>
  <input type="text" id="lname" name="lname" /><br /><br />
  <input type="submit" value="Submit" />
  <input type="submit" formtarget="_blank" value="Submit to a new window/tab" />
</form>
```

- The `input formnovalidate`or form no validate attribute specifies that an `<input>` element should not be validated when submitted. works with the following input types: submit.
  > Note: This attribute overrides the novalidate attribute of the `<form>` element.

Example:
A form with two submit buttons (with and without validation)

```html
<form action="/action_page.php">
  <label for="email">Enter your email:</label>
  <input type="email" id="email" name="email" /><br /><br />
  <input type="submit" value="Submit" />
  <input
    type="submit"
    formnovalidate="formnovalidate"
    value="Submit without validation"
  />
</form>
```

---

## HTML Canvas Graphics

The HTML `<canvas>` element is used to draw graphics on the fly, via JavaScript. For more information check [canvas on w3schools](https://www.w3schools.com/html/html5_canvas.asp).

## HTML SVG Graphics

SVG (stands for Scalable Vector Graphics) defines vector-based graphics in XML format. For more information check [SVG on w3schools](https://www.w3schools.com/html/html5_svg.asp).

---

## HTML Multimedia

- In **video** The MP4, WebM, and Ogg formats are supported by HTML.
- MP3, WAV, and Ogg **audio** are supported by the HTML standard.
- The HTML `<video>` element is used to show a video on a web page. Example:

```html
<video width="320" height="240" controls autoplay muted>
  <!--adds video controls, like play, pause, and volume. To start a video automatically we use autoplay.-->
  <source src="movie.mp4" type="video/mp4" />
  <source src="movie.ogg" type="video/ogg" />
  Your browser does not support the video tag.
</video>
```

> Chromium browsers do not allow autoplay in most cases. However, muted autoplay is always allowed.

- To play an audio file in HTML, use the `<audio>` element:

---

## HTML Plug-ins

Plug-ins were designed to be used for many different purposes like: To display maps, scan for viruses, verify a bank id and many more.

- The `<object>` & `<embed>` Element - defines an embedded object (like plug-ins) within an HTML document.
  > Web browsers have supported the `<embed>` element for a long time. However, it has not been a part of the HTML specification before HTML5.

in order to show youtube video the recommend way is this:

```html
<iframe
  width="420"
  height="315"
  src="https://www.youtube.com/embed/tgbNymZ7vqY"
>
</iframe>
<!--Add mute=1 after autoplay=1 to let your video start playing automatically (but muted).-->
<iframe
  width="420"
  height="315"
  src="https://www.youtube.com/embed/tgbNymZ7vqY?autoplay=1&mute=1"
>
</iframe>
<!--Add loop=1 to let your video loop forever.-->
<iframe
  width="420"
  height="315"
  src="https://www.youtube.com/embed/tgbNymZ7vqY?playlist=tgbNymZ7vqY&loop=1"
>
</iframe>
<!--Add controls=0 to not display controls in the video player.-->
<iframe
  width="420"
  height="315"
  src="https://www.youtube.com/embed/tgbNymZ7vqY?controls=0"
>
</iframe>
```

---

## HTML APIs

### HTML Geolocation API

The HTML Geolocation API is used to locate a user's position.

> Since this can compromise privacy, the position is not available unless the user approves it.

- The `getCurrentPosition()` method in javascript is used to return the user's position.

```JavaScript
<script>
var x = document.getElementById("demo");
function getLocation() {
  if (navigator.geolocation) {
    navigator.geolocation.getCurrentPosition(showPosition);
  } else {
    x.innerHTML = "Geolocation is not supported by this browser.";
  }
}

function showPosition(position) {
  x.innerHTML = "Latitude: " + position.coords.latitude +
  "<br>Longitude: " + position.coords.longitude;
}
</script>
```

Example explained:

- Check if Geolocation is supported
- If supported, run the getCurrentPosition() method. If not, display a message to the user
- If the getCurrentPosition() method is successful, it returns a coordinates object to the function specified in the parameter (showPosition)
- The showPosition() function outputs the Latitude and Longitude

The example above is a very basic Geolocation script, with no error handling. to handle the error and rejections use below JavaScript code:

```JavaScript
function showError(error) {
  switch(error.code) {
    case error.PERMISSION_DENIED:
      x.innerHTML = "User denied the request for Geolocation."
      break;
    case error.POSITION_UNAVAILABLE:
      x.innerHTML = "Location information is unavailable."
      break;
    case error.TIMEOUT:
      x.innerHTML = "The request to get user location timed out."
      break;
    case error.UNKNOWN_ERROR:
      x.innerHTML = "An unknown error occurred."
      break;
  }
}
```

Geolocation is also very useful for location-specific information, like:

- Up-to-date local information
- Showing Points-of-interest near the user
- Turn-by-turn navigation (GPS)

The other properties are returned if available:

| Property                | Returns                                                                 |
| ----------------------- | ----------------------------------------------------------------------- |
| coords.latitude         | The latitude as a decimal number (always returned)                      |
| coords.longitude        | The longitude as a decimal number (always returned)                     |
| coords.accuracy         | The accuracy of position (always returned)                              |
| coords.altitude         | The altitude in meters above the mean sea level (returned if available) |
| coords.altitudeAccuracy | The altitude accuracy of position (returned if available)               |
| coords.heading          | The heading as degrees clockwise from North (returned if available)     |
| coords.speed            | The speed in meters per second (returned if available)                  |
| timestamp               | The date/time of the response (returned if available)                   |

The Geolocation object also has other interesting methods:

`watchPosition()` - Returns the current position of the user and continues to return updated position as the user moves (like the GPS in a car).
`clearWatch()` - Stops the `watchPosition()` method.
The example below shows the watchPosition() method.

```JavaScript
<script>
var x = document.getElementById("demo");
function getLocation() {
  if (navigator.geolocation) {
    navigator.geolocation.watchPosition(showPosition);
  } else {
    x.innerHTML = "Geolocation is not supported by this browser.";
  }
}
function showPosition(position) {
  x.innerHTML = "Latitude: " + position.coords.latitude +
  "<br>Longitude: " + position.coords.longitude;
}
</script>
```

### HTML Drag and Drop API

In HTML, any element can be dragged and dropped like example below:

```html
<!DOCTYPE html>
<html>
  <head>
    <script>
      //4. By default, data/elements cannot be dropped in other elements. To allow a drop, we must prevent the default handling of the element.
      function allowDrop(ev) {
        ev.preventDefault();
      }
      //3. The dataTransfer.setData() method sets the data type and the value of the dragged data
      function drag(ev) {
        ev.dataTransfer.setData("text", ev.target.id);
      }

      function drop(ev) {
        ev.preventDefault(); //5. Call preventDefault() to prevent the browser default handling of the data (default is open as link on drop)
        var data = ev.dataTransfer.getData("text"); //6. Get the dragged data with the dataTransfer.getData() method. This method will return any data that was set to the same type in the setData() method
        ev.target.appendChild(document.getElementById(data)); //7. Append the dragged element into the drop element
      }
    </script>
  </head>
  <body>
    <div id="div1" ondrop="drop(event)" ondragover="allowDrop(event)"></div>
    <!--
      1. `draggable` makes an element draggable
      2. the `ondragstart` attribute calls a function, drag(event), that specifies what data to be dragged.
    -->
    <img
      id="drag1"
      src="img_logo.gif"
      draggable="true"
      ondragstart="drag(event)"
      width="336"
      height="69"
    />
  </body>
</html>
```

### HTML Web Storage API

> HTML web storage; better than cookies. Before HTML5, application data had to be stored in cookies, included in every server request. Web storage is more secure, and large amounts of data can be stored locally, without affecting website performance. Unlike cookies, the storage limit is far larger (at least 5MB) and information is never transferred to the server.

#### HTML Web Storage Objects

HTML web storage provides two objects for storing data on the client:

- `window.localStorage` - stores data with no expiration date (The data will not be deleted when the browser is closed, and will be available the next day, week, or year.)
  Example:

```html
<!--
Store
Create a localStorage name/value pair with name="lastname" and value="Smith"
-->
localStorage.setItem("lastname", "Smith");

<!--
Retrieve
Retrieve the value of "lastname" and insert it into the element with id="result"
-->
document.getElementById("result").innerHTML = localStorage.getItem("lastname");
```

The example above could also be written like this:

```html
<!-- Store -->
localStorage.lastname = "Smith";
<!-- Retrieve -->
document.getElementById("result").innerHTML = localStorage.lastname;
```

> he syntax for removing the "lastname" localStorage item is as follows: `localStorage.removeItem("lastname");`

The following example counts the number of times a user has clicked a button. In this code the value string is converted to a number to be able to increase the counter:

```JavaScript
if (localStorage.clickcount) {
  localStorage.clickcount = Number(localStorage.clickcount) + 1;
} else {
  localStorage.clickcount = 1;
}
document.getElementById("result").innerHTML = "You have clicked the button " +
localStorage.clickcount + " time(s).";
```

- `window.sessionStorage` - stores data for one session (data is lost when the browser tab is closed)
  The following example counts the number of times a user has clicked a button, in the current session:

```JavaScript
if (sessionStorage.clickcount) {
  sessionStorage.clickcount = Number(sessionStorage.clickcount) + 1;
} else {
  sessionStorage.clickcount = 1;
}
document.getElementById("result").innerHTML = "You have clicked the button " +
sessionStorage.clickcount + " time(s) in this session.";
```

### HTML Web Workers API

A web worker is a JavaScript running in the background, without affecting the performance of the page.When executing scripts in an HTML page, the page becomes unresponsive until the script is finished. with web worker JavaScript independently of other scripts, without affecting the performance of the page, runs in the background.

Now, let's create our web worker in an external JavaScript.
The script is stored in the "demo_workers.js" file:

```JavaScript
var i = 0;

function timedCount() {
  i = i + 1;
  postMessage(i);
  setTimeout("timedCount()",500);
}

timedCount();
```

The important part of the code above is the `postMessage()` method - which is used to post a message back to the HTML page.

Add an "onmessage" event listener to the web worker.

```JavaScript
w.onmessage = function(event){
  document.getElementById("result").innerHTML = event.data;
};
```

When the web worker posts a message, the code within the event listener is executed. The data from the web worker is stored in event.data.

> to terminate a web worker use : `w.terminate();`

a complete Example:

```html
<!DOCTYPE html>
<html>
  <body>
    <p>Count numbers: <output id="result"></output></p>
    <button onclick="startWorker()">Start Worker</button>
    <button onclick="stopWorker()">Stop Worker</button>

    <p>
      <strong>Note:</strong> Internet Explorer 9 and earlier versions do not
      support Web Workers.
    </p>

    <script>
      var w;

      function startWorker() {
        if (typeof Worker !== "undefined") {
          if (typeof w == "undefined") {
            w = new Worker("demo_workers.js");
          }
          w.onmessage = function (event) {
            document.getElementById("result").innerHTML = event.data;
          };
        } else {
          document.getElementById("result").innerHTML =
            "Sorry, your browser does not support Web Workers...";
        }
      }

      function stopWorker() {
        w.terminate();
        w = undefined;
      }
    </script>
  </body>
</html>
```

### HTML SSE API

Server-Sent Events (SSE) allow a web page to get updates from a server.
A server-sent event is when a web page automatically gets updates from a server. but it's One Way Messaging.

- The EventSource object is used to receive server-sent event notifications:

```JavaScript
var source = new EventSource("demo_sse.php");
source.onmessage = function(event) {
  document.getElementById("result").innerHTML += event.data + "<br>";
};
```

Example explained:

- Create a new EventSource object, and specify the URL of the page sending the updates (in this example "demo_sse.php")
- Each time an update is received, the onmessage event occurs
- When an onmessage event occurs, put the received data into the element with id="result"

#### Server-Side Code Example

The server-side event stream syntax is simple. Set the "Content-Type" header to "text/event-stream". Now you can start sending event streams.

Code in PHP (demo_sse.php):

```php
<?php
header('Content-Type: text/event-stream');
header('Cache-Control: no-cache');

$time = date('r');
echo "data: The server time is: {$time}\n\n";
flush();
?>
```

Code explained:

- Set the "Content-Type" header to "text/event-stream"
- Specify that the page should not cache
- Output the data to send (Always start with "data: ")
- Flush the output data back to the web page

if you are looking for more example Use this [link](https://www.w3schools.com/html/html_examples.asp)
