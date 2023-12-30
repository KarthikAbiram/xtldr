---
hide:
  - navigation
---

# Markdown

## Headings
Use `#` for headings. Use a space between the # and the heading text.
```
# Heading 1
## Heading 1.1
### Heading 1.1.1
```

## Paragraph
Use an empty line to separate paragraphs.

## Links
Have the text within square braces [ ], followed by the URL in round braces ( ).
```
I love [xTLDR](https://xtldr.com) for its brevity.
```
I love [xTLDR](https://xtldr.com) for its brevity.

## Images
Images are similar to links. Have an exclamatory mark, followed by alternate text for the image within square braces [ ], followed by absolute or relative URL of the image in round braces.
```
Logo of Wikipedia is ![Wikipedia Logo](https://en.wikipedia.org/static/images/icons/wikipedia.png)
```

## Lists
### Ordered lists
Use numbering for ordered lists.
```
1. Item 1
  1.1 Sub Item
2. Item 2
3. Item 3
```

### Unordered Lists
Use `-` or `+` or `*` for unordered lists.
```
- Item 1
  - Sub Item
- Item 2
- Item 3
```

## Code
To represent code or text that you don't want markdown syntax to decipher:

Enclose them with a single backtick (`) for single line content, which would show up as:
  
`Single line code enclosed within single backtick`

Enclose them with triple backticks (```) for multi line content

```
def function():
    print("Hello World!")
```

## Tables
Syntax for table is
```
| Column 1   | Column 2 | Column 3 |
| ---------- | -------- | -------- |
| Row 1 Text | Text     | Random   |
| Row 2 Text | Text     | Random   |
```