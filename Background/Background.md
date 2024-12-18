# Background In CSS

## Background Properties

### 1. background-color
Sets the background color of an element.
```css
/* Example */
background-color: #FF5733;
```

### 2. background-image
Specifies an image to be used as the background.
```css
/* Example */
background-image: url('image.jpg');
```

### 3. background-repeat
Determines how the background image repeats.
- Values: `repeat`, `repeat-x`, `repeat-y`, `no-repeat`
```css
/* Example */
background-repeat: repeat-x;
```

### 4. background-position
Sets the starting position of the background image.
- Values: Coordinates like `top left`, `center center`, `bottom right`, percentages, or length values.
```css
/* Example */
background-position: center center;
```

### 5. background-size
Defines the size of the background image.
- Values: `auto`, `cover`, `contain`, percentages, or length values.
```css
/* Example */
background-size: cover;
```

### 6. background-attachment
Specifies if the background image scrolls with the content.
- Values: `scroll`, `fixed`, `local`
```css
/* Example */
background-attachment: fixed;
```

---

## Background Property in CSS3

### 7. background-blend-mode
Applies blending modes to the background image and color.
- Values: Keywords like `multiply`, `screen`, `overlay`
```css
/* Example */
background-blend-mode: multiply;
```

---

## Parallax Background Example

### Code Example:
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Parallax</title>
    <style>
      * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
        font-family: "jost";
      }

      h2 {
        font-size: 64px;
        font-weight: bold;
        text-transform: uppercase;
        color: #fff;
        text-shadow: 2px 2px 5px #000;
      }

      p {
        font-size: 20px;
        color: #fff;
      }

      section {
        width: 100%;
        height: 100vh;
        display: grid;
        place-items: center;
        text-align: center;
        background-image: linear-gradient(
            rgba(0, 0, 0, 0.3),
            rgba(0, 0, 0, 0.3)
          ),
          url("https://images.pexels.com/photos/720606/pexels-photo-720606.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1");
        background-repeat: no-repeat;
        background-size: 100% auto;
        background-attachment: fixed;
      }

      .section-2 {
        background-repeat: no-repeat;
        background-size: 100% auto;
        background-image: linear-gradient(
            rgba(0, 0, 0, 0.3),
            rgba(0, 0, 0, 0.3)
          ),
          url("https://images.pexels.com/photos/175696/pexels-photo-175696.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1");
      }
      .section-3 {
        background-repeat: no-repeat;
        background-size: 100% auto;
        background-image: linear-gradient(
            rgba(0, 0, 0, 0.3),
            rgba(0, 0, 0, 0.3)
          ),
          url("https://images.pexels.com/photos/432059/pexels-photo-432059.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1");
        background-attachment: fixed;
      }

      .section-4 {
        background-repeat: no-repeat;
        background-size: 100% auto;
        background-image: linear-gradient(
            rgba(0, 0, 0, 0.3),
            rgba(0, 0, 0, 0.3)
          ),
          url("https://images.pexels.com/photos/1894263/pexels-photo-1894263.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1");
      }
    </style>
  </head>
  <body>
    <section>
      <div>
        <h2>Parallax</h2>
        <p>CSS Learning</p>
      </div>
    </section>
    <section class="section-2">
      <div>
        <h2>Darshan Vasani</h2>
        <p>CSS Learning</p>
      </div>
    </section>
    <section class="section-3">
        <div>
            <h2>Darshan Vasani</h2>
            <p>CSS Learning</p>
          </div>
    </section>
    <section class="section-4">
        <div>
            <h2>Darshan Vasani</h2>
            <p>CSS Learning</p>
          </div>
    </section>
  </body>
</html>
```

---

## Interview Questions

### 1. How can you set a background image for an element using CSS?
You can set a background image using the `background-image` property:
```css
background-image: url('image.jpg');
```

### 2. How can you make a background image cover the entire element without distortion?
Use `background-size: cover;` to ensure the background image covers the container while maintaining its aspect ratio:
```css
background-size: cover;
```

### 3. How can you apply multiple background images to a single element?
Use the `background-image` property with a comma to separate multiple image URLs:
```css
background-image: url('image1.jpg'), url('image2.jpg');
```

### 4. What property controls the image scroll behavior, and how is it related to parallax effects?
The `background-attachment` property controls image scroll behavior. For parallax effects, use:
```css
background-attachment: fixed;
```
