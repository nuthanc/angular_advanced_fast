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

### Flex Shorthand

* flex-flow as a shorthand for flex-direction and flex-wrap
* flex as a shorthand for flex-grow flex-shrink and flex-basis

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

### Flexbox vs Grid

* Flexbox controls how items flow in one dimension
  * Great at handling alignment, distribution and order of content and space
* Grid controls how items flow in two dimensions
  * Relies on Defined Gridlines

### Grid Layout Basics

* CSS Grid, like Flexbox is all about relationship between a parent container(Grid Container or Grid) and its direct descendant child items
* Grid is made out of 2 set of lines, known as Grid lines
  * One line for Columns of the Grid => Column Axis
  * One line for Rows of the Grid => Rox Axis
* Together the above make the Grid Tracks(Grid Column or Grid Row)
  * Created by space between 2 consecutive row lines or column lines and are given a size which controls how tall a row can be or how wide a column can be
* Grid cell: Intersection of Grid row and Grid Columns that we can place items into
* Grid Area: Any portion of the Grid that is contained by 4 Grid lines

### Setting up a Grid

* **Properties on Grid Container**
  * display of grid to the grid-container
    * inline-grid to shrink wrap the grid items(Only as much space as the item requires)
  * grid-template-columns
    * width(Give as many as for the number of columns)
    * E.g: grid-template-columns: 6em 6em 6em 6em; (This creates 4 columns, if there are 8 cols, 4 in each row)
      * This does not look grid like
      * This is because the Grid does not actually control the size of the items
      * It simply creates virtual areas for the grid items to live
      * For placing the Grid items, we use grid-column-start, grid-column-end, grid-row-start, grid-row-end
  * grid-template-rows
    * height(Give as many as for the number of rows)
    * E.g: grid-template-rows: 6em 6em; (This creates 2 rows)
  * gap property for providing gaps between our columns and rows
  * row-gap for row gaps
  * column-gap for column gaps
  * grid-auto-flow
* **Properties on Grid items**
  * grid-column-start: 1
    * This is the 1st vertical grid line
  * grid-column-end: 2
    * It should end at 2
  * grid-row-start: 1
  * grid-row-end: 3
* If we want to place the item in the 2nd column, then
  * grid-column-start: 2 and grid-column-end: 3
* If we want it to span for 2 columns
  * grid-column-start: 1 and grid-column-end: 3
* If we want to stretch it for the whole row
  * grid-column-start: 2 and grid-column-end: 4 and grid-row-start: 1 and grid-row-end: 3
* order property to change the order
* span keyword for items spanning across grid lines

### Auto Grid Features

* We don't want to manually define rows, columns and their heights(Using grid-column-start, grid-column-end etc) and placing them into these
* We want automatic placement and when we don't define the positions, the Grid does automatic placement
  * This is because of default flow horizontally from left to right along the row axis and then top to bottom
  * grid-auto-flow: row(default)
  * grid-auto-flow: column -> Top to bottom and then left to right
* We can also mix auto placed items with explicitly positioned ones
  * grid-auto-flow: column on the grid container and grid-column-start: 2 and grid-column-end: 4 and grid-row-start: 2 and grid-row-end: 2 on 2nd item
  * This will force all other auto placed items to wrap around it accordingly
* order: 1 on one of the items will place this item after all other non-order items
* With auto grid, we also have a notion of implicit grid lines
  * Let's say we add an 8th and 9th item, even though we have 2 rows and 4 columns, it will add the 9th item in the 3rd row
  * This is because a new implicit grid track has been created below these rows

### Grid Shorthand

* grid as a shorthand for grid-template-rows and grid-template-columns
  * grid: row row / column column;
* grid-row and grid-column as a shorthand for grid-row-start, grid-row-end and grid-column-start, grid-column-end respectively
  * grid-row: row-start / row-end;
  * grid-column: column-start / column-end;
* grid-area which will accept all 4 of them
  * grid-area: row-start / column-start / row-end/ column-end;
* span keyword for items spanning across grid lines
  * We still need to say what grid line to start on
  * grid-column: 2 / span 2; (Which is equivalent to grid-column: 2 / 4)
* repeat keyword for repeated patterns
  * grid-template-columns: repeat(4, 6em);
  * grid-template-rows: repeat(2, 6em); equivalent to grid-template-rows: 6em 6em;

### Custom Named Grid Lines

* Name our Grid lines instead of counting to get the item
* We do it in grid-template-columns or grid-template-rows using square brackets[] and name within it
* E.g: grid-template-columns: [name1] [name2]
* Check pluralsight note

### Custom Named Grid Areas

* Grid Area: Any area on a grid contained by 4 Grid lines
  * grid-area: title on the grid item
  * grid-area: thumbnail on thumbnail item
* grid-template-areas
```css
.media-container {
grid: auto auto/ 8em 1fr;
grid-template-areas : 
  "title title"
  "thumbnail content";
gap: 1em;
}

/* If we need Complex Grid spacing, we can create empty rows and empty columns */
.media-container {
grid: auto 1em auto/ 8em 1.5em 1fr;
grid-template-areas : 
  "title title title"
  ". . ." /* Period for empty */
  "thumbnail . content";
}
```
### Auto, fr & Overlapping/Layering

* auto for dynamic content
  * The row or column will size itself based on that content
* fr used for sizing a grid tracked based as a fraction of available space
  * E.g: grid-template-columns: 6em 1fr;
    * 1st column 6em and 2nd column all of available space
* For Overlapping 
```css
/* Total 8 items with 2 rows and 4 columns */
.grid-item-02 {
  grid-area: 1 / 1 / 3 / 4;
}
```
* Elements nested within another container to be part of the Grid
  * display: contents;
  * Adding display: contents to the body container will make it appear as if it is completely invisible from the layout engine in our browser
  * This allows the children within this container to be placed on the Grid