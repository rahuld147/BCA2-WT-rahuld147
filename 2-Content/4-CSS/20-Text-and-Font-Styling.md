# Day 20 — CSS Text & Font Styling

📖 **Type:** Theory Session
🕐 **Duration:** 2 Hours
📚 **Unit:** 4 — CSS

---

## Learning Objectives

By the end of this session, students will be able to:
- Style text using various CSS text properties
- Use web-safe fonts and Google Fonts
- Apply font shorthand property
- Understand CSS units (px, em, rem, %, vw/vh)

---

## 1. CSS Font Properties

> **Analogy:** Choosing fonts is like choosing **handwriting on a poster**. A wedding invitation uses elegant script. A tech startup uses clean sans-serif. The same text feels completely different just by changing the font.

### Font Family

```css
/* Font stack: browser tries first font, falls back to next */
body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

h1 {
    font-family: Georgia, 'Times New Roman', Times, serif;
}

code {
    font-family: 'Courier New', Courier, monospace;
}
```

### Web-Safe Fonts

These fonts are available on almost every computer:

| Serif | Sans-Serif | Monospace |
|-------|-----------|-----------|
| Times New Roman | Arial | Courier New |
| Georgia | Verdana | Lucida Console |
| Garamond | Tahoma | Consolas |

### Google Fonts (Free Custom Fonts)

```html
<head>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Poppins', sans-serif; }
    </style>
</head>
```

---

## 2. Font Size & Weight

### Size Units

| Unit | Meaning | Example |
|------|---------|---------|
| `px` | Absolute pixels | `font-size: 16px;` |
| `em` | Relative to parent | `font-size: 1.5em;` (1.5× parent) |
| `rem` | Relative to root (`<html>`) | `font-size: 1.2rem;` |
| `%` | Percentage of parent | `font-size: 120%;` |
| `vw` | % of viewport width | `font-size: 3vw;` |

> **Rule of thumb:** Use `rem` for font sizes (consistent, accessible) and `px` for borders/shadows.

### Font Weight

```css
.light    { font-weight: 300; }
.normal   { font-weight: 400; }   /* same as: normal */
.semibold { font-weight: 600; }
.bold     { font-weight: 700; }   /* same as: bold */
.heavy    { font-weight: 900; }
```

### Font Shorthand

```css
/* font: style weight size/line-height family; */
p {
    font: italic 600 18px/1.6 'Poppins', sans-serif;
}
```

---

## 3. Text Properties

### Text Alignment & Decoration

```css
.center     { text-align: center; }
.right      { text-align: right; }
.justify    { text-align: justify; }

.underline  { text-decoration: underline; }
.strike     { text-decoration: line-through; }
.no-line    { text-decoration: none; }           /* Remove link underline */

.upper      { text-transform: uppercase; }
.lower      { text-transform: lowercase; }
.cap        { text-transform: capitalize; }
```

### Text Shadow

```css
h1 {
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
    /* horizontal vertical blur color */
}

/* Neon glow effect */
.neon {
    color: #fff;
    text-shadow: 0 0 10px #0ff, 0 0 20px #0ff, 0 0 40px #0ff;
}
```

### Line Height & Spacing

```css
p {
    line-height: 1.8;         /* 1.8× font size */
    letter-spacing: 1px;      /* Space between letters */
    word-spacing: 3px;         /* Space between words */
    text-indent: 40px;         /* First line indent */
}
```

---

## 4. Complete Text Styling Example

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&family=Playfair+Display:wght@700&display=swap" rel="stylesheet">
    <title>Typography Showcase</title>
    <style>
        body {
            font-family: 'Poppins', sans-serif;
            font-size: 16px;
            line-height: 1.8;
            color: #333;
            max-width: 800px;
            margin: 40px auto;
            padding: 0 20px;
        }

        h1 {
            font-family: 'Playfair Display', serif;
            font-size: 2.5rem;
            color: #1565C0;
            text-align: center;
            text-transform: uppercase;
            letter-spacing: 3px;
            margin-bottom: 5px;
        }

        .subtitle {
            text-align: center;
            font-weight: 300;
            font-size: 1.1rem;
            color: #777;
            margin-bottom: 30px;
        }

        h2 {
            font-size: 1.5rem;
            color: #0D47A1;
            border-bottom: 2px solid #E3F2FD;
            padding-bottom: 5px;
            margin-top: 25px;
        }

        p {
            text-align: justify;
            margin-bottom: 15px;
        }

        .drop-cap::first-letter {
            font-size: 3.5em;
            float: left;
            line-height: 1;
            margin-right: 8px;
            color: #1565C0;
            font-weight: 700;
        }

        .highlight {
            background: linear-gradient(to bottom, transparent 60%, #FFEB3B 60%);
            padding: 0 2px;
        }

        blockquote {
            font-style: italic;
            border-left: 4px solid #1565C0;
            padding: 10px 20px;
            margin: 20px 0;
            background: #F5F5F5;
            color: #555;
        }

        .small-caps {
            font-variant: small-caps;
            font-size: 1.1rem;
        }
    </style>
</head>
<body>

    <h1>Typography in CSS</h1>
    <p class="subtitle">Mastering the art of beautiful text on the web</p>

    <h2>The Power of Fonts</h2>
    <p class="drop-cap">Typography is the art and technique of arranging type to make 
    written language legible, readable, and visually appealing. In web design, 
    good typography can make or break a website's user experience.</p>

    <h2>Why Typography Matters</h2>
    <p>Studies show that <span class="highlight">95% of web content is text</span>. 
    Good typography improves readability, establishes visual hierarchy, and creates 
    emotional connections with the reader.</p>

    <blockquote>
        "Web design is 95% typography." — Oliver Reichenstein
    </blockquote>

    <h2>CSS Font Stack</h2>
    <p>Always provide a <span class="highlight">font stack</span> — a list of fonts 
    in order of preference. If the user's device doesn't have the first font, the 
    browser tries the next one, and so on.</p>

    <p class="small-caps">This text uses CSS small-caps variant for a classic look.</p>

</body>
</html>
```

---

## Practice Exercise

Create a blog article page with:
1. A serif heading font (from Google Fonts)
2. A sans-serif body font
3. Drop cap on the first paragraph
4. Highlighted important phrases
5. A blockquote with special styling
6. Proper line-height, letter-spacing, and text-indent

---

## Summary

| Property | Purpose | Example |
|----------|---------|---------|
| `font-family` | Set typeface | `'Poppins', sans-serif` |
| `font-size` | Set text size | `16px`, `1.2rem` |
| `font-weight` | Bold/light | `400`, `700`, `bold` |
| `font-style` | Italic | `italic`, `normal` |
| `text-align` | Alignment | `center`, `justify` |
| `text-decoration` | Underline/strikethrough | `none`, `underline` |
| `text-transform` | Case | `uppercase`, `capitalize` |
| `text-shadow` | Shadow effect | `2px 2px 4px #000` |
| `line-height` | Vertical spacing | `1.6` |
| `letter-spacing` | Character spacing | `2px` |

---

*Day 20 of 55 | Unit 4 — CSS | Web Technology (25BCA060)*
