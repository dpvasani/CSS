### **1. Container Queries**

**What is it?**
Container queries allow you to apply styles based on the size of the container element rather than the viewport. This enables more responsive layouts that adapt to their parent container instead of just the browser window.

**Use Case:**  
Used for building layouts that adjust to different container sizes, making it easier to create modular and reusable components.

**Example:**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Container Queries</title>
    <style>
      .container {
        container-type: inline-size;
        container-name: my-container;
        width: 100%;
        max-width: 600px;
        border: 2px solid #333;
      }

      @container my-container (min-width: 400px) {
        .child {
          background-color: lightblue;
        }
      }
      @container my-container (min-width: 600px) {
        .child {
          background-color: lightgreen;
        }
      }

      .child {
        height: 200px;
      }
    </style>
  </head>
  <body>
    <div class="container">
      <div class="child"></div>
    </div>
  </body>
</html>
```

**Explanation:**  
- The `.child` element's background color changes based on the container's width.
- The first rule applies when the container width is at least 400px, and the second applies when it's at least 600px.

---

### **2. The `:is()`, `:has()`, `:not()`, `:where()` Pseudo-Classes**

**What is it?**
These pseudo-classes are used for selecting elements based on specific conditions:
- `:is()` allows matching any of the provided selectors.
- `:has()` selects elements that contain specific children.
- `:not()` excludes elements that match a selector.
- `:where()` is similar to `:is()` but with no specificity.

**Use Case:**  
Use these to simplify complex selectors, conditionally style elements based on their children, or exclude specific elements.

**Example:**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>:is(), :has(), :not(), :where()</title>
    <style>
      .parent:is(.highlight, .selected) p {
        color: red;
      }

      .parent:has(button:checked) {
        background-color: yellow;
      }

      .nav ul :not(li:first-child) {
        padding-left: 20px;
      }

      .container:where(.box, .grid) {
        border: 2px solid blue;
      }
    </style>
  </head>
  <body>
    <div class="parent">
      <p>Red text if .highlight or .selected class is present</p>
      <button>Click me</button>
    </div>
    <div class="nav">
      <ul>
        <li>Home</li>
        <li>About</li>
        <li>Contact</li>
      </ul>
    </div>
  </body>
</html>
```

---

### **3. Accent-Color**

**What is it?**
The `accent-color` property is used to define a custom color for certain form controls like checkboxes, radio buttons, and progress bars.

**Use Case:**  
This allows for custom theming of form controls without extra markup or JavaScript.

**Example:**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Accent Color</title>
    <style>
      input[type="checkbox"] {
        accent-color: #ff6347; /* Tomato color */
      }
    </style>
  </head>
  <body>
    <input type="checkbox" />
  </body>
</html>
```

---

### **4. Media Query Range Syntax**

**What is it?**
Range syntax for media queries allows specifying ranges for features like width, height, etc., within the same media query using `--min-` and `--max-` for a more fluid approach.

**Use Case:**  
Perfect for creating responsive layouts with more concise media query ranges.

**Example:**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Range Syntax</title>
    <style>
      @media (width: 500px..1000px) {
        body {
          background-color: lightblue;
        }
      }
    </style>
  </head>
  <body>
    <h1>Responsive Design</h1>
  </body>
</html>
```

---

### **5. Aspect Ratio**

**What is it?**
The `aspect-ratio` property allows you to set a specific aspect ratio (width to height ratio) for elements.

**Use Case:**  
Ideal for maintaining consistent ratios for images or videos without distortion.

**Example:**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Aspect Ratio</title>
    <style>
      img {
        aspect-ratio: 16 / 9;
        width: 100%;
        height: auto;
      }
    </style>
  </head>
  <body>
    <img src="path/to/image.jpg" alt="Image with fixed aspect ratio" />
  </body>
</html>
```

---

### **6. Scroll Snap**

**What is it?**
`scroll-snap` allows you to create a snapping effect where scroll position aligns with specific elements.

**Use Case:**  
Ideal for creating smooth, scrollable elements like carousels, image galleries, etc.

**Example:**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Scroll Snap</title>
    <style>
      .scroll-container {
        display: flex;
        overflow-x: auto;
        scroll-snap-type: x mandatory;
      }

      .scroll-container div {
        width: 300px;
        height: 200px;
        scroll-snap-align: center;
        margin-right: 10px;
        background-color: #ccc;
      }
    </style>
  </head>
  <body>
    <div class="scroll-container">
      <div>1</div>
      <div>2</div>
      <div>3</div>
      <div>4</div>
    </div>
  </body>
</html>
```

---

### **7. Gap Property for Flexbox**

**What is it?**
The `gap` property allows you to set the spacing between flex items or grid items. It works similarly to the `grid-gap` property.

**Use Case:**  
Great for adding consistent spacing in flex layouts without using margins.

**Example:**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Flex Gap</title>
    <style>
      .flex-container {
        display: flex;
        gap: 20px;
      }

      .flex-container div {
        width: 100px;
        height: 100px;
        background-color: #4caf50;
      }
    </style>
  </head>
  <body>
    <div class="flex-container">
      <div></div>
      <div></div>
      <div></div>
    </div>
  </body>
</html>
```

---

### **8. Individual Transform Properties**

**What is it?**
You can now apply individual transformations like `rotate`, `scale`, `skew`, and `translate` with the `transform` property in CSS.

**Use Case:**  
Useful for applying specific transformations without having to define all transforms at once.

**Example:**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Individual Transform</title>
    <style>
      .rotate {
        transform: rotate(45deg);
      }

      .scale {
        transform: scale(1.5);
      }
    </style>
  </head>
  <body>
    <div class="rotate">Rotated</div>
    <div class="scale">Scaled</div>
  </body>
</html>
```

---

### **9. CSS Logical Properties (inline and block)**

**What is it?**
Logical properties enable better control of layout directionality, using logical values like `inline-size`, `block-size`, `margin-block`, etc.

**Use Case:**  
Ideal for building layouts that adapt to both left-to-right and right-to-left languages.

**Example:**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Logical Properties</title>
    <style>
      div {
        margin-inline: 10px;
        padding-block: 20px;
      }
    </style>
  </head>
  <body>
    <div>Content</div>
  </body>
</html>
```

---

### **10. CSS Nesting**

**What is it?**
CSS nesting allows you to nest CSS selectors in a way that mirrors the HTML structure, making it easier to write and maintain styles.

**Use Case:**  
Ideal for writing cleaner, more organized CSS, especially in large projects.

**Example:**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>CSS Nesting</title>
    <style>
      .parent {
        color: red;
        .child {
          color: blue;
        }
      }
    </style>
  </head>
  <body>
    <div class="parent">
      <div class="child">Nested element</div>
    </div>
  </body>
</html>
```

---
