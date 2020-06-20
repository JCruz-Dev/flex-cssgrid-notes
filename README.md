# Flexbox

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

# CSS Grid

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

`grid-auto-rows`: this property makes changes to grid items added dinamicly or that surpass the rows explicit defined.

`grid-auto-flow`: this property tells de browser that the grid items created implicitly will place in a certain direction column or row (default).

`grid-auto-columns`: tells the browser the width of the implicitly created columns

`Fractional units (fr)`: Represent the amaunt of space left while elements are laid out. You can use percetages, rems/ems, pixels. in any case Wesbos uses rems and fr units.

`repeat`: its a function to set the width of columns or rows without having to write the values. it takes to arguments: Number of repetitions and unit

```css
.container {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
}
```

You can even mix it with the other values

```css
.container {
    display: grid;
    grid-template-columns: 100px repeat(4, 1fr) 200px;
    grid-template-columns: 100px repeat(4, 1fr auto) 200px;
    /* This will give us 8 columns alternating the width with 1 fr and 2 fr ( 4 columns with 1 fr width and other 4 columns with 2fr width). The 4 multiplies with the 1fr and then 2fr */
    grid-template-columns: 100px repeat(4, 1fr 2fr) 200px;
}
```

## CSS Grid - Sizing

To size grid items we have to use the value `span` on the property `grid-column`. If we use width, is going to resize all grid items next to the one or column is the width applied. the same concept can be applied to rows with `grid-row` property.

`grid-column` is a shorthand for: - grid-column-start - grid-column-end

```css
.item {
    grid-column: span 2;
    grid-row: span 2;
}
```

Spread and item across the entire grid:
`grid-column: 1/-1` the `-1` indicates that will spand to the last column.

Note: This can be done in the grid-row too. Example `grid-row: 1/-1`

## CSS GRID - Auto properties & minMax

`auto-fill`: tells the browser that he decides how many items fit in a container depending on the containers width. Without too many items to take space on screen, it will create automaticly columns to use depending on the available space.

`auto-fit`: tells the browser how to resize the content depending on its width and adjusting it to the grid.

`minmax`: minimum value that the content will shrink and max value that the content will grow. This can be used with the withing the repeat funcion in css.

```css
.container {
    grid-template-columns: repeat(auto-fit, minmax(150px, 1f));
}
```

## CSS Grid - Grid template Areas

The template areas let us organize our grid items into an specific layout that we want. Distributing the items depending on the area.

```css
.container {
    display: grid;
    grid-gap: 20px;
    grid-template-columns: 1fr 500px 1fr;
    grid-template-rows: 150px 150px 150px 100px;
    grid-template-areas:
        'sidebar-1 content sidebar-2'
        'sidebar-1 content sidebar-2'
        'footer footer footer';
}
.item1 {
    grid-area: sidebar-1;
}
.item2 {
    grid-area: content;
}
.item3 {
    grid-area: sidebar-2;
}
.footer {
    grid-area: footer;
}
```

We also con apply media queries and change the template areas if we want

```css
@media screen and (min-width: 700px) {
    .container {
        grid-template-areas:
            'content content content'
            'sidebar-1 sidebar-1 sidebar-2'
            'footer footer footer';
    }
}
```

We can define columns with the `template-areas` property without having `grid-template-columns`defined

```css
.container {
    display: grid;
    grid-gap: 20px;
    /* We are defininf 8 columns and 4 rows */
    grid-template-areas:
        'A A A A B B B B '
        'A A A A B B B B '
        'A A A A B B B B '
        'A A A A B B B B ';
}
```

## CSS GRID - grid auto flow dense

When we explicitly create a grid width different sizes sometimes a grid item wont fit in the line and goes to the next row creating an space between this item and the other ones behind him.

To solves this particular scenario we can use `grid-auto-flow: dense` and the browser will check and fill the empty spaces with the grid items that actually can fit in that space.

## CSS Grid - Aligning in CSS Grid

-   justify-items (strech property is the default one)
-   align-items
-   justify-content
-   align-content
-   align-self
-   justify-self

justify is a row axis
align is a column axis

A shorthand for using justify items and align items, we can use `place-items: (justify) (align)`

```css
.container {
    display: grid;
    place-items: center center;
}
```
They do not switch like in flexbox