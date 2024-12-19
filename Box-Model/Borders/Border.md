# Borders in CSS

CSS provides the `border` property to create and style borders around HTML elements. Borders help to visually separate and define the boundaries of elements on a web page. The `border` property combines multiple sub-properties like width, style, and color. Let's explore these in detail.

---

## Shorthand Syntax

The shorthand syntax for defining borders is:

```css
border: [border-width] [border-style] [border-color];
```

- **`border-width`**: Specifies the thickness of the border (e.g., `1px`, `2em`, `5%`).
- **`border-style`**: Defines the style of the border (e.g., `solid`, `dotted`, `dashed`).
- **`border-color`**: Sets the color of the border (e.g., color name, hex code, RGB value).

Example:

```css
border: 2px solid #333;
```

---

## Border Width

The `border-width` property controls the thickness of the border.

- Units: Pixels (`px`), ems (`em`), percentages (`%`), etc.

Example:

```css
border-width: 5px;
```

---

## Border Style

The `border-style` property determines the appearance of the border. Available values include:

- `none`: No border (default).
- `solid`: A single solid line.
- `dotted`: A dotted line.
- `dashed`: A dashed line.
- `double`: Two solid lines.
- `groove`: A carved effect.
- `ridge`: A raised effect.
- `inset`: The border makes the element look embedded.
- `outset`: The border makes the element look like it's coming out.

Example:

```css
border-style: dashed;
```

### Multiple Values

You can apply different styles to each side:

```css
/* top | right and left | bottom */
border-style: solid dashed dotted;
```

---

## Border Color

The `border-color` property specifies the color of the border. It accepts any valid CSS color value:

- Named colors: `red`
- Hex codes: `#ff0000`
- RGB values: `rgb(255, 0, 0)`
- HSL values: `hsl(0, 100%, 50%)`

Example:

```css
border-color: blue;
```

---

## Individual Borders

You can define individual border sides with these properties:

- `border-top`
- `border-right`
- `border-bottom`
- `border-left`

Example:

```css
border-top: 5px solid red;
border-right: 3px dashed blue;
border-bottom: 2px groove green;
border-left: 4px double yellow;
```

---

# Borders in CSS3

## Border Radius

The `border-radius` property allows you to create rounded corners or circular shapes for an element.

### Basic Syntax

```css
border-radius: 10px;
```

### Elliptical Radius

You can define two radii for elliptical shapes:

```css
border-radius: 10px 20%;
```

### Custom Radius for Each Corner

```css
border-radius: 10px 15px 5px 20px; /* top-left | top-right | bottom-right | bottom-left */
```

### Circular Shapes

To create a perfect circle:

```css
border-radius: 50%;
```

---

# Examples

### Simple Border Example

```css
.section-border {
  border: 5px solid #003180;
}
```

### Complex Border Example

```css
.section-border {
  border-top: 10px solid #003180;
  border-right: 5px dotted red;
  border-bottom: 7px ridge green;
  border-left: 4px double blue;
}
```

### Border Radius with Gradient Background

```css
div {
  width: 300px;
  height: 300px;
  border-radius: 50%;
  background-image: linear-gradient(to right, #051937, #004d7a, #008793, #00bf72, #a8eb12);
}
```

---

# Notes & Tips

- Explore advanced border-radius patterns: [Fancy Border Radius](https://9elements.github.io/fancy-border-radius/)  
- Generate custom border-radius styles: [CSS Border Radius Generator](https://10015.io/tools/css-border-radius-generator)

---

# Interview Questions

### 1. How do you set a border around an HTML element in CSS?
Use the shorthand syntax for the `border` property:

```css
border: 2px solid #333;
```

### 2. How can you create rounded corners for an HTML element in CSS?
Use the `border-radius` property:

```css
border-radius: 10px;
```

### 3. How do you create a circular border using border-radius?
Set the `border-radius` to `50%`:

```css
border-radius: 50%;
```
```