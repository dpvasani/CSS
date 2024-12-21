# CSS Variables

## 1. What Are CSS Variables?

CSS variables, also known as **CSS custom properties**, are reusable values defined in your CSS. They help make your styles more flexible and maintainable by centralizing commonly used values.

- **Declaration:** CSS variables are defined using the `--` prefix.
- **Usage:** Access variables using the `var()` function.
- Variables can hold **colors**, **sizes**, **text values**, and more.

---

## 2. Syntax for Declaring and Using CSS Variables

### Declaring a Variable:
```css
:root {
  --main-color: #3498db; /* Declaring a variable */
}
```

### Using a Variable:
```css
.button {
  background-color: var(--main-color); /* Accessing the variable */
}
```

### Example in Action:
```css
:root {
  --primary-color: #0062ff;
  --text-color: #fff;
}

h1 {
  color: var(--primary-color);
}

p {
  color: var(--text-color);
}
```

---

## 3. Benefits of Using CSS Variables

- **Centralized Management:** Change a variable's value, and it updates wherever it's used.
- **Dynamic Behavior:** CSS variables can adapt to JavaScript changes.
- **Improved Readability:** Variable names describe the purpose of a value.
- **Theme Customization:** Easily switch themes by updating variable values.

---

## 4. Practical Example with CSS Variables

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link
      href="https://fonts.googleapis.com/css2?family=Jost:wght@300;400;600&display=swap"
      rel="stylesheet"
    />
    <style>
      * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
        font-family: "Jost", sans-serif;
      }

      :root {
        --primary-color: #0062ff;
        --background-color: #080a0c;
        --text-color: #fff;
        --button-bg: #0062ff;
        --button-text: #fff;
      }

      body {
        background-color: var(--background-color);
        color: var(--text-color);
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
      }

      .button {
        background-color: var(--button-bg);
        color: var(--button-text);
        padding: 10px 20px;
        border: none;
        border-radius: 5px;
        text-transform: uppercase;
        cursor: pointer;
        font-size: 16px;
      }

      .button:hover {
        background-color: var(--text-color);
        color: var(--button-bg);
        transition: all 0.3s ease;
      }
    </style>
  </head>
  <body>
    <button class="button">Click Me</button>
  </body>
</html>
```

---

## 5. Dynamic Updates with JavaScript

CSS variables can be dynamically updated using JavaScript.

### Example:
```html
<style>
  :root {
    --background-color: #080a0c;
  }

  body {
    background-color: var(--background-color);
  }
</style>
<script>
  // Dynamically change CSS variable
  document.documentElement.style.setProperty('--background-color', '#3498db');
</script>
```

---

## 6. Interview Questions

### 1. What are CSS variables, and how do they differ from preprocessor variables like Sass variables?
**Answer:** CSS variables are live and dynamic, defined in the browser and accessible globally or locally. Preprocessor variables, like those in Sass, are static and processed at compile time.

---

### 2. How can CSS variables be used for theme switching?
**Answer:** Define variables for theme-specific values (e.g., `--primary-color`) and update them dynamically for light or dark themes.

---

### 3. How do you declare a CSS variable globally?
**Answer:** Use the `:root` pseudo-class to declare global variables.

---

### 4. What happens if a CSS variable is not defined?
**Answer:** If a variable is not defined, the fallback value provided in `var()` is used. If no fallback is specified, the property will not be applied.

**Example:**
```css
color: var(--undefined-variable, red); /* Red is used as fallback */
```

--- 

### 5. Can CSS variables be used inside media queries?
**Answer:** Yes, CSS variables can be defined and changed within media queries.

**Example:**
```css
@media (max-width: 768px) {
  :root {
    --primary-color: #ff5733;
  }
}
```

# CSS Variables with Night Mode Example

CSS variables can be effectively used to implement a **Night Mode** or **Dark Mode** feature by toggling between different sets of CSS variables.

---

## Night Mode Implementation

### Approach:
1. Define light mode and dark mode variables in the `:root` and a `.dark-mode` class.
2. Use JavaScript to toggle the `.dark-mode` class on the `body` element.

---

### Complete Example:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Night Mode with CSS Variables</title>
    <style>
      /* General reset and font setup */
      * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
        font-family: "Arial", sans-serif;
      }

      /* Light Mode Variables */
      :root {
        --background-color: #ffffff;
        --text-color: #000000;
        --button-bg: #0062ff;
        --button-text: #ffffff;
        --link-color: #0062ff;
      }

      /* Dark Mode Variables */
      body.dark-mode {
        --background-color: #121212;
        --text-color: #ffffff;
        --button-bg: #1e88e5;
        --button-text: #ffffff;
        --link-color: #90caf9;
      }

      /* Apply Variables */
      body {
        background-color: var(--background-color);
        color: var(--text-color);
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        min-height: 100vh;
        transition: background-color 0.3s ease, color 0.3s ease;
      }

      h1 {
        margin-bottom: 20px;
      }

      p {
        margin-bottom: 40px;
      }

      button {
        background-color: var(--button-bg);
        color: var(--button-text);
        border: none;
        padding: 10px 20px;
        border-radius: 5px;
        font-size: 16px;
        cursor: pointer;
        transition: background-color 0.3s ease, color 0.3s ease;
      }

      a {
        color: var(--link-color);
        text-decoration: none;
        margin-top: 20px;
      }

      button:hover {
        opacity: 0.9;
      }
    </style>
  </head>
  <body>
    <h1>Night Mode Example</h1>
    <p>Click the button below to toggle between Light Mode and Night Mode.</p>
    <button id="toggleButton">Toggle Night Mode</button>
    <a href="#">Learn More</a>

    <script>
      const toggleButton = document.getElementById("toggleButton");
      toggleButton.addEventListener("click", () => {
        document.body.classList.toggle("dark-mode");
      });
    </script>
  </body>
</html>
```

---

## How It Works:

1. **Light Mode:** By default, the `:root` contains the light mode variables (`--background-color`, `--text-color`, etc.).
2. **Dark Mode:** The `.dark-mode` class overrides these variables with dark mode values.
3. **Toggling Night Mode:** The JavaScript toggles the `.dark-mode` class on the `body`, switching between light and dark themes.

---

### Features:
- Smooth transitions using `transition` on `background-color` and `color`.
- Flexible design with reusable variables.
- Easy to extend for more themes.