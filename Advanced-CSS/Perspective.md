# Perspective in CSS

## 1. What is the `perspective` Property?

The `perspective` property in CSS is used to create a 3D perspective effect by defining the distance between the viewer (camera) and the 3D-transformed elements. It simulates depth, making elements appear closer or farther away from the viewer.

- **Syntax:** `perspective: value;`
- **Values:** 
  - Length in `px` (e.g., `perspective: 1000px;`).
  - Smaller values create a stronger perspective (more dramatic 3D effect).
  - Larger values make the perspective subtler.

---

## 2. Key Notes on `perspective`

- `perspective` is applied to a parent element to affect its children.
- The value represents the distance between the viewer and the Z=0 plane.
- Works in combination with `transform` properties like `rotateX()`, `rotateY()`, and `translateZ()`.

---

## 3. Example Code with `perspective`

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link
      href="https://fonts.googleapis.com/css2?family=Urbanist:wght@300;400;600;700;800;900&display=swap"
      rel="stylesheet"
    />
    <style>
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
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 30px;
        box-shadow: inset 0 0 0 5px #4861ec;
        perspective: 1000px; /* Adding 3D perspective */
      }

      .box {
        width: 500px;
        height: auto;
        background-color: #4861ec;
        box-shadow: 0 0 0px 15px #353f6d;
        margin: 20px;
        color: #fff;
        font-size: 2rem;
        text-transform: capitalize;
        display: flex;
        justify-content: center;
        align-items: center;
        transition: all 2s linear;
      }

      .box:hover {
        transform: rotateY(180deg); /* 3D rotation effect */
      }
    </style>
  </head>
  <body>
    <div class="container">
      <div class="box">Hover Me</div>
    </div>
  </body>
</html>
```

---

## 4. Key Notes on 3D Transformations

- **`rotateY()`**: Rotates the element around the vertical Y-axis.
- **`rotateX()`**: Rotates the element around the horizontal X-axis.
- **`translateZ()`**: Moves the element along the Z-axis, making it appear closer or farther.
- **`scale()`**: Scales the size of the element.

### Example:

```css
.box:hover {
  transform: rotateY(180deg); /* Flips horizontally */
  /* Other options:
    transform: scale(2);          // Doubles the size.
    transform: translateZ(200px); // Moves 200px closer.
  */
}
```

---

## 5. Sample CSS Code for Interactive 3D Hover Effect

```css
.container {
  perspective: 800px; /* Adds depth to the 3D effect */
}

.box {
  transition: transform 1s ease-in-out;
}

.box:hover {
  transform: rotateX(45deg) rotateY(30deg) translateZ(100px);
}
```

---

## 6. Interview Questions

### 1. What does the `perspective` property do in CSS?
**Answer:** The `perspective` property creates a 3D effect by simulating depth. It defines the distance between the viewer and the 3D-transformed elements.

---

### 2. How does `perspective` affect 3D transformations?
**Answer:** It determines how much depth the 3D effect will have. Smaller values create a stronger perspective, while larger values make the effect subtler.

---

### 3. Can `perspective` be applied directly to an element?
**Answer:** No, `perspective` is applied to the parent element and affects the child elements' 3D transformations.

---

### 4. How can you create a 3D flip animation using CSS?
**Answer:** Use `perspective` on the parent and `rotateY()` or `rotateX()` on the child with a `:hover` pseudo-class.

**Example:**
```css
.container {
  perspective: 1000px;
}

.box:hover {
  transform: rotateY(180deg);
}
```