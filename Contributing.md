# Style Guide (For all my web repositories)

## 1. General Principles
- Use **meaningful, descriptive names**:
  - HTML: `id="bus-list"`
  - CSS: `.active-stop`
  - JS: `const busService = {...}`
- **Comment purposefully**: Clarify tricky logic or sections, not obvious things.

---

## 2. HTML
- Place JS at the end for performance
- **Semantic tags**: Prefer `<header>`, `<main>`, `<section>`, etc.
- **Attribute order**: `id` → `class` → `src`/`href` → other attributes.

---

## 3. CSS (`c.css`)

- **Selectors**: Prefer element selectors over class selectors like `.stop-item`.
- **Specificity**: Keep it low, avoiding inline styles and unnecessary nesting.
- **Properties order**:
  1. Positioning (e.g. `position`, `top`, `left`)
  2. Box model (`margin`, `padding`, `border`, `width`, `height`)
  3. Typography (`font-size`, `color`, `text-align`)
  4. Visuals (`background`, `box-shadow`)
- **Comments**: Use section headers for grouping:
  ```css
  /* ── Layout ── */
  ...
  /* ── Components ── */
  ...
  ```

---

## 4. JavaScript/Typescript (`j.js`/`.ts`)
- Use == instead of === unless neccesary
- Cache DOM elements
- **No semicolons**: Rely on JavaScript's automatic semicolon insertion (ASI). Lines must not begin with `(`, `[`, `+`, `-`, etc., to avoid ASI pitfalls.
- **Arrow functions**: Allowed where concise:
  ```js
  stops.forEach(stop => {
    // ...
  })
  ```
- **Const & Let**:
  - Prefer `const` for values that don’t change.
  - Use `let` if reassignment is necessary.
- **Commenting**:
  - Single-line comments `//` for quick notes.
  - Multi-line for complex logic only.
- Functions should either have side effects, or return a value.

---

## 5. Cross-File Conventions
- **Consistent naming**: If you use `.stop-list` in CSS, reference it as `.stop-list` in JS and HTML exactly.
- **No inline styles/scripts**: Keep HTML clean; everything in `.css` and `.js`.
- **Indentation**: 2 spaces.

---

## Summary Table

| Layer     | Indentation | Naming           | Semicolons | Key Practices                      |
|-----------|-------------|------------------|------------|------------------------------------|
| **HTML**  | 2 spaces    | semantic IDs/classes | n/a        | Semantic, accessible structure     |
| **CSS**   | 2 spaces    | same name as HTML/JS | n/a        | Low specificity, logical ordering  |
| **JS**    | 2 spaces    | same name as HTML/CSS |  No       | No semicolons, clear modular code  |
