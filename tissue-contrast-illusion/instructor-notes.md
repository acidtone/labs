# 10 min video(?)
## Prolog
- code for creativity
## Objectives
- Centre two equally spaced, grey circles vertically in the viewport.
  1. make a grey box
      - `background: grey`
          - can't see it -> inspector -> `border: 5px solid <color>`
      - `width: 200px`
      - `height: 200px`
      - stretch:
          - viewport units
          - `rem`, `em`, `ch`
          - colour: hex, rgb, hsl
  2. make it a circle
      - `border-radius: 50%`
          - slide: `border-radius: 10px`
      - percentages
  3. centre it horizontally
      - `margin: auto`
  4. centre it vertically
      - holy grail -> optional: brief history
      - "if flexbox is intimidating, don't worry! we're just using it to tweak the behaviour of `margin: auto`"
      - container: `height: 100vh`
      - container: `display: flex`
      - item: `margin: auto`
      - Ta Da!
- Split a background into two colors.
  1. choose an element -> body
  2. Create a default black/white linear gradient
      - `background: linear-gradient(white, black)`
          - optional: reverse colours and use `to left` or `270deg` for line angle below
      - css functions -> documentation, articles, etc
  3. Set the gradient line angle to run horizontally `to right` (optional: use `90deg`)
      - `linear-gradient(90deg, white, black)`
      - default: `0deg` or `to top`
      - The illusion is actually more pronounced here before we even get to colour stops. The goal is to reproduce the Tissue Illusion but this can be a great jumping off point for other gradient exercises.
      - trivia: magic corners 
          - "The corners nearest to the starting and ending points have the same color as their respective starting or ending points." [source](https://developer.mozilla.org/en-US/docs/Web/CSS/linear-gradient#Composition_of_a_linear_gradient)
  4. Add some creative colour stops to make the gradient not a gradient.
      - `linear-gradient(90deg, white 50%, black 50%)`
      - default: `linear-gradient(90deg, white 0%, black 100%)`
          - "A color-stop's position can be explicitly defined by using a `<length>` or a `<percentage>`. If you don't specify the location of a color, it is placed halfway between the one that precedes it and the one that follows it." [source](https://developer.mozilla.org/en-US/docs/Web/CSS/linear-gradient#Customizing_Gradients)
      - other use cases
          - [Split Vertical Layout](https://codepen.io/mandymichael/pen/mNPvKo)
          - [Adjustable Thermometer](https://codepen.io/acidtone/pen/YbmvrX)
- Create a semi-transparent image.
  - Decision: Do we use an html or css image?
    - answer: both!
  - presentation method: css image
    1. add a `div` tag to the html just before the `</body>` tag (or at the bottom of the html panel if using a sandbox service like Codepen)
        - `<div></div>`
    2. make the `div` element the same size as the gradient from the previous step (most likely the size of viewport)
        - `width: 100vw`
        - `height: 100vh`
    3. add a background image that covers the entire background of the `div` element
        - `background-image: url([lorem picsum])`
        - `background-size: cover` 
        - `background-position: center` (optional)
    4. set the `div` opacity to 0.5
        - `opacity: 0.5`
  - content method: html image
    1. add an `img` tag to the html just before the `</body>` tag (or at the bottom of the html panel if using a sandbox service like Codepen)
        - `<img src="[lorem picsum]">`
    2. make the `img` element the same size as the gradient from the previous step (most likely the size of viewport)
        - `width: 100vw`
        - `height: 100vh`
    3. correct for aspect-ratio
        - `object-fit: cover`
    4. set the `div` opacity to 0.5
        - `opacity: 0.5`
- Overlap an image on top of another element
  - classic method: absolute positioning
    1. declare the image as absolutely positioned
        - `position: absolute`
    2. position image to the top left corner of the `body`
        - `top: 0`
        - `left: 0`
  - fancy-pants method: css grid
    1. wrap the two circles in a `div` tag
    2. place image as a sibling to the new div element
    3. make the parent to the `div` and image a grid
        - `display: grid`
    4. assign `div` and image to the same grid cells 
        - `grid-column: 1 / -1`
        - `grid-row: 1 / -1`

## Stretch Topics
- units
  - `rem`, `em`, `ch`
  - `vmin`, `vmax`
- resets
  - `margin: 0`
- responsive considerations
  - `min-width`
  - `@media (orientation: portrait)`
    - `flex-direction`
    - gradient line direction
- alternative solutions
  - Tissue Effect with `img` element
    - aspect-ratio considerations
    - `object-fit`
  - Tissue Effect with `grid` overlap