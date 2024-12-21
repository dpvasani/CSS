# CSS Selectors and Specificity  

## 1. What is CSS Specificity?  
CSS specificity is a system that browsers use to determine which styles should be applied when multiple CSS rules target the same element. It assigns weights to different types of selectors to resolve conflicts.  

---

## 2. Types of Selectors and Their Specificity  

### **Universal Selector**  
- **Selector:** `*`  
- **Specificity:** `0-0-0-0-0` (No priority)  
- **Example:**  
  ```css  
  * {  
    margin: 0;  
  }  
  ```  

---

### **Element and Pseudo-elements**  
- **Selector:** `h1`, `p`, `img`, `::before`  
- **Specificity:** `0-0-0-0-1`  
- **Example:**  
  ```css  
  h1::before {  
    content: "Title: ";  
  }  
  ```  

---

### **Class, Pseudo-classes, and Attributes**  
- **Selector:** `.myClass`, `:hover`, `[type="radio"]`  
- **Specificity:** `0-0-0-1-0`  
- **Example:**  
  ```css  
  .highlight {  
    background-color: yellow;  
  }  

  input[type="radio"]:hover {  
    cursor: pointer;  
  }  
  ```  

---

### **ID Selector**  
- **Selector:** `#btn`, `#navbar`  
- **Specificity:** `0-0-1-0-0`  
- **Example:**  
  ```css  
  #main-heading {  
    color: red;  
  }  
  ```  

---

### **Inline Styles**  
- **Selector:** Inline `style` attribute in HTML elements.  
- **Specificity:** `0-1-0-0-0`  
- **Example:**  
  ```html  
  <div style="background: #000;">Content</div>  
  ```  

---

### **!important** Declaration  
- **Specificity:** `1-0-0-0-0` (Highest priority)  
- **Example:**  
  ```css  
  p {  
    color: blue !important;  
  }  
  ```  

---

## 3. Specificity Weight System  

CSS specificity values are represented in the format `a-b-c-d-e`, where:  
- **a**: `!important` declarations  
- **b**: Inline styles  
- **c**: IDs  
- **d**: Classes, attributes, and pseudo-classes  
- **e**: Elements and pseudo-elements  

### Specificity Levels:  

| **Selector**           | **Specificity Weight** | **Example**               |  
|-------------------------|------------------------|---------------------------|  
| Universal Selector      | `0-0-0-0-0`           | `* {}`                    |  
| Element/Pseudo-element  | `0-0-0-0-1`           | `h1`, `::before`          |  
| Class/Pseudo-class      | `0-0-0-1-0`           | `.btn`, `:hover`          |  
| ID                      | `0-0-1-0-0`           | `#navbar`                 |  
| Inline Styles           | `0-1-0-0-0`           | `<div style="...">`       |  
| `!important`            | `1-0-0-0-0`           | `color: blue !important;` |  

---

## 4. Practical Examples  

### Example 1: Specificity Conflict  

```html  
<!DOCTYPE html>  
<html lang="en">  
  <head>  
    <meta charset="UTF-8" />  
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />  
    <style>  
      * {  
        color: gray; /* Specificity: 0-0-0-0-0 */  
      }  

      p {  
        color: blue; /* Specificity: 0-0-0-0-1 */  
      }  

      .highlight {  
        color: green; /* Specificity: 0-0-0-1-0 */  
      }  

      #main {  
        color: red; /* Specificity: 0-0-1-0-0 */  
      }  

      p {  
        color: orange !important; /* Specificity: 1-0-0-0-0 */  
      }  
    </style>  
  </head>  
  <body>  
    <p id="main" class="highlight">CSS Specificity</p>  
  </body>  
</html>  
```  

### Result:  
The `<p>` element text will be **orange** because of the `!important` rule, despite the ID selector and class rules.  

---

### Example 2: Combining Specificity  

```css  
/* Combined specificity: 0-0-1-1-1 */  
div#container .content p::before {  
  content: "CSS Rocks!";  
}  
```  

---

## 5. Tips for Managing Specificity  

1. **Use Specificity Sparingly:** Avoid writing overly complex selectors.  
2. **Minimize `!important`:** It should only be used for special cases.  
3. **Organize CSS:** Write rules in a modular and hierarchical manner.  
4. **Inspect Styles:** Use browser developer tools to debug specificity conflicts.  

---

## 6. Common Interview Questions  

### 1. What is CSS specificity?  
CSS specificity determines which CSS rule is applied when multiple rules target the same element.  

### 2. How does the `!important` declaration affect specificity?  
`!important` overrides all other rules except another `!important` rule, regardless of specificity weight.  

### 3. How are specificity values calculated?  
Specificity values are assigned based on the number of selectors:  
- Inline styles: `0-1-0-0-0`  
- ID selectors: `0-0-1-0-0`  
- Classes, attributes, and pseudo-classes: `0-0-0-1-0`  
- Elements and pseudo-elements: `0-0-0-0-1`  

### 4. How can you debug specificity issues in CSS?  
Inspect the element using browser developer tools and review the applied styles and their specificity weights.  

### 5. What happens if two selectors have the same specificity?  
If two rules have the same specificity, the one defined later in the CSS file takes precedence.