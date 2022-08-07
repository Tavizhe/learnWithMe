#Markdown Learning

To make a phrase italic in Markdown, you can surround words with an underscore (_ ). For example, \_this_ word would become italic.

Similarly, to make phrases bold in Markdown, you can surround words with two asterisks ( ** ). This will **really\*\* get your point across.

To make headers in Markdown, you preface the phrase with a hash mark (#).

To create an inline link, you wrap the link text in brackets ( [ ] ), and then you wrap the link in parenthesis ( ( ) ). [Visit GitHub!](www.github.com)

To create an inline image link, enter an exclamation point ( ! ), wrap the alt text in brackets ( [ ] ), and then wrap the link in parenthesis ( ( ) ). (Alt text is a phrase or sentence that describes the image for the visually impaired.)
![Benjamin Bannekat](https://octodex.github.com/images/bannekat.png).

To create a block quote, all you have to do is preface a line with the "greater than" caret (>). For example:

> "In a few moments he was barefoot"

There are two types of lists in the known universe: unordered and ordered. That's a fancy way of saying that there are lists with bullet points, and lists with numbers.
To create an unordered list, you'll want to preface each item in the list with an asterisk ( \* ). Each list item also gets its own line

- Milk

An ordered list is prefaced with numbers

1. Crack three eggs over a bowl
2. Pour a gallon of milk into the bowl

Markdown has several ways of formatting paragraphs. You can accomplish this by inserting two spaces after each new line. Each dot ( · ) represents a space on the keyboard.
Do I contradict myself?··
Very well then I contradict myself

---

# Markdown Cheat Sheet

Thanks for visiting [The Markdown Guide](https://www.markdownguide.org)!

This Markdown cheat sheet provides a quick overview of all the Markdown syntax elements. It can’t cover every edge case, so if you need more information about any of these elements, refer to the reference guides for [basic syntax](https://www.markdownguide.org/basic-syntax) and [extended syntax](https://www.markdownguide.org/extended-syntax).

## Basic Syntax

These are the elements outlined in John Gruber’s original design document. All Markdown applications support these elements.

### Heading

# H1

## H2

### H3

### Bold

**bold text**

### Italic

_italicized text_

### Blockquote

> blockquote

### Ordered List

1. First item
2. Second item
3. Third item

### Unordered List

- First item
- Second item
- Third item

### Code

`code`

### Horizontal Rule

---

### Link

[Markdown Guide](https://www.markdownguide.org)

### Image

![alt text](https://www.markdownguide.org/assets/images/tux.png)

## Extended Syntax

These elements extend the basic syntax by adding additional features. Not all Markdown applications support these elements.

### Table

| Syntax    | Description |
| --------- | ----------- |
| Header    | Title       |
| Paragraph | Text        |

### Fenced Code Block

```
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```

### Footnote

Here's a sentence with a footnote. [^1]

[^1]: This is the footnote.

### Heading ID

### My Great Heading {#custom-id}

### Definition List

term
: definition

### Strikethrough

~~The world is flat.~~

### Task List

- [x] Write the press release
- [ ] Update the website
- [ ] Contact the media

### Emoji

That is so funny! :joy:

(See also [Copying and Pasting Emoji](https://www.markdownguide.org/extended-syntax/#copying-and-pasting-emoji))

### Highlight

I need to highlight these ==very important words==.

### Subscript

H~2~O

### Superscript

X^2^
