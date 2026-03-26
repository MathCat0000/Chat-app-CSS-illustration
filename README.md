# Frontend Mentor - Chat app CSS illustration solution

This is a solution to the [Chat app CSS illustration challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/chat-app-css-illustration-O5auMkFqY).

The project was used not only to complete the layout but as a **laboratory for knowledge extraction** focused on CSS architecture, layout reasoning, and Git workflow.

---

# Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [CSS Concepts Learned](#css-concepts-learned)
  - [Git & Repository Setup](#git--repository-setup)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
  - [AI Collaboration](#ai-collaboration)
- [Author](#author)

---

# Overview

## The challenge

Users should be able to:

- View the optimal layout for the component depending on their device's screen size
- Build a mobile chat interface illustration using CSS

The project includes:

- a hero layout
- a simulated phone UI
- message bubbles
- gradients
- decorative shapes
- responsive typography

---

# Links

Solution URL  
https://github.com/MathCat0000/Chat-app-CSS-illustration

Live Site URL  
https://mathcat0000.github.io/Chat-app-CSS-illustration/

---

# My process

## Built with

- Semantic HTML5
- CSS Custom Properties
- CSS Grid
- CSS transforms
- pseudo elements
- responsive typography with `rem`
- Git
- GitHub Pages

---

# What I learned

This project was used as a **CSS architecture laboratory**.

The focus was not only finishing the layout but extracting knowledge about:

- layout systems
- CSS units
- pseudo-elements
- positioning mechanisms
- design tokens
- Git workflow

---

# CSS Concepts Learned

## Layout primitives

Before implementing styles the layout can be reduced to primitives:

```
page
 hero section
  phone card
   chat interface
  text content
```

Main layout system used:

```
CSS Grid
```

Example:

```css
.hero {
  display: grid;
  place-items: center;
}
```

This centers the entire hero content.

---

# Positioning system

### position: relative

Creates a **positioning reference**.

Example:

```css
.container {
  position: relative;
}
```

This allows children with `position:absolute` to use the container as reference.

---

### position: absolute

Removes element from normal flow and allows free positioning.

Example:

```css
.box {
  position: absolute;
  top: 10px;
  left: 10px;
}
```

Coordinates are calculated relative to the **nearest positioned ancestor**.

---

### Positioning rule

```
relative → defines reference box
absolute → positions element inside reference
```

---

# Absolute vs Relative reference

Example:

```
left:50%
transform:translateX(-50%)
```

Interpretation:

| Property         | Reference      |
| ---------------- | -------------- |
| left:50%         | parent         |
| translateX(-50%) | element itself |

This pattern is commonly used for **perfect centering**.

---

# translate() percentage behavior

Percentages in `transform: translate()` are relative to **the element itself**, not its parent.

Example:

```
translateX(-50%)
```

Means:

```
move left by 50% of element width
```

---

# Pseudo-elements

Example:

```
.phone-card::after
```

Pseudo-elements create **visual layers separate from structure**.

Used when:

- decoration should not affect layout
- extra visual layers are needed
- stacking order must be controlled

Example:

```css
.phone-card::after {
  content: "";
  position: absolute;
  inset: 0;
}
```

---

# ::before vs ::after

Both behave similarly.

| pseudo-element | insertion position |
| -------------- | ------------------ |
| ::before       | first child        |
| ::after        | last child         |

Choice depends on stacking order.

---

# CSS Custom Properties (Design Tokens)

Example:

```css
:root {
  --radius-phone: 2rem;
  --shadow-phone: 0 20px 40px rgba(62, 39, 83, 0.18);
}
```

These represent **reusable design tokens**.

Tokens can represent:

- colors
- spacing
- radius
- shadows
- layout sizes

Example usage:

```css
.phone-card {
  border-radius: var(--radius-phone);
  box-shadow: var(--shadow-phone);
}
```

---

# box-shadow values

Example:

```
0 20px 40px rgba(62,39,83,0.18)
```

Meaning:

| value     | meaning           |
| --------- | ----------------- |
| 0         | horizontal offset |
| 20px      | vertical offset   |
| 40px      | blur radius       |
| rgba(...) | color + opacity   |

---

# Why shadows use px

Shadows use fixed units because they represent **visual effects**, not layout.

Relative units would cause shadows to scale with typography.

Best practice:

```
px → shadows, blur, borders
rem → typography and spacing
```

---

# rem units for typography

Example:

```css
font-size: 1.5rem;
```

`rem` is relative to the **root font-size**.

Benefits:

- global scaling
- accessibility
- responsive typography

Example:

```
html { font-size:18px }
```

All typography scales automatically.

---

# min-height vs min-width

Example:

```css
body {
  min-height: 100vh;
}
```

Used to guarantee that the page fills the viewport height.

`min-width` is rarely necessary because body width already follows viewport width.

---

# HSL color usage

Example:

```
hsl(271,36%,24%)
```

HSL separates color into components:

| value      | meaning      |
| ---------- | ------------ |
| hue        | color family |
| saturation | intensity    |
| lightness  | brightness   |

Advantages:

- easier color manipulation
- easier palette consistency
- easier reasoning about colors

---

# Avatar concept

The term **avatar** in UI represents a visual representation of a user.

Example:

```
<img class="avatar">
```

Origin:

```
Sanskrit: avatāra
meaning manifestation or representation
```

In interfaces it represents:

- user identity
- chat sender
- profile image

---

# Git & Repository Setup

Local project folder:

```
chat-app-css-illustration-master
```

Initialize Git inside that folder:

```bash
git init
git add .
git commit -m "initial commit"
```

Connect repository:

```bash
git remote add origin https://github.com/MathCat0000/Chat-app-CSS-illustration.git
```

Push to GitHub:

```bash
git push -u origin main
```

---

# Git ignore

Example rule to ignore a personal folder:

```
/0/
```

Meaning:

ignore folder named `0` in repository root.

---

# GitHub Pages URL rule

Pages follow this pattern:

```
https://username.github.io/repository-name/
```

Example:

```
https://mathcat0000.github.io/Chat-app-CSS-illustration/
```

---

# Continued development

Topics to reinforce:

- CSS positioning system
- layout reasoning before implementation
- separating structure and decoration
- CSS architecture layers
- design tokens usage
- pseudo-element layering
- Git workflow automation

---

# Useful resources

Frontend Mentor  
https://www.frontendmentor.io

MDN CSS documentation  
https://developer.mozilla.org/en-US/docs/Web/CSS

---

# AI Collaboration

AI was used as a **conceptual debugging and learning tool**.

Main uses:

- understanding CSS layout mechanisms
- clarifying positioning systems
- explaining transform behavior
- understanding design tokens
- debugging Git issues
- understanding GitHub Pages deployment

The interaction functioned as a **knowledge extraction loop** rather than code generation.

---

# Author

GitHub  
https://github.com/MathCat0000
