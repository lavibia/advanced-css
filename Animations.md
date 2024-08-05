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

# Keyframes

## Animations vs transitions
* Transitions were designed to animate an element from one state to another. Animations were design with the purpose of explixitly enabling loops.
* Transitions need a trigger (hover, focus, adding/removing a class via JS). Animations do not need such a trigger. Once you have your elements in place and CSS defined, an animation will start running if that's what you told it to do.
* Transitions are not as flexible as using animations. When you define a transition, imagine you are sending that elem on a journey in a straight line from point A to point B
* **if you need to change the opacity of an element when it is active then an animation would be overkill, but if you need to carry out something more complicated, animations will provide you with the tools you need.**
  
## Animation properties
* An animation-duration of two seconds. This means that it will take two seconds for the #ball element to complete one animation cycle.

* Defined the animation-name to be “change-color” which is essential for the @keyframes section coming up next. This is just a custom name that is not a particular CSS value. We could have called it “pineapples” if we so wished, but for our purposes “change-color” suits us well.

* Set the animation-iteration-count to infinite, which means this animation will run forever. You could set this to 1, 2, or as many iterations as you wish.

* Set the animation-direction to alternate. This property decides if our animation should alternate direction on the completion of one cycle, or reset to the start point and repeat itself. Here it means that the #ball will smoothly change back to its original color instead of “jumping” straight back to red.
  
```
@keyframes change-color {
  from {
    background-color: red;
  }

  to {
    background-color: green;
  }
} 
```

It’s important to know that keyframes use a percentage to indicate the times for an animation to take place and that the from and to statements are actually aliases for 0% and 100%, respectively. You can read from/0% as meaning ‘at zero seconds’ and to/100% as ‘at 2 seconds’ according to our animation-duration in our example from above. There is no hard and fast rule on whether or not you should use from/to or 0%/100%. Just pick a style and be consistent with it.


*
