
# Module 2 - Browser Testing Checklist

**Project:** Beginner's Guide to Web Design  
**Course:** GIT 414  
**Testing Date:** November 10, 2026

## About This Checklist

I made this checklist to test my website at different screen sizes and check that the navigation, CSS, and print styles work correctly. I'm using Chrome DevTools and Live Server in VS Code to test the website before submitting my Module 2 assignment.

I'll mark each test as complete after checking it. Anything I haven't tested yet will stay unchecked.

## 1. Responsive Layout Testing

I'm using Chrome DevTools to see how the website responds to different screen widths.

- [ ] **320px:** Check the Home, HTML Basics, and Responsive Design pages. There should be no horizontal scrolling across the entire page. Code examples can scroll inside their own boxes.
- [x] **375px:** The homepage navigation wraps to fit the screen, and the topic cards stack into one column. I didn't notice any horizontal page overflow.
- [ ] **768px:** Check that the topic cards and example cards display in two columns.
- [x] **1280px:** The homepage displays four topic cards in one row. The introductory content and webpage diagram appear side by side, and the layout is centered.
- [ ] **200% zoom:** Make sure text, navigation, and code examples remain readable without overlapping or getting cut off.

## 2. Keyboard and Interaction Testing

I'm checking that the website can be navigated with a keyboard and that interactive elements have visible states.

- [ ] Press Tab to see if the "Skip to main content" link appears.
- [ ] Press Enter on the skip link and make sure it moves to the main content.
- [x] Use Tab to move through the navigation links. The focused elements have visible outlines.
- [x] Check that the current page is highlighted in the navigation. The Home link is visibly highlighted on the homepage.
- [ ] Hover over navigation links and buttons to see if their appearance changes.
- [ ] Press a button link and check that its background color changes while it's being pressed.
- [ ] Use Shift+Tab to verify reverse keyboard navigation.

## 3. Browser Testing

I'll check the website in Chrome and Firefox to make sure the layout and navigation behave consistently.

- [x] **Chrome:** Opened the homepage through Live Server and confirmed that the website displays correctly. I also tested the navigation links and confirmed that they open their destinations.
- [ ] **Chrome:** Inspect all five pages for layout problems, missing content, and code example overflow.
- [ ] **Firefox:** Open all five pages and check that the layouts, navigation, and code examples work.

## 4. Print Testing

I'm using Chrome's Print Preview feature to check how the website would look when printed or saved as a PDF.

- [x] **Homepage:** Opened Print Preview and confirmed that the page uses a simplified layout. The navigation and main button are hidden, the content is readable, and the four topic cards stack vertically.
- [ ] **HTML Basics:** Check that navigation is hidden and the lesson content and code examples are readable.
- [ ] **Responsive Design:** Check that the diagrams and code examples remain readable without being cut off.
- [x] **Homepage print colors and controls:** The print preview shows a white background and removes unnecessary interactive elements.
- [ ] **Lesson page print colors and controls:** Verify that the same print behavior works on the educational pages.

## 5. Final Website Checks

Before submitting, I'll check the following:

- [ ] All five pages have their own page titles and meta descriptions.
- [x] The navigation links I tested opened their correct destinations.
- [ ] All links between lessons work correctly.
- [ ] Any raster images used on the website load correctly and meet the 300 KB size limit.
- [x] The homepage displays without obvious layout problems at the 375px and 1280px widths I tested.
- [ ] All five pages have been checked for missing sections, broken layouts, or overflowing content.

## 6. My Testing Results

### Browsers Tested

**Chrome:** Tested using Live Server at `127.0.0.1:5500`.  
**Chrome version:** Not recorded yet.  
**Firefox:** Not tested yet.  
**Firefox version:** Not recorded yet.

### Mobile Layout

**Viewport width:** 375px

I used Chrome DevTools to check the mobile homepage. The navigation links wrapped onto additional rows instead of going off the screen. The heading and paragraph adjusted to fit the narrow layout, and the topic cards stacked vertically.

I didn't notice any horizontal scrolling across the page.

**Result:** Passed for the homepage at 375px.

### Desktop Layout

**Viewport width:** 1280px

I tested the homepage at 1280px using Chrome DevTools. The navigation displayed horizontally, and the introductory content and webpage diagram appeared next to each other.

The four topic cards also appeared in one row, matching the wide layout from my planning package. I didn't notice any overlapping content or obvious layout problems.

**Result:** Passed for the homepage at 1280px.

### Navigation and Keyboard Accessibility

I clicked the website's navigation links and confirmed that they opened the linked pages.

I also used the Tab key to move through the navigation. The focused elements displayed a visible outline, making it easier to see which link was selected.

The Home link was also highlighted while I was on the homepage.

I still need to test the skip link, reverse keyboard navigation, and additional hover and active states.

**Result:** Basic navigation and visible keyboard focus passed.

### CSS Architecture Verification

While inspecting the website in Chrome DevTools, I could see that the stylesheet was loading correctly.

The Styles panel showed the `reset` and `base` cascade layers, along with custom properties such as `var(--font-body)`, `var(--color-text)`, and `var(--color-background)`.

This helped confirm that my CSS architecture and reusable design tokens were being applied.

**Result:** Layered CSS and custom-property usage confirmed.

### Print Preview

I opened Chrome's Print Preview on the homepage using Command + P.

The preview showed a simplified version of the website with a white background. The navigation and main button were removed, but the educational content and diagram remained visible.

The topic cards appeared in a single column, and the homepage fit onto one printed page.

I still need to check how the longer educational pages print, especially pages containing code examples.

**Result:** Homepage print preview passed.

### Problems I Found

So far, I haven't noticed any major problems with the homepage at the screen widths I tested.

I still need to finish testing the remaining pages and interaction states before confirming that everything works across the entire website.

### Changes I Made

No CSS changes were needed based on the tests completed so far.

The homepage's mobile and desktop layouts, navigation, visible focus indicators, and print styles behaved as expected.

### Screenshots

Screenshots captured during testing:

- Homepage displayed through Live Server in Chrome.
- Homepage at 375px in Chrome DevTools.
- Homepage at 1280px in Chrome DevTools.
- Homepage in Chrome Print Preview.

These screenshots can be included as supporting evidence if needed.

## 7. Final Review

- [ ] I completed all planned browser and responsive testing.
- [x] I recorded the testing results completed so far.
- [x] I documented that no major homepage issues were found during the completed checks.
- [ ] I verified the remaining pages and interaction states.
- [ ] I confirmed that my CSS files, architecture notes, and testing documentation are ready to submit.

## Current Testing Summary

My initial browser testing shows that the CSS architecture is working correctly on the homepage in Chrome. The responsive layouts, navigation, focus indicators, and print presentation behaved as expected in the tests I completed.

I still need to finish the 320px, 768px, 200% zoom, Firefox, skip-link, and lesson-page print checks before marking the full testing process complete.
