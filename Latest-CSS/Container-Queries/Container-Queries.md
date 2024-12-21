### **Container Queries Example: Responsive Layouts Based on Container Size**

Container queries allow you to apply styles to an element based on the size of its container instead of the viewport. This feature enables more flexible and dynamic layouts. Below is an example showing how to use container queries to change the layout based on the size of the container element.

---

#### **Code Explanation:**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Container Queries</title>
    <style>
      * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
        font-family: "Urbanist", sans-serif;
      }

      body {
        height: 100vh;
        background-color: #191717;
      }

      /* Container Styles */
      .container,
      .media {
        max-width: 800px;
        height: auto;
        border: 5px solid #ffb000;
        margin-right: 200px;
      }

      /* Child Grid Layout */
      .container div {
        display: grid;
        grid-template-columns: 1fr 0.5fr;
        align-items: center;
      }

      /* Container Query Setup */
      .container {
        container-type: inline-size;
        container-name: changelayout;
      }

      /* Image Styling */
      img {
        width: 100%;
        height: auto;
      }

      /* Heading Styling */
      h1 {
        text-align: center;
        color: #fff;
        font-weight: bold;
        text-transform: capitalize;
        font-size: 32px;
        text-shadow: -3px 10px 10px rgba(249, 141, 141, 0.2);
        animation: floating 2s linear infinite alternate;
      }

      /* Container Query: Change layout for container width <= 600px */
      @container changelayout (width <= 600px) {
        .container div {
          grid-template-columns: 1fr;
        }

        h1 {
          color: #ffb000;
          text-transform: uppercase;
          padding: 20px 0;
        }
      }

      /* Media Query: Change layout for viewport width <= 600px */
      @media (width <= 600px) {
        .media div {
          grid-template-columns: 1fr;
        }

        h1 {
          color: #ffb000;
          text-transform: uppercase;
          padding: 20px 0;
        }
      }
    </style>
  </head>
  <body>
    <br /><br />

    <!-- Container with Container Query -->
    <div class="container">
      <div>
        <img src="../../images/html.png" alt="Image" />
        <h1>New CSS Feature: Container Queries</h1>
      </div>
    </div>

    <br /><br />

    <!-- Container with Media Query -->
    <div class="media">
      <div>
        <img src="../../images/html.png" alt="Image" />
        <h1>New CSS Feature: Container Queries</h1>
      </div>
    </div>
  </body>
</html>
```

---

### **Key Points:**

1. **`container-type`**:  
   The `container-type` property defines the containment used for the container query. In this example, the `.container` uses `inline-size` as the containment type, which means the layout changes based on the width of the container.

2. **`@container` Query**:  
   The `@container changelayout (width <= 600px)` rule applies styles when the `.container` element's width is less than or equal to 600px. In this case, the layout of the child grid changes to a single column (`grid-template-columns: 1fr`), and the heading color changes.

3. **`@media` Query**:  
   The media query (`@media (width <= 600px)`) applies the same layout change for the viewport width but is not dependent on the size of the container itself. It shows how container queries work alongside traditional media queries.

---

### **Container Queries vs Media Queries:**
- **Container Queries** apply styles based on the size of an element's container.
- **Media Queries** apply styles based on the viewport size.

Both of these can be used together to create highly responsive designs. In this case, the container query modifies the layout when the container is resized, while the media query ensures that styles are applied when the viewport is resized.

