### **Latest CSS Pseudo-Classes**

---


#### **Pseudo-Classes Introduction**
CSS pseudo-classes enable styling elements based on their state or position without adding extra classes or attributes in the HTML. They allow for powerful, flexible styling with minimal markup.

---

#### **1. `:is()` Pseudo-Class**
The `:is()` pseudo-class allows matching any of the provided selectors and takes the specificity of its most specific argument.  

**Use Case:**  
It simplifies complex selectors by grouping them together, allowing for concise and efficient CSS rules.  

```css
:is(.section-about, .section-testimonial) .grid :is(h1, p) {
  color: yellow;
}
```

**Explanation:**  
The styles will apply to `h1` and `p` elements within `.grid` in both `.section-about` and `.section-testimonial`.

---

#### **2. `:where()` Pseudo-Class**
The `:where()` pseudo-class functions similarly to `:is()`, but it always has zero specificity.  

**Use Case:**  
Used for grouping selectors without contributing to specificity, making it ideal for non-intrusive overrides.  

```css
:where(.section-about, .section-testimonial) .grid :where(h1, p) {
  color: yellow;
}
```

**Difference Between `:is()` and `:where()`:**
- `:is()` inherits the specificity of the most specific argument.  
- `:where()` does not contribute to specificity, providing a safer way to override styles.

---

#### **3. `:has()` Pseudo-Class**
The `:has()` pseudo-class selects elements based on their children or descendants that match a provided selector.  

**Use Case:**  
Style a parent element if it contains a specific child, enhancing conditional styling.  

```css
.parent:has([type="checkbox"]:checked) label {
  color: red;
}
```

**Explanation:**  
If a `checkbox` inside `.parent` is checked, the `label` within `.parent` will turn red.

---

#### **4. `:not()` Pseudo-Class**
The `:not()` pseudo-class excludes specific elements from selection.  

**Use Case:**  
Avoid applying styles to certain elements within a group by negating them in the selector.  

```css
nav ul :not(li:first-child) {
  padding-left: 50px;
}
```

**Explanation:**  
This will add `padding-left` to all `li` elements except the first one in the `ul`.

---

#### **5. `accent-color` Property**
The `accent-color` CSS property allows customization of the color of form controls like checkboxes, radio buttons, and other input elements.  

**Use Case:**  
Enhances the appearance of form controls across browsers by customizing their accent colors.  

```css
input[type="checkbox"] {
  accent-color: pink;
  width: 50px;
  aspect-ratio: 1;
}
```

**Explanation:**  
The checkbox will be styled with a `pink` accent color, providing a more consistent and visually appealing appearance across platforms.

---

#### **Code Example**

```css
/** General Reset **/
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Urbanist", sans-serif;
}

/** Container Styles **/
.container {
  width: 1280px;
  margin: 0 auto;
}

/** Section Styles **/
.section-about,
.section-testimonial {
  background-color: #000;
}

:is(.section-about, .section-testimonial) .grid :is(h1, p) {
  color: yellow;
}

/** Parent-Child Relationship **/
.parent:has([type="checkbox"]:checked) label {
  color: red;
}

input[type="checkbox"] {
  accent-color: pink;
  width: 50px;
  aspect-ratio: 1;
}

/** Grid Layout **/
.grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  align-items: center;
}

img {
  width: 100%;
  height: auto;
}

p,
label {
  font-size: 20px;
}

/** Navbar **/
header {
  padding: 3.6rem 0;
}

nav ul {
  display: flex;
}

nav ul li {
  font-size: 2rem;
  list-style: none;
  border: 1px solid red;
}

nav ul :not(li:first-child) {
  padding-left: 50px;
}
```

---

### **Summary Table: Latest Pseudo-Classes and Features**

| **Pseudo-Class**  | **Purpose**                                      | **Specificity**                     |
|-------------------|--------------------------------------------------|-------------------------------------|
| `:is()`           | Matches any of the provided selectors.           | Inherits the most specific selector |
| `:where()`        | Matches any of the provided selectors.           | Always 0 specificity                |
| `:has()`          | Matches elements containing specific children.   | Depends on the outer selector       |
| `:not()`          | Excludes specific elements from being styled.    | Inherits the specificity of its argument |
| `accent-color`    | Customizes the color of form controls.           | N/A                                 |

