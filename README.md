# CSS Grid
A lightweight layout library for building great responsive mobile first layouts that work everywhere.

> [!NOTE]
> Built with CSS Grid and Flexbox, it leverages custom html data attributes to help namespace the layout based CSS.

> [!TIP]
> View the [demo.html](https://html-preview.github.io/?url=https://github.com/caitken-com/css-grid/blob/main/demo.html) to see examples.

1. [Usage](#usage)
2. [Grid layout](#grid-layout)
   - [Implicit Columns](#implicit-columns)
   - [Explicit Columns](#explicit-columns)
   - [Implicit rows](#implicit-rows)
   - [Explicit rows](#explicit-rows)

3. [Responsive breakpoints](#responsive-breakpoints)
   - [Implicit columns](#responsive-implicit-columns)
   - [Explicit columns](#responsive-explicit-columns)
   - [Implicit rows](#responsive-implicit-rows)
   - [Explicit rows](#responsive-explicit-rows)
   - [Apply grid at breakpoint](#apply-grid-at-breakpoint)
4. [Gap](#gap)
5. [Aligning elements](#aligning-grid-elements)
   - [Auto matching grid heights](#auto-matching-heights)
   - [Vertically top align columns](#vertically-top-align-columns)
   - [Vertically center columns](#vertically-center-columns)
   - [Vertically bottom align columns](#vertically-bottom-align-columns)
   - [Flex align center](#flexbox-alignment-center)
   - [Flex align around](#flexbox-alignment-around)
   - [Flex align between](#flexbox-alignment-between)
   - [Flex align evenly](#flexbox-alignment-evenly)
   - [Flex align start](#flexbox-alignment-start)
   - [Flex align end](#flexbox-alignment-end)
   - [Vertical and horizontal column centering](#vertical-and-horizontal-column-centering)
6. [Offset grid elements](#offset-grid-elements)
7. [Ordering grid elements](#ordering-grid-elements)
8. [Flex layout, Fit & Fill](#flex-fit--fill)
9. [Visibility utilities](#visibility-utilities)
10. [Text alignment](#text-alignment)
11. [Float utilities](#float-utilities)
12. [Container](#container)
13. [Aspect ratio](#aspect-ratio)

## Usage

```html
<link href="https://cdn.statically.io/gh/caitken-com/css-grid/main/grid.css" rel="stylesheet" />
```

## Grid Layout

The grid can be implicit or explicit 12 columns and rows.

### Implicit Columns

Implicit uniform columns can define their values at the parent grid element using `grid-cols-?`. There is no need for wrapper elements around each row, see `grid-cols-2` example below.

```html
<div data-layout="grid-cols-5">
  <div>5</div>
  <div>5</div>
  <div>5</div>
  <div>5</div>
  <div>5</div>
</div>
```

```html
<div data-layout="grid-cols-2">
  <div>2</div>
  <div>2</div>
  <div>2</div>
  <div>2</div>
</div>
```

### Explicit Columns

Columns that are not uniform can define their column span value directly on the column element using `cols-?`. Multiple rows are achieved with filling columns according to the 12 column layout.

```html
<div data-layout="grid-cols">
  <div data-layout="cols-1">1</div>
  <div data-layout="cols-11">11</div>

  <div data-layout="cols-2">2</div>
  <div data-layout="cols-10">10</div>

  <div data-layout="cols-3">3</div>
  <div data-layout="cols-9">9</div>

  <div data-layout="cols-4">4</div>
  <div data-layout="cols-8">8</div>
</div>
```

### Implicit rows

Implicit uniform rows can define their values at the parent grid element using `grid-rows-X`

```html
<div data-layout="grid-rows-3" style="height: 350px;">
  <div>3</div>
  <div>3</div>
  <div>3</div>
</div>
```

### Explicit rows

Rows that are not uniform can define their row span value directly on the element using `rows-X`

```html
<div data-layout="grid-rows" style="height: 350px;">
  <div data-layout="rows-2">2</div>
  <div data-layout="rows-4">4</div>
  <div data-layout="rows-6">6</div>
</div>
```

## Responsive breakpoints

Breakpoints attributes can be stacked.

| Attribute | Screen size | Device | Behavior |
| --- | --- | --- | --- |
| `grid-cols`<br>`grid-rows`<br>`cols-1` to `cols-12`<br>`rows-1` to `rows-12` | Extra small or any | Phones | Always display grid columns.<br>Always display grid rows.<br>Always column width.<br>Always row height. |
| `sm:grid-cols`<br>`sm:grid-rows`<br>`sm:cols-1` to `sm:cols-12`<br>`sm:rows-1` to `sm:rows-12` | Small devices (48em) | Phones / Tablets | Display grid columns at breakpoint.<br>Display grid rows at breakpoint.<br>100% width to start, column width at breakpoint.<br>100% height to start, row height at breakpoint. |
| `md:grid-cols`<br>`md:grid-rows`<br>`md:cols-1` to `md:cols-12`<br>`md:rows-1` to `md:rows-12` | Medium devices (64em) | Tablets / Laptops | Display grid columns at breakpoint.<br>Display grid rows at breakpoint.<br>100% width to start, column width at breakpoint.<br>100% height to start, row height at breakpoint. |
| `lg:grid-cols`<br>`lg:grid-rows`<br>`lg:cols-1` to `lg:cols-12`<br>`lg:rows-1` to `lg:rows-12` | Large devices (75em) | Tablets / Laptops | Display grid columns at breakpoint.<br>Display grid rows at breakpoint.<br>100% width to start, column width at breakpoint.<br>100% height to start, row height at breakpoint. |
| `xl:grid-cols`<br>`xl:grid-rows`<br>`xl:cols-1` to `xl:cols-12`<br>`xl:rows-1` to `xl:rows-12` | Extra large devices (86em) | Hi-res Laptop / Desktop | Display grid columns at breakpoint.<br>Display grid rows at breakpoint.<br>100% width to start, column width at breakpoint.<br>100% height to start, row height at breakpoint. |

### Responsive implicit columns

```html
<div data-layout="md:grid-cols-2 lg:grid-cols-6">
  <div>md:2 lg:6</div>
  <div>md:2 lg:6</div>
  <div>md:2 lg:6</div>
  <div>md:2 lg:6</div>
  <div>md:2 lg:6</div>
  <div>md:2 lg:6</div>
</div>
```

### Responsive explicit columns

```html
<div data-layout="md:grid-cols">
  <div data-layout="md:cols-3 lg:cols-8">md:3 lg:8</div>
  <div data-layout="md:cols-3 lg:cols-4">md:3 lg:4</div>
  <div data-layout="md:cols-3 lg:cols-4">md:3 lg:4</div>
  <div data-layout="md:cols-3 lg:cols-8">md:3 lg:8</div>
</div>
```

### Responsive implicit rows

```html
<div data-layout="grid-rows-2 lg:grid-rows-3" style="height: 350px;">
  <div>*:2 lg:3</div>
  <div>*:2 lg:3</div>
  <div data-layout="hide lg:show">*:hide lg:show</div>
</div>
```

### Responsive explicit rows

```html
<div data-layout="grid-rows" style="height: 350px;">
  <div data-layout="rows-2 lg:rows-4">*:2 lg:4</div>
  <div data-layout="rows-4">*:4</div>
  <div data-layout="rows-4 lg:rows-2">*:4 lg:2</div>
</div>
```

### Apply grid at breakpoint

`grid-cols`, `grid-rows` is applied at breakpoint, otherwise `display: block`.

```html
<div data-layout="grid-cols-2">

  <div data-layout="lg:grid-cols-2" style="height: 350px;">
    <div>lg:cols-2</div>
    <div>lg:cols-2</div>
  </div>

  <div data-layout="lg:grid-rows-2" style="height: 350px;">
    <div>lg:rows-2</div>
    <div>lg:rows-2</div>
  </div>

</div>
```

## Gap

- `cols-gap-0`, `sm:cols-gap-0`, `md:cols-gap-0`, `lg:cols-gap-0`, `xl:cols-gap-0`
- `cols-gap-1`, `sm:cols-gap-1`, `md:cols-gap-1`, `lg:cols-gap-1`, `xl:cols-gap-1`
- `cols-gap-2`, `sm:cols-gap-2`, `md:cols-gap-2`, `lg:cols-gap-2`, `xl:cols-gap-2`
- `cols-gap-3`, `sm:cols-gap-3`, `md:cols-gap-3`, `lg:cols-gap-3`, `xl:cols-gap-3`
- `cols-gap-4`, `sm:cols-gap-4`, `md:cols-gap-4`, `lg:cols-gap-4`, `xl:cols-gap-4`
- `cols-gap-5`, `sm:cols-gap-5`, `md:cols-gap-5`, `lg:cols-gap-5`, `xl:cols-gap-5`

---

- `rows-gap-0`, `sm:rows-gap-0`, `md:rows-gap-0`, `lg:rows-gap-0`, `xl:rows-gap-0`
- `rows-gap-1`, `sm:rows-gap-1`, `md:rows-gap-1`, `lg:rows-gap-1`, `xl:rows-gap-1`
- `rows-gap-2`, `sm:rows-gap-2`, `md:rows-gap-2`, `lg:rows-gap-2`, `xl:rows-gap-2`
- `rows-gap-3`, `sm:rows-gap-3`, `md:rows-gap-3`, `lg:rows-gap-3`, `xl:rows-gap-3`
- `rows-gap-4`, `sm:rows-gap-4`, `md:rows-gap-4`, `lg:rows-gap-4`, `xl:rows-gap-4`
- `rows-gap-5`, `sm:rows-gap-5`, `md:rows-gap-5`, `lg:rows-gap-5`, `xl:rows-gap-5`

```html
<div data-layout="grid-cols-3 sm:cols-gap-1 md:cols-gap-2 lg:cols-gap-3 xl:cols-gap-5 rows-gap-1 sm:rows-gap-2 md:rows-gap-3 lg:rows-gap-5 xl:rows-gap-5">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
</div>
```


## Aligning grid elements

- `cols-top`, `sm:cols-top`, `md:cols-top`, `lg:cols-top`, `xl:cols-top`
- `cols-middle`, `sm:cols-middle`, `md:cols-middle`, `lg:cols-middle`, `xl:cols-middle`
- `cols-bottom`, `sm:cols-bottom`, `md:cols-bottom`, `lg:cols-bottom`, `xl:cols-bottom`

### Auto matching heights

Grid columns automatically match column heights.

```html
<div data-layout="grid-cols-4">
  <div>A</div>
  <div>B</div>
  <div>C</div>
  <div>Ipsum dolor amet alcatra landjaeger. Ipsum dolor amet alcatra landjaeger.</div>
</div>
```

### Vertically top align columns

```html
<div data-layout="grid-cols-4 cols-top">
  <div>A</div>
  <div>B</div>
  <div>C</div>
  <div>Ipsum dolor amet alcatra landjaeger. Ipsum dolor amet alcatra landjaeger.</div>
</div>
```


### Vertically center columns

```html
<div data-layout="grid-cols-4 cols-middle">
  <div>A</div>
  <div>B</div>
  <div>C</div>
  <div>Ipsum dolor amet alcatra landjaeger. Ipsum dolor amet alcatra landjaeger.</div>
</div>
```

### Vertically bottom align columns

```html
<div data-layout="grid-cols-4 cols-bottom">
  <div>A</div>
  <div>B</div>
  <div>C</div>
  <div>Ipsum dolor amet alcatra landjaeger. Ipsum dolor amet alcatra landjaeger.</div>
</div>
```

### Flexbox alignment center

- `flex-cols-center`, `sm:flex-cols-center`, `md:flex-cols-center`, `lg:flex-cols-center`, `xl:flex-cols-center`
- `flex-rows-center`, `sm:flex-rows-center`, `md:flex-rows-center`, `lg:flex-rows-center`, `xl:flex-rows-center`

```html
<div data-layout="flex-cols-center">
  <div data-layout="cols-2">A</div>
  <div data-layout="cols-2">B</div>
  <div data-layout="cols-2">C</div>
</div>
```

```html
<div data-layout="flex-rows-center" style="height: 350px;">
  <div>A</div>
  <div>B</div>
  <div>C</div>
</div>
```

### Flexbox alignment around

- `flex-cols-around`, `sm:flex-cols-around`, `md:flex-cols-around`, `lg:flex-cols-around`, `xl:flex-cols-around`
- `flex-rows-around`, `sm:flex-rows-around`, `md:flex-rows-around`, `lg:flex-rows-around`, `xl:flex-rows-around`

```html
<div data-layout="flex-cols-around">
  <div data-layout="cols-2">A</div>
  <div data-layout="cols-2">B</div>
  <div data-layout="cols-2">C</div>
</div>
```

```html
<div data-layout="flex-rows-around" style="height: 350px;">
  <div>A</div>
  <div>B</div>
  <div>C</div>
</div>
```

### Flexbox alignment between

- `flex-cols-between`, `sm:flex-cols-between`, `md:flex-cols-between`, `lg:flex-cols-between`, `xl:flex-cols-between`
- `flex-rows-between`, `sm:flex-rows-between`, `md:flex-rows-between`, `lg:flex-rows-between`, `xl:flex-rows-between`

```html
<div data-layout="flex-cols-between">
  <div data-layout="cols-2">A</div>
  <div data-layout="cols-2">B</div>
  <div data-layout="cols-2">C</div>
</div>
```

```html
<div data-layout="flex-rows-between" style="height: 350px;">
  <div>A</div>
  <div>B</div>
  <div>C</div>
</div>
```

### Flexbox alignment evenly

- `flex-cols-evenly`, `sm:flex-cols-evenly`, `md:flex-cols-evenly`, `lg:flex-cols-evenly`, `xl:flex-cols-evenly`
- `flex-rows-evenly`, `sm:flex-rows-evenly`, `md:flex-rows-evenly`, `lg:flex-rows-evenly`, `xl:flex-rows-evenly`

```html
<div data-layout="flex-cols-evenly">
  <div data-layout="cols-2">A</div>
  <div data-layout="cols-2">B</div>
  <div data-layout="cols-2">C</div>
</div>
```

```html
<div data-layout="flex-rows-evenly" style="height: 350px;">
  <div>A</div>
  <div>B</div>
  <div>C</div>
</div>
```

### Flexbox alignment start

- `flex-cols-start`, `sm:flex-cols-start`, `md:flex-cols-start`, `lg:flex-cols-start`, `xl:flex-cols-start`
- `flex-rows-start`, `sm:flex-rows-start`, `md:flex-rows-start`, `lg:flex-rows-start`, `xl:flex-rows-start`

```html
<div data-layout="flex-cols-start">
  <div data-layout="cols-2">A</div>
  <div data-layout="cols-2">B</div>
  <div data-layout="cols-2">C</div>
</div>
```

```html
<div data-layout="flex-rows-start" style="height: 350px;">
  <div>A</div>
  <div>B</div>
  <div>C</div>
</div>
```

### Flexbox alignment end

- `flex-cols-end`, `sm:flex-cols-end`, `md:flex-cols-end`, `lg:flex-cols-end`, `xl:flex-cols-end`
- `flex-rows-end`, `sm:flex-rows-end`, `md:flex-rows-end`, `lg:flex-rows-end`, `xl:flex-rows-end`

```html
<div data-layout="flex-cols-end">
  <div data-layout="cols-2">A</div>
  <div data-layout="cols-2">B</div>
  <div data-layout="cols-2">C</div>
</div>
```

```html
<div data-layout="flex-rows-end" style="height: 350px;">
  <div>A</div>
  <div>B</div>
  <div>C</div>
</div>
```

### Flexbox alignment stretch

- `flex-cols-stretch`, `sm:flex-cols-stretch`, `md:flex-cols-stretch`, `lg:flex-cols-stretch`, `xl:flex-cols-stretch`
- `flex-rows-stretch`, `sm:flex-rows-stretch`, `md:flex-rows-stretch`, `lg:flex-rows-stretch`, `xl:flex-rows-stretch`

```html
<div data-layout="flex-cols-stretch">
  <div>A</div>
  <div>B</div>
  <div>C</div>
</div>
```

```html
<div data-layout="flex-rows-stretch" style="height: 350px;">
  <div>A</div>
  <div>B</div>
  <div>C</div>
</div>
```

### Vertical and horizontal column centering

```html
<div data-layout="flex-cols-center cols-middle" style="height: 350px;">
  <div data-layout="cols-4">Ipsum dolor amet alcatra landjaeger.</div>
</div>
```

## Offset grid elements

Offset utilities allows an element to be offset on a given column and/or row.

- `cols-start-X`, `sm:cols-start-X`, `md:cols-start-X`, `lg:cols-start-X`, `xl:cols-start-X`
- `cols-end-X`, `sm:cols-end-X`, `md:cols-end-X`, `lg:cols-end-X`, `xl:cols-end-X`
- `rows-start-X`, `sm:rows-start-X`, `md:rows-start-X`, `lg:rows-start-X`, `xl:rows-start-X`
- `rows-end-X`, `sm:rows-end-X`, `md:rows-end-X`, `lg:rows-end-X`, `xl:rows-end-X`

```html
<div data-layout="grid-cols grid-rows">
  <div data-layout="cols-start-2 cols-end-4 rows-start-2 rows-end-12">A</div>
  <div data-layout="cols-start-6 cols-end-6 rows-start-4 rows-end-8">B</div>
  <div data-layout="cols-start-8 cols-end-8 rows-start-2 rows-end-11">C</div>
  <div data-layout="cols-start-10 cols-end-10 rows-start-2 rows-end-2">D</div>
  <div data-layout="cols-start-10 cols-end-10 rows-start-4 rows-end-4">E</div>
  <div data-layout="cols-start-10 cols-end-10 rows-start-6 rows-end-6">F</div>
  <div data-layout="cols-start-10 cols-end-10 rows-start-8 rows-end-8">G</div>
  <div data-layout="cols-start-10 cols-end-10 rows-start-10 rows-end-10">H</div>
</div>
```

## Ordering grid elements

Flexbox allows us to reorder columns regardless of the HTML order.

- `first`, `sm:first`, `md:first`, `lg:first`, `xl:first`
- `last`, `sm:last`, `md:last`, `lg:last`, `xl:last`

### First

```html
<div data-layout="grid-cols-4">
  <div>A</div>
  <div>B</div>
  <div>C</div>
  <div data-layout="first">D</div>
</div>
```

### Last

```html
<div data-layout="grid-cols-4">
  <div data-layout="last">A</div>
  <div>B</div>
  <div>C</div>
  <div>D</div>
</div>
```

### Responsive example

```html
<div data-layout="grid-cols-4">
  <div data-layout="md:last">A</div>
  <div>B</div>
  <div>C</div>
  <div data-layout="md:first">D</div>
</div>
```

## Flex, Fit & Fill

### Flex implicit columns

Implicit uniform columns can define their values at the parent flex element using `flex-cols-?`. There is no need for wrapper elements around each row, see `flex-cols-2` example below.

- `flex-cols-?`, `sm:flex-cols-?`, `md:flex-cols-?`, `lg:flex-cols-?`, `xl:flex-cols-?`

```html
<div data-layout="flex-cols-5">
  <div>5</div>
  <div>5</div>
  <div>5</div>
  <div>5</div>
  <div>5</div>
</div>
```

```html
<div data-layout="flex-cols-2">
  <div>2</div>
  <div>2</div>
  <div>2</div>
  <div>2</div>
</div>
```

### Flex explicit columns

Columns that are not uniform can define their column span value directly on the column element using `cols-?`. Multiple rows are achieved with filling columns according to the 12 column layout.

- `cols-?`, `sm:cols-?`, `md:cols-?`, `lg:cols-?`, `xl:cols-?`

```html
<div data-layout="flex-cols">
  <div data-layout="cols-1">1</div>
  <div data-layout="cols-11">11</div>

  <div data-layout="cols-2">2</div>
  <div data-layout="cols-10">10</div>

  <div data-layout="cols-3">3</div>
  <div data-layout="cols-9">9</div>

  <div data-layout="cols-4">4</div>
  <div data-layout="cols-8">8</div>
</div>
```

### Fit explicit columns

An explicit flex element can shrink to fit the contents using `cols-fit`.

- `cols-fit`, `sm:cols-fit`, `md:cols-fit`, `lg:cols-fit`, `xl:cols-fit`

```html
<div data-layout="flex-cols-4">
  <div>4</div>
  <div>4</div>
  <div data-layout="cols-fit">fit</div>
</div>
```

### Fill explicit columns

An explicit flex element can fill the row using `cols-fill`.

- `cols-fill`, `sm:cols-fill`, `md:cols-fill`, `lg:cols-fill`, `xl:cols-fill`

```html
<div data-layout="flex-cols-4">
  <div>4</div>
  <div>4</div>
  <div data-layout="cols-fill">fill</div>
</div>
```

### Flex implicit rows

Implicit uniform rows can define their values at the parent flex element using `flex-rows-?`.

- `flex-rows-?`, `sm:flex-rows-?`, `md:flex-rows-?`, `lg:flex-rows-?`, `xl:flex-rows-?`

```html
<div data-layout="flex-rows-3" style="height: 350px;">
  <div>3</div>
  <div>3</div>
  <div>3</div>
</div>
```

### Flex explicit rows

Rows that are not uniform can define their row span value directly on the element using `rows-?`.

- `rows-?`, `sm:rows-?`, `md:rows-?`, `lg:rows-?`, `xl:rows-?`

```html
<div data-layout="flex-rows" style="height: 350px;">
  <div data-layout="rows-2">2</div>
  <div data-layout="rows-4">4</div>
  <div data-layout="rows-6">6</div>
</div>
```

### Fit explicit rows

An explicit flex element can shrink to fit the contents using `rows-fit`.

- `rows-fit`, `sm:rows-fit`, `md:rows-fit`, `lg:rows-fit`, `xl:rows-fit`

```html
<div data-layout="flex-rows-4" style="height: 350px;">
  <div>4</div>
  <div>4</div>
  <div data-layout="rows-fit">fit</div>
</div>
```

### Fill explicit rows

An explicit flex element can fill the column using `rows-fill`.

- `rows-fill`, `sm:rows-fill`, `md:rows-fill`, `lg:rows-fill`, `xl:rows-fill`

```html
<div data-layout="flex-rows-4" style="height: 350px;">
  <div>4</div>
  <div data-layout="rows-fill">fill</div>
</div>
```

## Visibility utilities

Multiple helper attributes to show and hide content to the corresponding grid breakpoints.

- `show`, `sm:show`, `md:show`, `lg:show`, `xl:show`
- `hide`, `sm:hide`, `md:hide`, `lg:hide`, `xl:hide`

```html
<div data-layout="grid-cols-2">
  <div data-layout="hide md:show lg:show">
    A <span data-layout="hide lg:show">Also works on inline elements!</span>
  </div>
  <div>B <span data-layout="lg:hide">Also works on inline elements!</span></div>
</div>
```

## Text alignment

- `text-left`, `sm:text-left`, `md:text-left`, `lg:text-left`, `xl:text-left`
- `text-right`, `sm:text-right`, `md:text-right`, `lg:text-right`, `xl:text-right`
- `text-center`, `sm:text-center`, `md:text-center`, `lg:text-center`, `xl:text-center`

```html
<div data-layout="grid-cols">
  <div data-layout="cols-6 text-left">text-left</div>
  <div data-layout="cols-6 text-right">text-right</div>
  <div data-layout="cols-12 text-center">text-center</div>
</div>
```

## Float utilities

The float utils make it easy to float a item left, right, or center (margin auto). The `clear-fix` is a common clear fix utility to force content to clear a block element that is floated. Without a clearfix a single floated item will cause content immediately after it to potentially wrap content which may or may not be desired. Read more about [clear fix here](https://css-tricks.com/snippets/css/clear-fix).

- `clear-fix`, `sm:clear-fix`, `md:clear-fix`, `lg:clear-fix`, `xl:clear-fix`
- `float-left`, `sm:float-left`, `md:float-left`, `lg:float-left`, `xl:float-left`
- `float-center`, `sm:float-center`, `md:float-center`, `lg:float-center`, `xl:float-center`
- `float-right`, `sm:float-right`, `md:float-right`, `lg:float-right`, `xl:float-right`

```html
<div data-layout="clear-fix">
  <div data-layout="float-center">A</div>
  <div data-layout="float-left md:float-right">B</div>
  <div data-layout="float-right md:float-left">C</div>
</div>
```

## Container

Basic `container` attribute to set max width and centered page level content. The container has maximum width of 1440px.

```html
<div data-layout="container">
  <div>Ipsum dolor amet</div>
</div>
```

## Aspect ratio

The aspect ratio utils make it easy to set the aspect ratio of an element. The aspect ratio is set using the `aspect-ratio-X-Y` syntax. The `X` is the width and the `Y` is the height.

- `aspect-ratio-16-9`, `sm:aspect-ratio-16-9`, `md:aspect-ratio-16-9`, `lg:aspect-ratio-16-9`, `xl:aspect-ratio-16-9`
- `aspect-ratio-4-3`, `sm:aspect-ratio-4-3`, `md:aspect-ratio-4-3`, `lg:aspect-ratio-4-3`, `xl:aspect-ratio-4-3`
- `aspect-ratio-3-2`, `sm:aspect-ratio-3-2`, `md:aspect-ratio-3-2`, `lg:aspect-ratio-3-2`, `xl:aspect-ratio-3-2`
- `aspect-ratio-2-1`, `sm:aspect-ratio-2-1`, `md:aspect-ratio-2-1`, `lg:aspect-ratio-2-1`, `xl:aspect-ratio-2-1`
- `aspect-ratio-1-1`, `sm:aspect-ratio-1-1`, `md:aspect-ratio-1-1`, `lg:aspect-ratio-1-1`, `xl:aspect-ratio-1-1`

```html
<div data-layout="aspect-ratio-2-1 md:aspect-ratio-1-1">*:2:1 md:1:1</div>
```
