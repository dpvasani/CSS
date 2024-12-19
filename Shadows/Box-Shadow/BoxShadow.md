# CSS Box Shadow

---

## What is Box Shadow?

The **`box-shadow`** CSS property allows you to add shadow effects to HTML elements. Shadows can be customized with different colors, offsets, blur levels, spread radii, and even multiple layers. 

**Key Characteristics:**
1. Shadows **do not affect the layout** of the element.
2. Multiple shadows can be applied by separating them with commas.
3. Shadows can be **outer** or **inner**.

---

## Syntax
```css
box-shadow: h-offset v-offset blur-radius spread-radius color [inset];
```

### Parameters:
1. **`h-offset`** (required): Horizontal offset. Positive values move the shadow to the right; negative to the left.
2. **`v-offset`** (required): Vertical offset. Positive values move the shadow downward; negative upward.
3. **`blur-radius`** (optional): Controls the blur of the shadow. Higher values create softer shadows.
4. **`spread-radius`** (optional): Expands or contracts the shadow size.
5. **`color`** (optional): Specifies the shadow color (e.g., `#000`, `rgba(0,0,0,0.5)`).
6. **`inset`** (optional): Moves the shadow **inside** the element.

---

## Examples

### 1. Basic Outer Shadow
```css
box-shadow: 10px 10px 20px 0px rgba(0, 0, 0, 0.5);
```

### 2. Inner Shadow
```css
box-shadow: inset 5px 5px 10px rgba(0, 0, 0, 0.5);
```

### 3. No Blur, No Spread
```css
box-shadow: 5px 5px 0px 0px #333;
```

### 4. Multiple Shadows
```css
box-shadow: 10px 10px 20px rgba(0, 0, 0, 0.3), -10px -10px 20px rgba(255, 255, 255, 0.5);
```

---

## Ready-Made Shadows
For prebuilt and customizable shadow examples, visit:  
[GetCSSScan Box Shadow Examples](https://getcssscan.com/css-box-shadow-examples)

---

## Key Notes

### Outer Shadow:
- Default behavior is **outer** shadow.
- Horizontal and vertical offsets are required; the rest are optional.

### Inner Shadow:
- Use the **`inset`** keyword to create inner shadows.
  ```css
  box-shadow: inset 10px 10px 20px rgba(0, 0, 0, 0.3);
  ```

---

## Interview Questions

1. **What is the `box-shadow` property, and how is it used?**
   - The `box-shadow` property adds shadow effects to elements. It can customize offset, blur, spread, and color.

2. **How do you create an inner shadow?**
   - Add the `inset` keyword:
     ```css
     box-shadow: inset 5px 5px 10px rgba(0, 0, 0, 0.5);
     ```

3. **How can you apply multiple shadows to an element?**
   - Separate shadows with commas:
     ```css
     box-shadow: 5px 5px 10px #333, -5px -5px 10px #fff;
     ```

4. **Explain the difference between `blur-radius` and `spread-radius`.**
   - **`blur-radius`** controls the softness of the shadow edges.
   - **`spread-radius`** expands or contracts the size of the shadow.

---

## Practical Example

```html
<div class="shadow"></div>
```

```css
.shadow {
  width: 300px;
  height: 300px;
  padding: 40px;
  background-color: rgb(174, 68, 90);
  border-radius: 50%;
  box-shadow: 0px 0px 60px 60px #ffb000;
}
```

---

## Projects and Challenges

1. **Create a Glow Effect:**
   ```css
   box-shadow: 0px 0px 30px rgba(255, 255, 0, 0.8);
   ```

2. **Add a Neomorphic Shadow:**
   ```css
   box-shadow: 10px 10px 20px #d1d9e6, -10px -10px 20px #ffffff;
   ```

3. **Customizable Button Shadows:**
   ```css
   button {
     padding: 10px 20px;
     background: #4caf50;
     box-shadow: 5px 5px 15px rgba(0, 0, 0, 0.2);
   }
   ```

By mastering **box-shadow**, you can create stunning effects for buttons, cards, modals, and more.
```