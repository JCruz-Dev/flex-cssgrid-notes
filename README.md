# flex-cssgrid-notes

## Flexbox

Is a new layout model that allows aligning in a horizontal and vertical way the elements and this elements can compress and expand. To be functional, it needs a father container called flex container and children called as items

Flexbox has a fundamental principal of two edges. They are main axis and cross axis.

## Flex container

Have two properties that are inline-flex | Flex
the inline flex property makes the element inline (adjusts to its content)

### Flex direction

Adjusts the direction in which the elements are been shown.There is an main axis and cross axis changes depending on the flex direction property.

`Flex direction: row (default property without indicating it)`

-   Main axis (default): from left to right
-   cross axis (default): from top to bottom

`flex direction: column`

-   Main axis: from top to bottom
-   Cross axis: from left to right

`flex direction: row-reverse`

-   Main axis: from right to left
-   Cross axis: from bottom to top

### Flex Wrap

The childrens are going to align in one line or more lines.

`Flex-wrap: nowrap (default behavior)` - If it is not going to contain more lines.

`flex-wrap: wrap` - if is is going to have more lines.

`flex-wrap: wrap-reverse` - This property modifies the cross axis direction from bottom to top.

### Order

Allows you to order the flex items. The default order is 0
You can use positive values from 1 and negative ones from -1

## Justify content

This property by default align the items in the main axis direction (left to right).

By default the items are aligned at the flex start.

-   Space between: Space the items between each one of them.
-   Space around: Space the items between each of them and taking into account the left and right edges
-   Space evenly: Space the items with a equal spacing between items.

### Align items

This property by default align items in the cross axis direction (Top to bottom) and has a property set called `strech`

`baseline` is for text or items of a flex container that aligns the vertical height

### Align Content

Manages the extra spacing in the cross axis (default is top to bottom). Only works when we have multiple lines of code. it needs a container to work.

### Align Self

it applies to a individual flex item.

### Flex

Its a shorthand for Flex grow, flex shrink, flex basis.

-   Flex grow: Tells to he flex item to take all the space available to grow.
-   Flex basis: Determines how high or width should have the flex items. The default value is 0
-   Flex-shrink`: Determines how to manage the short space between the elements. The default value is 1

```css
flex: 1 (flex-grow) 1 (flex-shrink) 400px (flex-basis);
```

---

### CSS Grid

Is a Layout system for CSS that can handle columns and rows (2 dimensional).

When display grid is declared in our css every item inside that grid container transforms into a grid item.

`grid-template-colums` : defines how many columns to display the content and the rows are automaticly created (implicitly created by the browser)

`grid-gap`: defines space between the grid items in the column and row side

Defining your columns in the grid-template columns property you can have a value `auto` where the grid item takes the available space between the other columns properties values written

```css
.container {
    display: grid;
    grid-template-columns: 100px auto 200px 50px;
}
```
