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
* aside>
* footer>
* form>
* header>
  main>
* nav>
* section>

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

# Keyboard Navigation

> Adding event handlers for 'click' AND 'keydown' when an element is not focusable

``` js
const buttons = document.querySelectorAll('.button');

function nameAlerter(e) {
  if (e.type === 'click' || e.key === ' ' || e.key === 'Enter') {
    alert(e.target.textContent);
  }
}

buttons.forEach(button => {
  button.addEventListener('click', nameAlerter)
  button.addEventListener('keydown', nameAlerter)
})
```
## Focus styles: outline or border of the element when it recieves focus
Never completely remove focus styles. Change them or leave them alone

## Tab order
It is by default in the same order as the order of elements listed in the HTML file
Sometimes you may find it necessary to either change the visual order of elements on a page using CSS (the float or order properties, for example), or the tab order of elements themselves using the **tabindex=0** attribute.

## Hidden content

A better solution is giving the container for the hidden content itself either the **display: none** or **visibility: hidden** CSS property when it’s hidden, and removing or overriding that property when it’s meant to be visible. This not only removes the menu items from the tab order, but it also prevents assistive technologies from announcing them.

## Meaningful Text
* Links
1. Make sure that the text content of the <a> element somehow indicates where the link redirects to and that it’s brief (around 100 characters). So avoid using phrases like “click here” or “this page”.
2. If a link would open or download a file, include text that tells the user what kind of file it is as well as the file size.
3. If a link would automatically open in a new tab or window with the target="_blank" attribute, you should indicate this to the user in some way.
   
* Forms
1. Provide meaningfull errors to users. eg. Error: JognSmith@test.com is not valid
2. Provide instuctions eg. Mult include at least one uppercase letter and one number"

* Alternative text
1. alt attrbut set to '' for decorative images


# WAI_ARIA

ARIA can only modify semantics or context of an elment.
ARIA can NOT:
* modify an element's appearance
* modify an element's behavior
* add focusability
* add keyboard event handling

no ARIA is better than bad ARIA

## 5 Rules Of Aria
1. Always use native HTML elements and attributes over ARIA
2. Never change native semantics, unless you have no other choice
3. All interanctive ARIA controls must be usable with a keyboard
4. Never use role='presentation' or 'aria-hidden='true' on focusable elements.
5. All interactive elements must have an accessible name

## The accessibility tree
- is based on the DOM and contains only the accessibility related info that will be used by assistive technologies

> ARIA modifies properties of the objects that make up the accessibility tree.
 - NAME: may be set by one or more native labels, including the text contents of an element, eg. **label** element, **alt** element
 - DESCRIPTION: what assistive tech announce in addition to its accessible name

## ARIA labels

* aria-label
> Aria-label does not have any effect on div> or a span>

Common use for aria-label can be found in the close buttons od menus or modals: "Close menu, button"

```html
<button type='button' aria-label='Close menu'>X</button>
```

Another use navigation, when you have multiples 

```html
<nav aria-label='main navigation'>...</nav>
```

* aria-labelledby concatenates string of the test contents or alt attributes of the labelling elements (ones whose id are passed in)

  eg. "Shirts, shop now"

```html
<!-- Here's the labelling element -->
<h2 id='label'>Shirts</h2>

<!-- And here's the labelled element. Note the order of the ID references passed in -->
<button type='button' id='shop-btn' aria-labelledby='label shop-btn'>Shop Now</button>
```

* aria-describedby modifies the description property in the accessibility tree

eg. " Password, edit protected, password must be at least ten characters long." 

```html
<label>Password:
  <input type='password' aria-describedby='password-requirements' />
</label>

<!-- Meaningful text + ARIA! -->
<span id='password-requirements'>Password must be at least 10 characters long.</span>
```

## Hiding content from the accessibility tree

**aria-hidden** useful if tou want to add an icon inside of another element

Eg.

```html
<!-- Example 1 -->
<button type='button'>
  <span class='material-icons'>add</span>
  Add Book
</button>

<!-- Example 2 -->
<button type='button'>
  <span class='material-icons' aria-hidden='true'>add</span>
  Add Book
</button>
```  
While both of the above examples would look visually identical, the button in Example 1 would be announced by a screen reader as, “Add add book, button”. The text content of the <span> and the text content of the button itself are concatenated as the accessible name of the button. The button in Example 2, however, hides the <span> from the accessibility tree so its text content isn’t added to the button’s accessible name, meaning a screen reader would correctly announce “Add book, button”.

> Be careful when using this attribute, though. When you give an element aria-hidden='true', all children of that element will also become hidden to the accessibility tree. Adding aria-hidden='false' to a child element won’t have any effect if one of its parents still has aria-hidden='true', either.


