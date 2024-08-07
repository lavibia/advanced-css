# What is it and why it matters?
Types:
* auditory
* physical/motor
* cognitive
* visual

PERMANENT/TEMPORARY
**old people**
**Situational limitations**
* using a phone outside on a bright day
* slow internet
* expensive bandwidth

LAWS REQUIRE ACCESSIBILITY

# The Web Content Accessibility Guidelines (WCAG)
* create a shared standard of web accessibility

## The four priciples
1. Perceivable: eg. light text on alight background could be difficult for some users wwith visual impairment to perceive
2. Operable: eg. a nav bar with drop-down menus that only expand when a mouse cursor hovers over them, would not be operable by keyboard users giving those menu items focus
3. Understandable: eg. if a user tried submitting a form and received an error such as "Error 113: Bad Data", they would not be able ti understand what the error actually means or how to fix whaterver caused the error
4. Robust: accessible by current assistive technlogies and other user agents and must remain accessible as those technologies advance

## Conformance levels
* Level A (essential support): minimum level of conformance for the WCAG
* Level AA (ideal support): many org. strive for it
* Level AAA (specialized support): isn't recommended for entire sites to meet in full, as some content may make it impossible to meet this conformance level.

# CHECKLIST
https://webaim.org/standards/wcag/checklist

# Semantic HTML
Headings are the <h1> through <h6> elements, and like the name implies, these elements act as headings to sections of a page. Landmarks, on the other hand, are HTML elements that act as regions of a page.

There are seven native HTML elements that define these landmark regions:
* <aside>
* <footer>
* <form>
* <header>
* <main>
* <nav>
* <section>

https://www.w3.org/WAI/ARIA/apg/patterns/landmarks/examples/HTML5.html

# Accessible Colors
A contrast ratio is the difference in brightness between two colors expressed as a ratio. White text on a white background would have lowest ratio (1:1), while black text on a white background would have the highest (21:1). Contrast ratios refer to both normal text as well as images of text.

There are two different conformance levels for contrast ratios, both of which have rules for normal text and large text. Normal text is defined as text with a font size that’s less than 18 points/24px (or less than 14 points/18.66px for bold text), and large text is defined as text with a font size that is at least 18 points/24px (or at least 14 points/18.66px for bold text).

* Level AA (minimum) requires a contrast ratio of at least 4.5:1 for normal text and 3:1 for large text.
* Level AAA (enhanced) requires a contrast ratio of at least 7:1 for normal text and 4.5:1 for large text.

Both conformance levels have exceptions that don’t need to follow the contrast ratio rules:
  * Incidental text, such as text that just happens to be within an image that has other significant visual content, or text that is purely decorative.
  * Text that is part of an inactive or disabled user interface component, such as a button that is disabled and has a lowered opacity.
  * Text that is part of a logo or brand name.

 Checking:
 In Chrome, click the “element picker” tool in the Elements tab, then hover over an element on the web page. This displays a tooltip showing the contrast ratio under the Accessibility section. You can also view the contrast ratio by selecting an element with text in the Elements tab and clicking on the color picker tool for the “color” property in the Styles pane.
 

# DARK MODE TUTORIAL
https://css-tricks.com/a-complete-guide-to-dark-mode-on-the-web/

