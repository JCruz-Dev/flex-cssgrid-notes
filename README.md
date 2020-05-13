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
