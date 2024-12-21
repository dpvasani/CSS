# Transform in CSS

## 1. Transform Functions

### `transform: translate()`
Moves an element along the X and Y axes within its containing block.

- **Syntax:** `translate(x, y)`
- Moves the element by `x` units horizontally and `y` units vertically.

**Example:**
```css
.element {
  translate: 50px 20px; /* No need to explicitly write `transform:` */
}
```

---

### `transform: scale()`
Scales an element along the X and Y axes.

- **Syntax:**
  - `scale(x)` - Scales by a factor of `x` for both axes.
  - `scale(x, y)` - Scales by a factor of `x` for the X-axis and `y` for the Y-axis.
  - `scaleX(x)` - Scales only along the X-axis.
  - `scaleY(y)` - Scales only along the Y-axis.

**Example:**
```css
.element {
  scale: 2; /* Doubles the size without needing `transform:` */
}
```

---

### `transform: rotate()`
Rotates an element around its origin.

- **Syntax:** `rotate(angle)`
- Positive values rotate clockwise, and negative values rotate counterclockwise.

**Example:**
```css
.element {
  rotate: 45deg; /* Works without `transform:` */
}
```

---

### `transform: skew()`
Skews an element along the X and/or Y axes.

- **Syntax:**
  - `skew(angleX, angleY)` - Skews along both axes.
  - `skewX(angle)` - Skews along the X-axis.
  - `skewY(angle)` - Skews along the Y-axis.

**Example:**
```css
.element {
  skew: 20deg -10deg; /* Skew without explicitly writing `transform:` */
}
```

---

### `transform-origin`
Specifies the origin point for the transformation.

- **Default:** The center of the element.
- **Syntax:** `transform-origin: x-axis y-axis;`

**Example:**
```css
.element {
  transform-origin: left; /* Origin is the left edge */
}
```

---

### Perspective
Perspective creates a 3D effect by defining the distance between the viewer's eye and the screen.

---

## 2. Sample CSS Code

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Urbanist", sans-serif;
}

body {
  background-color: #2b3033;
}

.container {
  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 30px;
  box-shadow: inset 0 0 0 5px #4861ec;
}

.box {
  width: 250px;
  height: 250px;
  background-color: #4861ec;
  box-shadow: 0 0 0px 15px #353f6d;
  margin: 20px;
  color: #fff;
  font-size: 2rem;
  text-transform: capitalize;
  display: flex;
  justify-content: center;
  align-items: center;
  transition-property: all;
}

.container img {
  width: 30%;
  height: auto;
  transition: all 1s linear;
}

.container img:hover {
  translate: 100px;
  scale: 0.5;
  rotate: 45deg;
}
```

---

## 3. Key Note: No Need to Write `transform` Explicitly

CSS now supports using individual transformation functions directly without explicitly writing `transform:`. This can simplify your code when applying transformations like `translate`, `scale`, or `rotate`.

### Example Comparison:

**With `transform:`**
```css
.element {
  transform: translate(50px, 20px) scale(2) rotate(45deg);
}
```

**Without `transform:`**
```css
.element {
  translate: 50px 20px;
  scale: 2;
  rotate: 45deg;
}
```

Both approaches work the same!

---

## 4. Interview Questions

### 1. How can you use the `translate` transform function to move an element 50 pixels to the right and 20 pixels down?
**Answer:**
```css
.element {
  translate: 50px 20px;
}
```

---

### 2. Explain the `scale` transform function. How would you make an element twice its original size?
**Answer:**
```css
.element {
  scale: 2;
}
```

---

### 3. How do you rotate an element 45 degrees clockwise using the `rotate` transform function?
**Answer:**
```css
.element {
  rotate: 45deg;
}
```

---

### 4. How can you combine multiple transform functions to perform complex transformations on an element?
**Answer:**
```css
.element {
  scale: 1.5;
  rotate: 45deg;
  translate: 20px 30px;
}
```