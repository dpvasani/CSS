The code you've shared is a basic example of a webpage with inline, internal, and external CSS capabilities. Here's how to incorporate all three types of CSS styling:

### **Folder Structure**
```
/Basics
    |-- index.html
    |-- style.css
```

### **1. Inline CSS**
Inline CSS is added directly to an HTML element using the `style` attribute. For example:
```html
<h1 style="color: blue; text-align: center;">CSS Basic</h1>
```

### **2. Internal CSS**
Internal CSS is defined within the `<style>` tag in the `<head>` section of the HTML document. For example:
```html
<head>
  <style>
    .para {
      color: green;
      font-size: 18px;
    }
    #btn {
      background-color: lightblue;
      text-decoration: none;
      padding: 10px 20px;
      border-radius: 5px;
    }
  </style>
</head>
```

### **3. External CSS**
External CSS is linked to the HTML document via a `<link>` tag in the `<head>`. The styles are written in a separate file (e.g., `style.css`). Example `style.css` content:
```css
body {
  font-family: Arial, sans-serif;
  margin: 20px;
  background-color: #f4f4f9;
}

h1 {
  color: darkblue;
  text-align: center;
}

a#btn {
  color: white;
  background-color: red;
  text-decoration: none;
  padding: 10px 20px;
  border-radius: 5px;
}
```

### **Final `index.html` with All CSS Types**
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Basic of CSS</title>
    <!-- External CSS -->
    <link rel="stylesheet" href="style.css" />
    <!-- Internal CSS -->
    <style>
      .para {
        color: green;
        font-size: 18px;
      }
      #btn {
        background-color: lightblue;
        text-decoration: none;
        padding: 10px 20px;
        border-radius: 5px;
      }
    </style>
  </head>
  <body>
    <h1 style="color: blue; text-align: center;">CSS Basic</h1> <!-- Inline CSS -->
    <p class="para">
      Welcome To My CSS Repositories! You can learn CSS from here.
    </p>
    <br />
    <a href="https://github.com/dpvasani/CSS" id="btn" target="_blank">Follow</a>
  </body>
</html>
```

### **Explanation**
- **Inline CSS**: The `h1` tag uses inline styles.
- **Internal CSS**: The `<style>` block in the `<head>` defines the styles for `.para` and `#btn`.
- **External CSS**: The `style.css` file handles general page-wide styles, like `body` and `h1`.

This approach allows you to understand and manage different CSS types effectively.