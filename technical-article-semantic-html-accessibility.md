# Why Semantic HTML Matters — Before & After (Accessibility Wins)

Semantic HTML is the practice of using HTML elements that describe their meaning and purpose (for example, `<header>`, `<nav>`, `<main>`, `<article>`, `<footer>`) instead of generic `<div>` and `<span>` containers. Using semantic tags makes content clearer for browsers, search engines, and most importantly, assistive technologies such as screen readers.

Why it matters

- Accessibility: Screen readers rely on landmarks to let users jump between header, navigation, main content, and forms.
- SEO: Search engines better understand content structure.
- Maintainability: Developers read and update code faster when structure reflects intent.

Before / After

Non-semantic (BAD):

```html
<!-- BAD: non-semantic -->
<div class="header">
  <div class="logo">My Site</div>
  <div class="nav">
    <div class="nav-item">Home</div>
    <div class="nav-item">About</div>
  </div>
</div>
<div class="main">
  <div class="article">
    <div class="title">Welcome</div>
    <div class="text">This is my paragraph.</div>
  </div>
</div>
```

Semantic (BETTER):

```html
<header>
  <div class="logo">My Site</div>
  <nav aria-label="Main navigation">
    <ul>
      <li><a href="/">Home</a></li>
      <li><a href="/about.html">About</a></li>
    </ul>
  </nav>
</header>

<main>
  <article>
    <h1>Welcome</h1>
    <p>This is my paragraph.</p>
  </article>
</main>
```

Accessibility issues I found and how I fixed them

1) Missing headings and incorrect hierarchy

- Problem: Pages used divs for titles or skipped from no h1 to h3, preventing screen reader users from getting a clear document outline.
- Fix: Replace title containers with semantic headings (`h1` → `h2` → `h3`) and ensure a single `h1` per page for the main topic.

2) Images without alt text

- Problem: Decorative or informative images without `alt` attributes cause confusion for non-visual users.
- Fix: Add meaningful `alt` attributes for informative images (`alt="Screenshot of Project X"`). For purely decorative images, use empty alt (`alt=""`) so screen readers skip them.

3) Unlabeled form controls

- Problem: Inputs lacked `<label>` associations, so labels were not announced to assistive tech.
- Fix: Associate labels with inputs using `for`/`id`, group related fields with `<fieldset>/<legend>`, and add `required` attributes + descriptive placeholders. Example:

```html
<label for="email">Email</label>
<input id="email" type="email" required />
```

Extra improvements

- Added `lang="en"` to `<html>`, ARIA label on `nav` where appropriate, and a small script to highlight the active nav item for sighted keyboard users.
- Used landmark elements (`<header>`, `<main>`, `<footer>`, `<nav>`, `<article>`, `<aside>`) to give users and assistive tech clear navigation points.

See the deployed portfolio

- Live portfolio: https://nahashonmutahi95.github.io/iyf-s11-week-01-nahashonmutahi95/

---

Author: Nahashon Mutahi
