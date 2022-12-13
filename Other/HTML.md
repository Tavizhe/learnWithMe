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

### HTML Images

HTML images are defined with the `<img>` tag. The source file (src), alternative text (alt), width, and height are provided as attributes. Example:

`<img src="w3schools.jpg" alt="W3Schools.com" width="104" height="142">`

---

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
