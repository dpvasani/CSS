# Font Properties in CSS

CSS allows you to control various aspects of font usage, including the font family, size, weight, style, and variant. Here's how each property works:

## Font Family
- The `font-family` property allows you to specify the font used for the text.
- It can accept a list of fonts in a preferred order, with fallback fonts for situations when the preferred font is unavailable.

```css
font-family: "Fortune", "Urbanist", sans-serif;
```
In this example, the `Fortune` font is the primary choice, followed by `Urbanist` as a fallback, and then a generic `sans-serif` if neither of the specified fonts is available.

## Font Size
- The `font-size` property controls the size of the text.
- Units like `px`, `em`, `%`, and keywords (`small`, `medium`, `large`) can be used to specify the size.

```css
font-size: 20px;
```

## Font Weight
- The `font-weight` property defines the thickness of the text characters, ranging from `100` (thin) to `900` (bold).
- You can use numeric values (100, 200, 300, etc.) or keywords like `normal`, `bold`.

```css
font-weight: 900;
```

## Font Style
- The `font-style` property allows you to apply styles like italic to text.
- Common values include `normal`, `italic`, and `oblique`.

```css
font-style: italic;
```

## Font Variant
- The `font-variant` property is used to control the appearance of text characters, like small-caps or normal text.

```css
font-variant: small-caps;
```

# Adding Custom Fonts in CSS

To use a custom font, the `@font-face` rule is used. This allows you to define and include custom fonts on your webpage. Here's an example of how to add the "Fortune" font family:

```css
@font-face {
  font-family: "Fortune";
  src: url("./Font/Fortune.otf") format("opentype");
}
```
In this case, the font is loaded from the `./font/Fortune.otf` file in your project, with a `format` of `opentype`.

# Example of Applying Fortune Font

You can use the custom "Fortune" font in your CSS like this:

```css
h1 {
  font-family: "Fortune", "Urbanist", sans-serif;
  font-size: 54px;
  font-weight: 900;
  font-style: italic;
  font-variant: small-caps;
}
```

This sets the `h1` text to use the "Fortune" font with a fallback to "Urbanist" and `sans-serif` if "Fortune" is unavailable.

# Fallback Fonts

Fallback fonts ensure that the text remains legible even if the primary font is unavailable. To specify fallback fonts, simply list them in order after the preferred font:

```css
font-family: "Preferred Font", Fallback1, Fallback2, sans-serif;
```

# Notes & Tips

### Common Font Formats:
- **TrueType Font (.ttf):** format('truetype') or format('opentype')
- **WOFF Font (.woff):** format('woff')
- **WOFF2 Font (.woff2):** format('woff2')
- **Embedded OpenType Font (.eot):** format('embedded-opentype')
- **SVG Font (.svg):** format('svg')
```