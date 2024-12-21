### Combined and Enhanced Explanation: **CSS New Features**

---

#### **1. Border-Related Logical Properties**

##### **`border-inline` Property**
The `border-inline` CSS property is a shorthand for setting the inline-start and inline-end border properties in logical block directions.  

**Usage:**  
```css
border-inline: 1px solid red;
```

**Expands to:**  
- `border-inline-color`
- `border-inline-style`
- `border-inline-width`

##### **`border-block` Property**
The `border-block` CSS property is a shorthand for setting the block-start and block-end border properties in logical block directions.  

**Usage:**  
```css
border-block: 1px solid red;
```

**Expands to:**  
- `border-block-color`
- `border-block-style`
- `border-block-width`

---

#### **2. CSS Nesting**
CSS Nesting allows defining child rules within parent rules, improving readability and structure.  

**Example:**  
```css
.hero-content {
  color: white;
  
  & h1 {
    font-size: 2rem;
  }

  & p {
    font-size: 1rem;
    color: lightgray;
  }
}
```

**Result:**  
The nested selectors apply styles relative to the parent `.hero-content`.

---

#### **3. `writing-mode` Property**
The `writing-mode` property specifies whether lines of text are laid out horizontally or vertically.  

**Possible Values:**  
- `horizontal-tb` (default): Horizontal text layout.  
- `vertical-rl`: Vertical text layout with lines flowing from right to left.  
- `vertical-lr`: Vertical text layout with lines flowing from left to right.  

**Example:**  
```css
h1 {
  writing-mode: vertical-lr;
}
```

---

#### **Full CSS Code**

```css
/** ------------------------------------- */
/** CSS NEW FEATURES
/** ---------------------------------------- */

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Jost", sans-serif;
}

body {
  background-color: #080a0c;
  color: azure;
  height: 100vh;
}

.container {
  height: 100vh;
  max-width: 1320px;
  padding: 64px 0;
  margin: 0 auto;
  display: grid;
  align-items: center;
}

.grid {
  display: grid;
  align-items: center;
  gap: 6.4rem;
}

.grid-two-column {
  grid-template-columns: repeat(2, 1fr);
}

img {
  width: 100%;
  height: auto;
}

.hero-content {
  /* Nesting starts */
  & h1 {
    text-align: left;
    font-size: 54px;
    writing-mode: vertical-lr;
    position: absolute;
    left: 0;
  }

  & p {
    font-size: 18px;
    letter-spacing: 1px;
    margin: 2rem 0 4rem 0;
  }
  /* Nesting ends */
}

.hero-content a {
  background-color: #fff;
  display: inline-block;
  padding: 10px 32px;
  text-transform: capitalize;
  text-decoration: none;
  border-radius: 5px;
  font-size: 24px;
  font-weight: bold;
}

h1 {
  /* Example using new border shorthand properties */
  border-block: 5px solid red;
}
```

---

### **Key Features Demonstrated**
1. **Logical Properties:** `border-inline` and `border-block` usage.  
2. **CSS Nesting:** Organized styles within `.hero-content`.  
3. **Vertical Writing Mode:** Use of `writing-mode` for rotated text layout.  
4. **Modern Practices:** Shorthand properties for concise, maintainable code.  
