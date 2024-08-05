# Transforms
* takes in one or more CSS transform functions as its values, functions take angle or number as values
* EXCEPTIONS (col colgroup and non-replaces elements ~span, b, em~)
## Two dimensional transforms
* rotate(45deg) or: -1 rad, 0.3turn
* scale(0.25, 1.5) scaleX(0.25) scaleY(1.5)
* skewX() skewY() skew() : deg, rad
* translateX/Y :px, %

## Three-dimensional transform
* rotate scale translate to work in 3D you have to use perspective()
* perspective() - sets the distance from the user to the z =0 plane
* eg. transform: perspective(100px) translateZ(30px);
* matrix() - combine all transform functions into one **rarely used**

## Benefits of transforms
* occurs during COMPOSITION : cheaper to use compared to other properties
* can be hardwawre-accelerated via a GPU

* sets the value of the perspective property. Remember, this value sets the distance from the object’s plane, so the smaller the value is, the more noticeable the perspective effect will be.
The other two sliders refer to the perspective-origin property.
* sets the origin on the vertical axis, from top to bottom, and the bottom slider sets the origin on the horizontal axis, from right to left.

# Transitions
* transition-property - This determines what CSS property will be transitioned. In this case it is the background-color.
* transition-duration - This determines the duration that the transition will occur over. In this case the color change will gradually happen over 1 second.
* transition-timing-function - This lets us change the speed of the transition over the course of its duration. Here it will ease-out, meaning the color change will be faster at the start than at the end of the transition.
* transition-delay - This determines the delay at which the transition will start. In this case, the color change starts a quarter of a second after the cursor rests on the button.

## Performance
* stacking context
* keep animations to only affecting opacity and transform

	https://web.dev/articles/animations-guide
https://web.archive.org/web/20220727225220/https://csstriggers.com/
https://www.joshwcomeau.com/animation/css-transitions/
https://dzhavat.github.io/2021/02/18/debugging-layout-repaint-issues-triggered-by-css-transition.html
