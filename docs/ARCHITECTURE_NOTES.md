
# CSS Architecture Notes - Module 2

**Project:** Beginner's Guide to Web Design  
**Course:** GIT 414

## 1. CSS Organization

For my website, I decided to keep all the CSS in one stylesheet called `css/styles.css`. Since my website only has five pages, I think this makes the most sense for now.

I organized the stylesheet using the six layers we learned about in Module 2:

```css
@layer reset, base, layout, components, utilities, overrides;
```

Each layer has a different purpose:

- **Reset:** Removes some default browser spacing and sets up box sizing.
- **Base:** Handles the main colors, fonts, headings, and links.
- **Layout:** Controls page containers, spacing, grids, and responsive layouts.
- **Components:** Styles reusable parts like navigation, cards, buttons, diagrams, and code examples.
- **Utilities:** Contains small helper classes for things like centered text.
- **Overrides:** Handles the skip link and print styles.

The layers help me control which styles take priority without needing complicated selectors or `!important`.

## 2. Design Tokens and Custom Properties

I used CSS custom properties to keep the website's colors, fonts, and spacing consistent.

For example:

```css
:root {
  --color-text: #24313a;
  --color-primary: #205b79;
  --space-medium: 1rem;
  --border-radius: 6px;
}
```

Instead of typing the same values repeatedly, I can reuse them with `var()`.

I also used a few custom properties inside individual components, like the topic cards:

```css
.topic-card {
  --card-background: var(--color-background);
  --card-padding: var(--space-medium);

  background-color: var(--card-background);
  padding: var(--card-padding);
}
```

This makes it easier to update the cards later without having to change every single one.

## 3. Reusable Components and Class Names

Since my website has five pages, I wanted the same styles to work across all of them.

Some of the reusable components I created include:

- Navigation links
- Topic cards
- Buttons
- Code examples
- Educational diagrams
- Information callouts
- Footer

I tried to keep the class names simple and descriptive, like `.topic-card`, `.site-nav`, and `.code-example`.

For smaller parts of a component, I used names like `.topic-card__title` and `.site-nav__link`.

I also included utility classes such as `.text-center`, `.flow`, and `.visually-hidden`. These help with smaller styling changes without needing a completely new component.

## 4. Interactive States and Accessibility

I included a few different states to make the website easier to navigate.

- **Hover:** Changes how links, buttons, and cards look when someone moves their mouse over them.
- **Focus-visible:** Adds a visible outline so keyboard users can tell which link is selected.
- **Current page:** Uses `[aria-current="page"]` to show which page someone is currently viewing.
- **Active:** Changes a button's background color while it's being pressed.

I also added a skip link so keyboard users can jump straight to the main content.

Accessibility is one of the topics my website teaches, so I wanted to make sure I was using some of those same practices in my own design.

## 5. Responsive Layouts and Print Styles

I used a mobile-first approach, starting with a single-column layout on smaller screens.

At 768px, some sections change into two columns. At 1200px, the homepage topic cards can display in four columns.

I also used a maximum container width of 1152px so the content doesn't stretch too far across larger screens. Code examples have their own horizontal scrolling area so longer code lines don't make the entire page scroll sideways.

For printing, I added an `@media print` section that removes navigation and buttons, keeps the background white, and makes the lesson content easier to read on paper.

This should be useful for people who want to print the HTML or CSS lessons.

## 6. Refactoring Examples

Since I started this capstone website from scratch, I didn't have an older stylesheet to clean up. However, I used what we learned about refactoring to avoid repeating unnecessary CSS.

Here are three examples.

### Example 1: Reusing Card Styles

**Before:**

```css
.html-card {
  padding: 16px;
  border: 1px solid #cccccc;
}

.css-card {
  padding: 16px;
  border: 1px solid #cccccc;
}
```

**After:**

```css
.topic-card {
  padding: var(--card-padding);
  border: 1px solid var(--color-border);
}
```

Instead of giving each topic its own CSS, I used one shared `.topic-card` class. This keeps the cards consistent and makes them easier to update.

### Example 2: Reusing Colors

**Before:**

```css
header a {
  color: #205b79;
}

footer a {
  color: #205b79;
}
```

**After:**

```css
:root {
  --color-primary: #205b79;
}

a {
  color: var(--color-primary);
}
```

Now I can change the link color in one place instead of searching through the whole stylesheet.

### Example 3: Simplifying Selectors

**Before:**

```css
#header nav ul li a.current {
  font-weight: bold !important;
}
```

**After:**

```css
.site-nav__link[aria-current="page"] {
  font-weight: bold;
  text-decoration: underline;
}
```

The second version is easier for me to understand and doesn't need `!important`. It also uses the current-page attribute to identify the active navigation link.

These are examples of approaches I wanted to avoid, rather than changes made to an older website.

## 7. Browser Testing

I tested my website locally in Chrome using Live Server and Chrome DevTools.

At 375px, the homepage navigation wrapped to fit the screen, the topic cards stacked vertically, and I didn't notice any horizontal page overflow.

At 1280px, the homepage displayed four topic cards in one row, and the introductory content and diagram appeared side by side.

I also tested the navigation links and keyboard focus indicators. The links opened their destinations, and focused elements displayed visible outlines.

For print testing, I used Chrome's Print Preview. The homepage changed to a simpler layout without the navigation or main button, and the content fit on one printed page.

I documented these results in docs/TEST_CHECKLIST.md. Additional testing, including Firefox, 200% zoom, and the longer educational pages, has not been completed yet.

## 8. Connection to My Planning Package

My website is still based on the five pages from my Module 1 Planning Package:

1. Home
2. HTML Basics
3. CSS Basics
4. Responsive Design
5. Accessibility

I used my responsive wireframes to guide how the layout should change between mobile, tablet, and desktop screens.

This CSS system gives me a starting point that I can build on in the remaining modules without needing to rewrite the entire stylesheet.

## 9. AI Assistance Disclosure 

I used GitHub Copilot to help suggest ways to organize my CSS architecture, including how to separate styles into cascade layers like reset, base, layout, components, utilities, and overrides. I reviewed the suggestions and verified that the CSS worked as expected through browser testing.