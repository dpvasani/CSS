### **Pseudo-Classes in CSS**

---

#### **What Are Pseudo-Classes?**  
Pseudo-classes in CSS define the special states or conditions of elements. They allow you to apply styles based on user interaction, document structure, or element status, without modifying the HTML.

---

### **List of Common Pseudo-Classes**

| **Pseudo-Class**        | **Description**                                                                                         | **Example**                                                                 |
|--------------------------|---------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------|
| `:link`                 | Styles an unvisited link.                                                                               | `a:link { color: blue; }`                                                  |
| `:visited`              | Styles a visited link.                                                                                 | `a:visited { color: purple; }`                                             |
| `:hover`                | Styles an element when the user hovers over it with a mouse.                                           | `a:hover { color: red; }`                                                  |
| `:active`               | Styles an element while it is being clicked.                                                           | `a:active { color: green; }`                                               |
| `:first-child`          | Selects the first child of a parent.                                                                   | `p:first-child { color: red; }`                                            |
| `:last-child`           | Selects the last child of a parent.                                                                    | `p:last-child { color: blue; }`                                            |
| `:nth-child(n)`         | Selects elements based on their position within their parent (1-based index).                          | `li:nth-child(2) { color: green; }`                                        |
| `:nth-child(odd/even)`  | Selects odd/even indexed elements within their parent.                                                 | `li:nth-child(odd) { color: red; }`                                        |
| `:first-of-type`        | Selects the first instance of an element type within its parent.                                       | `p:first-of-type { color: orange; }`                                       |
| `:last-of-type`         | Selects the last instance of an element type within its parent.                                        | `p:last-of-type { color: purple; }`                                        |
| `:nth-of-type(n)`       | Selects elements of a specific type based on their position within their parent.                       | `p:nth-of-type(2) { color: pink; }`                                        |
| `:focus`                | Styles an element when it gains focus (e.g., an input field).                                          | `input:focus { border: 2px solid red; }`                                   |
| `:checked`              | Styles a checkbox or radio button when it is checked.                                                 | `input:checked { background-color: yellow; }`                              |
| `:disabled`             | Styles an element that is disabled.                                                                   | `button:disabled { opacity: 0.5; }`                                        |
| `:enabled`              | Styles an element that is enabled.                                                                    | `button:enabled { background-color: green; }`                              |
| `:not(selector)`        | Selects elements that do not match a given selector.                                                  | `div:not(.active) { display: none; }`                                      |
| `:empty`                | Selects elements with no children (including text nodes).                                             | `div:empty { display: none; }`                                             |
| `:root`                 | Selects the root element of the document (typically the `<html>` element).                            | `:root { font-size: 16px; }`                                               |
| `:target`               | Styles an element when its ID matches the fragment identifier in the URL.                             | `#section:target { background-color: lightblue; }`                         |
| `:checked`              | Targets inputs like checkboxes or radio buttons that are checked.                                     | `input:checked { border: 2px solid green; }`                               |
| `:before` and `:after`  | While technically pseudo-elements, they are often used alongside pseudo-classes to style elements.    | `h1::before { content: '*'; color: red; }`                                 |

---

#### **Example Usage**

1. **Hover State**: Change the text color of a link when hovered.  
   ```css
   a:hover {
     color: #0062ff;
   }
   ```

2. **Nth Child**: Style every odd list item.  
   ```css
   li:nth-child(odd) {
     color: red;
   }
   ```

3. **Last Child**: Style the last paragraph in a container.  
   ```css
   p:last-child {
     color: blue;
   }
   ```

4. **Disabled State**: Make disabled buttons appear faded.  
   ```css
   button:disabled {
     opacity: 0.5;
   }
   ```

5. **Focus State**: Highlight an input field when it gains focus.  
   ```css
   input:focus {
     outline: 2px solid blue;
   }
   ```

---

#### **Important Notes**

1. **`:first-child` vs. `:first-of-type`**:  
   - `:first-child` applies to any element that is the first child of its parent, regardless of its type.  
   - `:first-of-type` applies to the first instance of a specific type within a parent.

2. **Pseudo-Class vs. Pseudo-Element**:  
   - Pseudo-classes (`:hover`, `:nth-child`, etc.) target states of elements.  
   - Pseudo-elements (`::before`, `::after`) target specific parts of elements.

3. **Accessibility**: Be cautious when using pseudo-classes to indicate state changes, as they may not be visible to screen readers.

---

#### **Interview Questions**

1. **What is the difference between `:hover` and `:active`?**  
   - `:hover` is triggered when the user hovers the mouse over an element.  
   - `:active` is triggered when the user clicks and holds the mouse button on an element.

2. **Can you style every third child of a parent element?**  
   Yes, by using the `:nth-child(3n)` pseudo-class.

3. **What does `:not(selector)` do?**  
   It selects elements that do not match the specified selector.

---
