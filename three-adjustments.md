# Three Adjustments to `index.html`

## 1. Changed the color scheme

I changed the color scheme to blue, white, and standard red so it matches the Coginchaug Blue Devils logo. The CSS variables make it possible to update colors across the whole website from one place.

Before:

```css
--ink: #1b3157;
--deep: #0b1f3a;
--blue: #d6a21f;
--sky: #f0ca62;
--paper: #fffdf7;
```

After:

```css
--ink: #2b287f;
--deep: #1f1c66;
--blue: #8b1e2d;
--sky: #ffffff;
--paper: #ffffff;
```

Deep blue now matches the main color in the logo, white keeps the page clean, and dark red (`#8B1E2D`) highlights buttons, numbers, labels, and important accents without overpowering the page.

## 2. Changed the headings' font and size

I changed the display font from a narrow sans-serif font to a bold serif font. I also reduced the maximum hero-heading size and increased its line height, which makes the title easier to read.

Before:

```css
.display {
  font-family: Impact, "Arial Narrow", sans-serif;
  font-weight: 400;
  letter-spacing: .025em;
  text-transform: uppercase;
}

h1 {
  font-size: clamp(3.5rem, 9vw, 7.6rem);
  line-height: .88;
}
```

After:

```css
.display {
  font-family: Georgia, "Times New Roman", serif;
  font-weight: 800;
  letter-spacing: -.025em;
}

h1 {
  font-size: clamp(3.2rem, 8vw, 6.8rem);
  line-height: .95;
}
```

This demonstrates that HTML supplies the heading text, while CSS controls how that heading looks.

## 3. Added pictures to the website

I added a photograph of the Coginchaug Benchwarmers booth behind the main heading, the Blue Devils logo in the header and footer, and a photograph of Coginchaug Regional High School in the Our Story section. A dark transparent gradient sits over the heading photograph so the white text remains readable.

Before:

```css
.hero {
  background:
    linear-gradient(120deg, rgba(16,35,66,.98), rgba(16,35,66,.72)),
    linear-gradient(155deg, #244a76 0 52%, #162e50 52%);
}
```

After:

```css
.hero {
  background-image:
    linear-gradient(90deg, rgba(11,31,58,.94), rgba(11,31,58,.42)),
    url("data:image/jpeg;base64,...");
  background-position: center;
  background-size: cover;
}
```

The photograph is encoded directly into `index.html` as a base64 data URL. This keeps the page self-contained, so the background still appears when the single HTML file is moved or submitted without a separate image folder.

## What I learned

Builder output is often written for a framework and may depend on build tools, imported components, and separate assets. A browser cannot always open that source directly. In this version, the HTML provides the website's structure and text, while the CSS inside the `<style>` element controls colors, fonts, spacing, layout, and responsive behavior. Because both are contained in `index.html`, the finished page opens directly in a browser without a framework or build step.
