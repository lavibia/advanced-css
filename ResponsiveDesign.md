# What is Responsive DEsign and why it's importants

* lower target of screen size : 320px
* set up a max-width for all of your content and then center that on the page for super wide resolutions

# Natural Responsiveness
* use techniques that are naturally flexible: flexbox, grid
* the **viewpoint** meta tag (we eant our websites to be viewed at the actual non-zoomed screen resolution
  ```
  <meta name="viewport" content="width=device-width, initial-scale=1">
  ```
* avoid fixed width or height use **max-width** or **min-height** instead
  > Avoid heights altogether (use it for headers and footers) use margin and padding instead
  > Fixed widths are appropriate when: small widths (icons, sidebar)
* use flex and grid: flex-wrap / minmax, auto-fill
  > minmax() in auto-fill repeating tracks
> In this example I am creating a grid that contains as many 200 pixel column tracks as will fit into the container with the remaining space shared equally between the columns. In the minmax() function the first value is the minimum size I want my tracks to be, the second is the maximum. By using 1fr as the maximum value the space is equally distributed.
```
.wrapper {
    display: grid;
    grid-gap: 10px;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr) ) ;
    background-color: #fff;
    color: #444;
  }
```
# Responsive Images
* give width and set height to auto to preserv the img ratio while shrinking
* background-size, background-position and object-fit
  >background-size and position work on elements with a background image and not with img tags
  >background-position: center will 'cut' the image on the center
  >background-size: cover will resize the image so that it is completely filling its container whil cropping as little as possible
  >object-fit is meant for img tags. Specify a width and a height for the elem. and set object-fit to cover or contain or fill
*  instead of just trusting object-fit to keep the subject of a photograph in a frame, you could present a cropped version of it on smaller screens. There are two ways of achieving this, but the most flexible is using the <picture> tag

https://css-tricks.com/a-guide-to-the-responsive-images-syntax-in-html/

# Media Queries

* limit media queries
* common breakpoints max-width:500px / 1000px / min-width 2000px
* zooming will change the effective resolution of that page

# Print styles

```
@media print{
/* print styles go here! styles for your website when it is sent to your printer or viewed in print-view mode (black/white, hide buttons, nav etc)

}


  >

