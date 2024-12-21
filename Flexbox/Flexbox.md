### **Flexbox in CSS**

---

#### **Overview**

Flexbox (Flexible Box Layout) is a one-dimensional layout system used to arrange items in rows or columns. It provides powerful alignment and distribution capabilities, making it easier to create responsive layouts without relying on floats or positioning.

---
### Flex Generator : https://angrytools.com/css-flex/

### Flex Generator : https://loading.io/flexbox/

### Flex Generator : https://www.cssportal.com/css-flexbox-generator/

### **Key Flexbox Concepts**

1. **Flex Container**  
   - The parent element with `display: flex;` applied.  
   - Contains **flex items** (children elements).  

2. **Main Axis & Cross Axis**  
   - **Main Axis**: Defined by the `flex-direction` property.  
   - **Cross Axis**: Perpendicular to the main axis.  

3. **Flex Items**  
   - Child elements within a flex container that can be arranged and aligned.  

---

### **Flex Container Properties (Parent)**

| **Property**           | **Description**                                                                 | **Values**                           | **Example**               |
|-------------------------|---------------------------------------------------------------------------------|--------------------------------------|---------------------------|
| `display`              | Defines a flex container.                                                       | `flex`, `inline-flex`                | `display: flex;`          |
| `flex-direction`       | Specifies the direction of the main axis.                                       | `row`, `row-reverse`, `column`, `column-reverse` | `flex-direction: row;`  |
| `justify-content`      | Aligns flex items along the main axis.                                          | `flex-start`, `flex-end`, `center`, `space-between`, `space-around`, `space-evenly` | `justify-content: center;` |
| `align-items`          | Aligns flex items along the cross axis.                                         | `flex-start`, `flex-end`, `center`, `baseline`, `stretch` | `align-items: stretch;` |
| `flex-wrap`            | Determines whether items should wrap onto a new line.                          | `nowrap`, `wrap`, `wrap-reverse`     | `flex-wrap: wrap;`        |
| `align-content`        | Aligns multiple rows of items along the cross axis when `flex-wrap` is enabled. | `flex-start`, `flex-end`, `center`, `space-between`, `space-around`, `stretch` | `align-content: center;` |

---

### **Flex Item Properties (Children)**

| **Property**    | **Description**                                                            | **Values**                      | **Example**                 |
|------------------|----------------------------------------------------------------------------|---------------------------------|-----------------------------|
| `order`         | Specifies the order of the item relative to other items.                  | Numeric values (default: `0`)   | `order: 1;`                |
| `flex-grow`     | Defines how much the item should grow relative to other items.            | Numeric values (default: `0`)   | `flex-grow: 1;`            |
| `flex-shrink`   | Defines how much the item should shrink relative to other items.          | Numeric values (default: `1`)   | `flex-shrink: 0;`          |
| `flex-basis`    | Specifies the initial size of the item along the main axis.               | Length values or `auto`         | `flex-basis: 200px;`       |
| `flex`          | A shorthand for `flex-grow`, `flex-shrink`, and `flex-basis`.             | `none`, or `grow shrink basis`  | `flex: 1 1 auto;`          |
| `align-self`    | Aligns the individual item differently from others on the cross axis.     | `auto`, `flex-start`, `flex-end`, `center`, `baseline`, `stretch` | `align-self: center;` |

---

### **Examples**

#### 1. **Basic Flex Container**

```css
.flex-container {
  display: flex;           /* Enable Flexbox */
  flex-direction: row;     /* Arrange items in a row (default) */
  justify-content: center; /* Center items along the main axis */
  align-items: center;     /* Center items along the cross axis */
}
```

#### 2. **Responsive Navigation Bar**

```html
<nav class="navbar">
  <a href="#">Home</a>
  <a href="#">About</a>
  <a href="#">Services</a>
  <a href="#">Contact</a>
</nav>
```

```css
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px 20px;
  background-color: #333;
  color: white;
}
.navbar a {
  text-decoration: none;
  color: white;
  padding: 0 10px;
}
```

#### 3. **Center a Div**

```css
.center-container {
  display: flex;
  justify-content: center; /* Center horizontally */
  align-items: center;    /* Center vertically */
  height: 100vh;
}
```

---

### **Common Interview Questions**

1. **How do you center elements using Flexbox?**  
   Use `justify-content: center;` and `align-items: center;` on the flex container.

2. **How can you reorder items without changing HTML structure?**  
   Use the `order` property to rearrange the visual order of items.

3. **What is the difference between `justify-content` and `align-items`?**  
   - `justify-content`: Aligns items along the main axis.  
   - `align-items`: Aligns items along the cross axis.

4. **How do you make a flex item grow proportionally?**  
   Use the `flex-grow` property on the item. For example, `flex-grow: 1;`.

---

### **Pro Tips**

- Use `flex-wrap: wrap;` for responsiveness when items exceed container width.  
- Combine Flexbox with media queries to create adaptive layouts.  
- The `gap` property (recently added) allows spacing between items without using margins. Example: `gap: 20px;`.

---

### **Practical Example**

```html
<div class="flex-container">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</div>
```

```css
.flex-container {
  display: flex;
  justify-content: space-around;
  align-items: center;
  flex-wrap: wrap;
  gap: 20px;
}
.item {
  flex: 1;
  min-width: 150px;
  height: 100px;
  background-color: #008080;
  color: white;
  display: flex;
  justify-content: center;
  align-items: center;
  text-transform: uppercase;
}
``` 
