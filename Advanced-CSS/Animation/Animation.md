# Animation in CSS

## 1. Animation Properties

### `animation-name`
Defines the name of the keyframe animation to be applied.

- **Syntax:** `animation-name: keyframe-name;`
- Links the animation to the keyframe defined using `@keyframes`.

**Example:**
```css
.box {
  animation-name: myAnimation;
}
```

---

### `animation-duration`
Specifies how long the animation should run.

- **Syntax:** `animation-duration: time;`
- Values can be in seconds (`s`) or milliseconds (`ms`).

**Example:**
```css
.box {
  animation-duration: 2s;
}
```

---

### `animation-timing-function`
Controls the speed curve of the animation.

- **Common Values:** `ease`, `linear`, `ease-in`, `ease-out`, `ease-in-out`.
- **Syntax:** `animation-timing-function: timing-function;`

**Example:**
```css
.box {
  animation-timing-function: ease-in-out;
}
```

---

### `animation-delay`
Delays the start of the animation.

- **Syntax:** `animation-delay: time;`
- Can be in seconds (`s`) or milliseconds (`ms`).

**Example:**
```css
.box {
  animation-delay: 1s;
}
```

---

### `animation-iteration-count`
Determines how many times the animation runs.

- **Syntax:** `animation-iteration-count: number | infinite;`

**Example:**
```css
.box {
  animation-iteration-count: infinite;
}
```

---

### `animation-direction`
Specifies the direction the animation runs.

- **Values:**
  - `normal`: Forward direction only.
  - `reverse`: Backward direction only.
  - `alternate`: Alternates between forward and backward.
  - `alternate-reverse`: Alternates starting in reverse.

**Example:**
```css
.box {
  animation-direction: alternate;
}
```

---

### `animation-fill-mode`
Controls how the element's styles are applied before and after the animation.

- **Values:**
  - `none`: Default. Styles are not retained.
  - `forwards`: Retains the styles from the last keyframe.
  - `backwards`: Applies styles from the first keyframe before the animation starts.
  - `both`: Combines `forwards` and `backwards`.

**Example:**
```css
.box {
  animation-fill-mode: forwards;
}
```

---

### `@keyframes`
Defines the sequence of styles for the animation.

- **Syntax:**
```css
@keyframes animation-name {
  from {
    /* Starting styles */
  }
  to {
    /* Ending styles */
  }
}
```

OR 

```css
@keyframes animation-name {
  0% {
    /* Starting styles */
  }
  100% {
    /* Ending styles */
  }
}
```

**Example:**
```css
@keyframes myAnimation {
  from {
    background-color: red;
    transform: translateX(0);
  }
  to {
    background-color: blue;
    transform: translateX(200px);
  }
}
```

---

## 2. Sample CSS Code

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Jost";
}

body {
  background-color: #2b3033;
}

.container {
  width: 100vw;
  height: 100vh;
}

.box {
  width: 100px;
  height: 100px;
  background-color: #4861ec;
  border-radius: 50%;
  margin: 50px;
  display: inline-block;
  animation-name: trip;
  animation-duration: 2.5s;
  animation-timing-function: linear;
  animation-iteration-count: 2;
  animation-direction: alternate;
}

@keyframes trip {
  from {
    background-color: #ffbb5cb5;
    transform: translate(200px, 0%);
  }
  25% {
    background-color: #fcbf49;
    transform: translate(calc(90vw - 10%));
  }
  50% {
    background-color: #000000;
    transform: translate(calc(90vw - 10%), 500px);
  }
  75% {
    background-color: #fcbf49;
    transform: translate(20%, 500px);
  }
  to {
    background-color: #ffbb5cb5;
    transform: translate(20%, 0%);
  }
}
```

---

## 3. Key Notes: Animations on Page Load

- **CSS animations don't require pseudo-classes like `:hover`**. They can start on page load by defining `animation-name` and related properties.
- Combine properties into shorthand for cleaner code:
```css
animation: trip 2.5s linear 1s infinite alternate;
```

---

## 4. Interview Questions

### 1. Can CSS animations be applied without user interaction like `:hover`?
**Answer:** Yes, animations can run on page load by defining an `animation-name` and related properties.

---

### 2. Explain the purpose of the `@keyframes` rule.
**Answer:** It defines the animation sequence by specifying styles at various percentages (`0%` to `100%`) or using `from` and `to`.

---

### 3. What does the `animation-fill-mode` property do?
**Answer:** It determines how styles are applied to the element before and after the animation.

---

### 4. How can an animation alternate its direction when it ends?
**Answer:** Use the `animation-direction` property with the value `alternate` or `alternate-reverse`.

**Example:**
```css
.box {
  animation-direction: alternate;
}
```