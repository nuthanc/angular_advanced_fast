# Course

* https://app.pluralsight.com/library/courses/modern-web-layout-flexbox-css-grid/table-of-contents

### A Little History

* Before FlexBox and CSS Grid, single columns
* To have multiple columns, earlier used HTML tables
* Then margin, padding, alignment and floats came into picture
* Float based layouts replaced HTML table based layouts
* Finally emergence of Flexbox and CSS grids

### Flexbox Basics

* Flexbox is all about relationship between a parent container(Flex Container) and its direct descendant child items
* The flex items flow along what is known as the Main Axis
  * Default: Left to Right
* Cross Axis runs perpendicular to the Main Axis
* **Properties on flex-container**
  * display: flex
  * inline-flex similar to inline-block to shrink wrap its contents
  * flex-direction: column, default is row
    * row-reverse: for Right to Left and similarly for column-reverse
    * column: Top to Bottom
  * flex-wrap, no-wrap is default
    * wrap for Wrapping
    * wrap-reverse: Rows flow from bottom to top
    * Wrapping changes when main-axis is changed
  * flex-flow as a shorthand for flex-direction and flex-wrap
    * flex-flow: column wrap
  * justify-content, align-items, align-content
  * gap
* **Properties on Flex-item**
  * order for changing the display order
  * flex-grow for growing the items to fill up available space
  * flex-shrink is opposite of flex-grow(How space is distributed when there is not enough space)
  * flex-basis: Sets initial space of items before extra space is distributed(Similarities between width property)
  * flex as a shorthand for flex-grow flex-shrink and flex-basis
    * flex: 0 1 auto
      * Flex do not grow to fill up available space since flex-grow is 0
  * align-self


### Controlling Display Order of Flex Items

* Naturally the Display order matches the Source Order
* If we want to change, we can place them into a new Ordinal Group
* By default, all the Flex items are placed in 1 Ordinal Group whose value is 0
* order property on Flex item for changing the display order
  * order: 1 to say 4th item places it to the very end, cause all other items have value of 0
* Ordinal placed from smallest to largest
  * When same order value, the placement depends on the Source Order of the page
* Even negative values can be used in order
* **Accessibility**
  * Only changes the Visual order and not the Source order
  * So Screen Readers read it in the same order as Source Order
  * Similarly for those who use Keyboards to navigate the web pages

### Flexibility

* flex-grow
  * Value of 1 for all items to grow available space equally
  * If for 1 item, we have like flex-grow: 4 it would take 4 times more space than others(Others have value of 1)
* flex-shrink
  * Can see this in action by setting extra large width on all flex-item(But all items would still fit in the container since they are flex items which flex(shrink))
  * Then set flex-shrink: 2 to one of the items to see the effect
  * flex-shrink: 0 would keep its original flex-item size(width that we set, while other flex-items shrink)
* flex-basis: 10em to 1st of the flex-item would have that much width whereas all other flex-items have default value of auto which shrinks them to contain their content
  * Then flex-grow: 1 to all items, we see the 1st item wider

### Alignment

* On the Container
  * justify-content, align-items, align-content
* Individual Flex Item
  * align-self
* justify-content: Align items along the Main axis
  * flex-start: Beginning of main axis(aka main start)
  * flex-end: End
  * center: Center
  * space-between: Space in between
  * space-around: Space before the first and after the last
  * If we change the main axis, the location also changes(flex-direction: column)
* align-items: Align items along the Cross axis
  * flex-start: Beginning of cross axis
  * flex-end: End
  * center: Center
  * baseline: If we have text in our flex-item, align based on the baseline of text in each item
  * stretch: Stretch the items over the entire Cross size of the flex container
  * space-between: Space in between
  * space-around: Space before the first and after the last
  * If we change the main axis, the location also changes(flex-direction: column)
* align-self: For individual items
  * flex-start to one of the item
* align-content: When wrapping to multiple lines(Aligns alongs the cross axis when there's extra space available)
  * Not applicable to single-line flex containers
  * Similar properties of justify-content
* gap property for providing gaps between items(Add in flex-container)
  * To check this, add flex: 1(which is flex-grow shorthand) to flex-item
  * gap: 2em in flex-container

### Flexbox in the Real World

* Two items side by side taking 50% width
  * Before flexbox give them width, float both and clear both
  * With Flexbox, give flex items flex: 1
* Content on one side longer than the other
  * Give min-width or something
  * With flexbox nothing required(flex: 1 initially set to flex items)
* 3 equal width columns
  * Again flex: 1
* Holy Grail Layout also super simple with Flexbox
  * The main thing we would use here is flex and flex-direction
* Also super useful when we have an unknown number of items