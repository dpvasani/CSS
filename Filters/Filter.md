# CSS Filters

---

## What Are CSS Filters?

CSS filters are a set of graphical effects that can be applied to HTML elements to modify their appearance. These effects include changes to color, brightness, contrast, blur, and more.  

Filters are useful for creating visual enhancements, highlighting elements, or achieving specific artistic effects without modifying the original content.

---

## Syntax

```css
filter: <filter-function> [<filter-function> ...];
```

Filters can be combined by separating them with spaces.

### Example:
```css
filter: blur(5px) grayscale(0.5) contrast(1.2);
```

---

## Commonly Used Filter Functions

| **Function**   | **Description**                                                                 | **Example**                 |
|-----------------|---------------------------------------------------------------------------------|-----------------------------|
| **`grayscale()`** | Converts an element to grayscale. Value `0` is original, `1` is fully grayscale. | `filter: grayscale(0.5);`  |
| **`blur()`**     | Applies a blur effect. The value determines the amount in pixels.              | `filter: blur(5px);`       |
| **`brightness()`** | Adjusts brightness. Values > `1` increase brightness; < `1` decrease.         | `filter: brightness(1.5);` |
| **`contrast()`** | Adjusts contrast. Similar behavior to `brightness()`.                         | `filter: contrast(0.8);`   |
| **`saturate()`** | Increases or decreases saturation. Values > `1` oversaturate; < `1` desaturate.| `filter: saturate(2);`     |
| **`hue-rotate()`** | Rotates hues by the specified degrees.                                       | `filter: hue-rotate(90deg);` |
| **`invert()`**   | Inverts the colors of the element. Value `1` is fully inverted.               | `filter: invert(0.7);`     |
| **`opacity()`**  | Adjusts transparency. Value `0` is fully transparent, `1` is fully opaque.    | `filter: opacity(0.5);`    |
| **`sepia()`**    | Applies a sepia tone effect. Value `1` is fully sepia.                        | `filter: sepia(0.7);`      |

---

## Combining Filters

Filters can be combined by listing them in the `filter` property, separated by spaces.

### Example:
```css
filter: blur(5px) grayscale(0.5) contrast(1.2);
```

---

## Application Examples

### 1. Grayscale with Blur
```css
filter: grayscale(0.8) blur(3px);
```

### 2. Hue Rotation
```css
filter: hue-rotate(120deg);
```

### 3. Brightness and Contrast
```css
filter: brightness(1.5) contrast(1.2);
```

---

## Advanced Usage

### Filters on Images
```html
<img src="example.jpg" style="filter: sepia(0.6) brightness(1.2) contrast(0.8);">
```

### Filters on Backgrounds
```css
section {
  background: url('example.jpg');
  filter: blur(10px);
}
```

---

## Interview Questions

1. **What are CSS filters, and why are they used?**  
   CSS filters are visual effects applied to HTML elements to modify their appearance. They are used to create effects like blurring, adjusting brightness, contrast, and more.

2. **How do you create a blur effect using CSS filters?**  
   Use the `blur()` function and specify the amount in pixels. Example:  
   ```css
   filter: blur(5px);
   ```

3. **How can you combine multiple filters?**  
   Filters can be combined by listing them in the `filter` property, separated by spaces. Example:  
   ```css
   filter: blur(3px) grayscale(0.5) contrast(1.2);
   ```

---

## Best Practices

1. **Combine filters thoughtfully**: Avoid excessive use to maintain readability and performance.  
2. **Experiment**: Use combinations for creative effects like vintage or futuristic styles.  
3. **Test performance**: Filters can impact rendering speed, especially with animations.

---

## Explore More

For interactive filter design, try [CSS Filter Generator](https://cssfilters.co/).  

---