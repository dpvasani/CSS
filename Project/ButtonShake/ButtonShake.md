### **1. Font and Reset Styles**
```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Urbanist";
}
```
- This rule is applied to all elements (`*`), which:
  - Removes default margin and padding.
  - Ensures consistent box-sizing across elements.
  - Sets the font to **Urbanist**, a clean and modern sans-serif font for the button text.

### **2. Body Styling**
```css
body {
  height: 100vh;
  display: grid;
  place-items: center;
  background-color: #191825;
}
```
- **`height: 100vh`**: Ensures the body takes up the full viewport height.
- **`display: grid; place-items: center;`**: Uses **CSS Grid** to center the button both vertically and horizontally in the middle of the screen.
- The background color is set to a **dark shade** (`#191825`), providing good contrast for the button.

### **3. Button Styling**
```css
button {
  padding: 12px 36px;
  border: 2px solid #865dff;
  text-align: center;
  color: #865dff;
  font-weight: bold;
  font-size: 20px;
  text-transform: capitalize;
  background-color: transparent;

  &:hover {
    border: 2px solid #d80032;
    color: #d80032;
    animation: shaking 0.2s linear;
  }
}
```
- **Padding**: The button has padding (`12px 36px`) around the text to make it more clickable and well-spaced.
- **Border**: The button has a `2px solid` border with a purple color (`#865dff`), which matches the text color.
- **Text Styling**:
  - `text-align: center` centers the text inside the button.
  - `color: #865dff`: The text is colored in purple.
  - `font-weight: bold`: Makes the text bold for emphasis.
  - `font-size: 20px`: The font size is set to 20px, making it large enough to read clearly.
  - `text-transform: capitalize`: Ensures that the first letter of each word is capitalized.
- **Background**: The background is transparent, allowing the border and text to be the primary focus.
  
#### **Hover Effect**
- **`&:hover`**: The hover effect is applied when the button is hovered over by the mouse:
  - **`border: 2px solid #d80032;`**: Changes the border color to red (`#d80032`) when hovered.
  - **`color: #d80032;`**: Changes the text color to red as well.
  - **`animation: shaking 0.2s linear;`**: When hovered, the `shaking` animation is triggered, making the button appear to shake for **0.2 seconds** in a smooth, linear motion.

### **4. Shaking Animation (`@keyframes shaking`)**
```css
@keyframes shaking {
  0% {
    transform: rotate(20deg);
  }
  50% {
    transform: rotate(-20deg);
  }
  100% {
    transform: rotate(20deg);
  }
}
```
- This animation simulates a **shaking effect**:
  - **`0%` (start)**: The button is rotated by `20deg` (tilted to the right).
  - **`50%` (middle)**: The button rotates in the opposite direction (`-20deg`), tilting to the left.
  - **`100%` (end)**: The button rotates back to the original `20deg` position.
- The `rotate` transform property makes the button shake horizontally by rotating it in a back-and-forth motion.
- **Duration**: The `shaking` animation lasts `0.2s` and plays linearly, meaning the shaking is smooth and continuous during the animation.

### **How It All Comes Together:**
- When you hover over the button, the **shaking animation** kicks in, making the button visually move back and forth with a tilt.
- The color and border change to **red** on hover, providing visual feedback to the user that the button is interactive.

### **Summary**
- This code creates a **hoverable button** that **shakes** when the user hovers over it, attracting attention and providing a fun interactive element.
- The **hover effect** not only changes the button's colors but also triggers the **shaking animation**, making it more dynamic.
