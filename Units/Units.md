# UNITS IN CSS

## Absolute Lengths
Absolute length units are fixed and a length expressed in any of these will appear as exactly that size.

## Relative Lengths
Relative length units specify a length relative to another length property. Relative length units scale better between different rendering mediums.

### **Pixels (px)**
- `px` is an absolute unit of measurement in CSS, representing the smallest unit of screen space.
- It provides a fixed and consistent size on all devices and screens.

### **Percentages (%)**
- Percentages are relative units based on the parent element's size or the containing block.
- Widely used in creating responsive layouts.
- 100% = 16px
- **Example:** `width: 50%;` sets an element's width to 50% of its parent's width.

### **Em (em)**
- `em` is a relative unit that is calculated based on the font size of the parent element.
- When you set an element's size in `em`, it's relative to the font size of its nearest parent with a specified font size.

### **Root Em (rem)**
- `rem` is also a relative unit like `em`, but it's based on the font size of the root (`html`) element.
- Using `rem` ensures that the size is consistent throughout the entire document, making it especially useful for responsive design.

---

## IMPORTANT TIPS + NOTES

- **`px`** provides fixed sizes and is not recommended for responsive design as it doesn't adapt to different screen sizes and font settings. However, it can be useful for precise control over small elements.
- **`em`** is useful for relative sizing within the context of the parent element's font size. It allows for more flexible and scalable designs.
- **`rem`** is the preferred choice for responsive design as it offers a consistent relative size based on the root font size. It's easier to maintain and provides better scalability.

---

## Code Examples

### Using Pixels (`px`)
```css
h1 {
  font-size: 54px;
  color: purple;
}

p {
  font-size: 36px;
}

li {
  font-size: 44px;
}
```

### Using Percentages (`%`)
- **100% = 16px**, so **1px = 6.25%**
```css
h1 {
  font-size: 337.5%;
}

p {
  font-size: 225%;
}

li {
  font-size: 275%;
}
```

### Using Em (`em`)
- **1em = 16px (default browser size)**
```css
h1 {
  font-size: 3.374em;
}

p {
  font-size: 2.25em;
}

.parent {
  font-size: 10px; /* Sets the base font size */
}

li {
  font-size: 2.75em;
}
```

### Using Root Em (`rem`)
- Set root size for ease of scaling:
  - **16px = 100%, so 1rem = 10px** with `html { font-size: 62.5%; }`
```css
html {
  font-size: 62.5%;
}

h1 {
  font-size: 5.4rem;
}

p {
  font-size: 3.6rem;
}

li {
  font-size: 4.4rem;
}
```

---

## INTERVIEW QUESTIONS

1. **What is the main difference between `em` and `rem` units in CSS?**
   - `em` units are relative to the font size of their parent element, while `rem` units are relative to the root element's font size.
   - This means that `em` can compound when nested, while `rem` maintains consistency across the document.

2. **How does using `rem` units in your CSS benefit a responsive web design?**
   - `rem` units provide a consistent and predictable scaling mechanism across the document.
   - By setting a root font size (e.g., `html { font-size: 62.5%; }`), you can easily calculate and adjust sizes for different screen sizes or user preferences.

3. **Can you explain how the `font-size` property in `em` units works when nested within parent elements with different font sizes?**
   - The size of an element defined in `em` is calculated based on the font size of its parent.
   - For example, if a parent element has `font-size: 20px;` and a child has `font-size: 1.5em;`, the child's font size will be `1.5 * 20px = 30px`.
   - This compounding effect can lead to unexpected results when multiple levels of nesting occur.
