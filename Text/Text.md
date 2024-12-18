# Text Properties in CSS

CSS provides several properties for controlling the style and appearance of text. Below is an overview of the key text properties you can use.

## Text Alignment
The `text-align` property controls the horizontal alignment of text within an element's box. Common values are:
- `left` - Aligns text to the left.
- `center` - Centers the text.
- `right` - Aligns text to the right.
- `justify` - Justifies the text to both the left and right edges.

```css
text-align: left;
```

## Text Decoration
The `text-decoration` property allows you to add decorations like underlines, overlines, or line-through to text. You can control the line's appearance with the following properties:

- **text-decoration-line**: Specifies which type of line should be used as decoration for text (e.g., underline, overline, line-through, or none).
- **text-decoration-color**: Sets the color of the text decoration lines (e.g., underlines or overlines).
- **text-decoration-style**: Sets the style of the decoration line (e.g., solid, dashed, dotted).
- **text-decoration-thickness**: Specifies the thickness of the decoration line.

Example:

```css
text-decoration-line: underline;
text-decoration-color: red;
text-decoration-thickness: 2px;
text-decoration-style: solid;
```

## Text Transform
The `text-transform` property allows you to control the capitalization of text. The values are:
- `uppercase` - Converts text to all uppercase.
- `lowercase` - Converts text to all lowercase.
- `capitalize` - Capitalizes the first letter of each word.

```css
text-transform: capitalize;
```

# Text Spacing in CSS

CSS allows you to control the spacing between letters, words, and lines of text. The following properties help you manage text spacing:

## Letter Spacing
The `letter-spacing` property controls the spacing between characters in a text. Positive values increase the spacing, while negative values decrease it.

```css
letter-spacing: 1.2px;
```

## Word Spacing
The `word-spacing` property controls the spacing between words in a text. Like letter spacing, it can be increased or decreased.

```css
word-spacing: 1px;
```

## Line Height
The `line-height` property specifies the space between lines of text. It can be set to a specific unit (like `px`) or a relative value (such as `1.5`).

```css
line-height: 1.56;
```

## White Space
The `white-space` property controls how white space within an element is handled. It can be used to prevent text from wrapping or to preserve multiple spaces.

```css
white-space: nowrap;
```

# Text Properties of CSS3

## Text Shadow
The `text-shadow` property allows you to add a shadow effect to text characters. It takes three values: horizontal shadow offset, vertical shadow offset, and the shadow color.

```css
text-shadow: -2px -2px 5px rgba(255, 0, 0, 0.2);
```

# Example CSS Usage

Here is an example of how you might use various text properties in a CSS file:

```css
body {
  background-color: hsl(0, 0%, 94%);
  display: grid;
  place-items: center;
  font-family: "Urbanist", sans-serif;
}

.hero-section {
  width: 50%;
}

h1 {
  font-size: 54px;
  font-weight: 900;
  text-align: left;
  text-decoration-line: underline;
  text-decoration-color: red;
  text-decoration-thickness: 10px;
  text-decoration-style: solid;
  text-transform: capitalize;
  text-shadow: -2px -2px 5px rgba(255, 0, 0, 0.2);
}

p,
a {
  font-size: 20px;
  font-weight: 400;
  letter-spacing: 1.2px;
  word-spacing: 1px;
  line-height: 1.56;
}

a {
  text-decoration: none;
  color: red;
}

p::first-letter {
  text-transform: uppercase;
  font-size: 48px;
  font-weight: 600;
}
```

# Interview Questions

### 1. How can you control the spacing between lines of text in CSS?
- The `line-height` property is used to control the spacing between lines of text. You can set it to a specific unit like `px` or a relative value like `1.5`.

### 2. How can you create drop caps (initial letter styling) in CSS?
- You can create drop caps using the `::first-letter` pseudo-element in CSS. Here's an example:

```css
p::first-letter {
  text-transform: uppercase;
  font-size: 48px;
  font-weight: 600;
}
```
