### **CSS Float & Clip-path**

---

#### **1. `float` Property in CSS:**

The `float` property allows you to place an element on the left or right side of its container. This enables text or inline elements to wrap around it. However, the floated element is removed from the normal flow of the page, though it still remains part of the document flow.

Here's an example using the `float` property:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Float</title>
    <style>
      * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
      }

      header {
        width: 100%;
        height: 10vh;
        background-color: #451952;
        color: #fff;
      }

      header .container {
        width: 90vw;
        margin: 0 auto;
      }

      header a {
        color: #fff;
        font-size: 20px;
      }

      header .logo-brand {
        width: 30%;
        float: left;
        text-align: center;
        line-height: 10vh;
      }

      header .navbar-nav {
        width: 70%;
        float: right;
        text-align: right;
        line-height: 10vh;
      }

      header .navbar-nav ul li {
        list-style: none;
        display: inline-block;
        padding: 0 25px;
      }
    </style>
  </head>
  <body>
    <header>
      <div class="container">
        <div class="logo-brand">
          <a href="#">Darshan Vasani</a>
        </div>
        <nav class="navbar-nav">
          <ul>
            <li><a href="#">Home</a></li>
            <li><a href="#">About</a></li>
            <li><a href="#">Services</a></li>
            <li><a href="#">Contact</a></li>
          </ul>
        </nav>
      </div>
    </header>
  </body>
</html>
```

**Explanation:**
- The `.logo-brand` is floated to the left, and the `.navbar-nav` is floated to the right.
- This creates a layout where the brand logo is on the left side and the navigation menu is on the right side of the header.

---

#### **2. `clip-path` Property in CSS:**

The `clip-path` property creates a clipping region for an element, specifying which parts should be visible. It allows you to apply different shapes like circles, polygons, and ellipses to an element.

Here's an example using the `clip-path` property:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Clip-path</title>
    <style>
      * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
      }

      body {
        width: 100%;
        height: 100vh;
        background-color: hsl(0, 0%, 91%);
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 50px;
      }

      img {
        width: 50%;
        border-radius: 10px;
        /* You can experiment with different clip-path values */
        clip-path: polygon(20% 0%, 80% 0%, 100% 20%, 100% 80%, 80% 100%, 20% 100%, 0% 80%, 0% 20%);
      }
    </style>
  </head>
  <body>
    <h1>CSS Clip-path</h1>
    <img src="../../images/html.png" alt="HTML image with clip-path" />
  </body>
</html>
```

**Explanation:**
- The `clip-path` is used to create a polygonal clipping path for the image, effectively hiding parts of the image that fall outside the defined polygon.
- You can define other shapes like `circle()`, `ellipse()`, and `polygon()` for more customized clipping paths.

---

### **Summary:**

- **`float` Property**: Allows elements to float left or right, with content wrapping around them. It's commonly used for layout purposes such as creating sidebars or image placements within text.
  
- **`clip-path` Property**: Allows you to clip an element to a specific shape (like a circle, polygon, or ellipse), hiding parts of the element outside the shape.

Both properties can be used to create complex layouts and designs without the need for extra markup or JS-based approaches.