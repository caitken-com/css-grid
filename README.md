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
7. [Nesting grid elements](#nesting-grid-elements)
8. [Ordering grid elements](#ordering-grid-elements)
9. [Flex layout, Fit & Fill](#flex-fit--fill)
10. [Visibility utilities](#visibility-utilities)
11. [Text alignment](#text-alignment)
12. [Float utilities](#float-utilities)
13. [Containter](#container)

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
  <div data-layout="rows-1">1</div>
  <div data-layout="rows-4">4</div>
  <div data-layout="rows-7">7</div>
</div>
```

## Responsive breakpoints

Breakpoints attributes can be stacked.

| Attribute | Screen size | Device | Behavior |
| --- | --- | --- | --- |
| `grid-cols`<br>`grid-rows`<br>`cols-1` to `cols-12`<br>`rows-1` to `rows-12` | Extra small or any | Phones | Always display grid columns.<br>Always display grid rows.<br>Always column width.<br>Always row height. |
| `grid-cols-sm`<br>`grid-rows-sm`<br>`cols-1-sm` to `cols-12-sm`<br>`rows-1-sm` to `rows-12-sm` | Small devices (480px) | Phones / Tablets | Display grid columns at breakpoint.<br>Display grid rows at breakpoint.<br>100% width to start, column width at breakpoint.<br>100% height to start, row height at breakpoint. |
| `grid-cols-md`<br>`grid-rows-md`<br>`cols-1-md` to `cols-12-md`<br>`rows-1-md` to `rows-12-md` | Medium devices (720px) | Tablets / Laptops | Display grid columns at breakpoint.<br>Display grid rows at breakpoint.<br>100% width to start, column width at breakpoint.<br>100% height to start, row height at breakpoint. |
| `grid-cols-lg`<br>`grid-rows-lg`<br>`cols-1-lg` to `cols-12-lg`<br>`rows-1-lg` to `rows-12-lg` | Large devices (960px) | Tablets / Laptops | Display grid columns at breakpoint.<br>Display grid rows at breakpoint.<br>100% width to start, column width at breakpoint.<br>100% height to start, row height at breakpoint. |
| `grid-cols-xl`<br>`grid-rows-xl`<br>`cols-1-xl` to `cols-12-xl`<br>`rows-1-xl` to `rows-12-xl` | Extra large devices (1440px) | Hi-res Laptop / Desktop | Display grid columns at breakpoint.<br>Display grid rows at breakpoint.<br>100% width to start, column width at breakpoint.<br>100% height to start, row height at breakpoint. |

### Responsive implicit columns

```html
<div data-layout="grid-cols-2-md grid-cols-6-lg">
  <div>2-md 6-lg</div>
  <div>2-md 6-lg</div>
  <div>2-md 6-lg</div>
  <div>2-md 6-lg</div>
  <div>2-md 6-lg</div>
  <div>2-md 6-lg</div>
</div>
```

### Responsive explicit columns

```html
<div data-layout="grid-cols">
  <div data-layout="cols-3-md cols-6-lg">3-md 6-lg</div>
  <div data-layout="cols-3-md cols-6-lg">3-md 6-lg</div>
  <div data-layout="cols-3-md cols-4-lg">3-md 4-lg</div>
  <div data-layout="cols-3-md cols-8-lg">3-md 8-lg</div>
</div>
```

### Responsive implicit rows

```html
<div data-layout="grid-rows-2 grid-rows-3-lg" style="height: 350px;">
  <div>2-? 3-lg</div>
  <div>2-? 3-lg</div>
  <div data-layout="hide show-lg">hide-? show-lg</div>
</div>
```

### Responsive explicit rows

```html
<div data-layout="grid-rows" style="height: 350px;">
  <div data-layout="rows-1 rows-7-lg">1-? 7-lg</div>
  <div data-layout="rows-4">4-?</div>
  <div data-layout="rows-7 rows-1-lg">7-? 1-lg</div>
</div>
```

## Gap

- `cols-gap-0`, `cols-gap-0-sm`, `cols-gap-0-md`, `cols-gap-0-lg`, `cols-gap-0-xl`
- `cols-gap-1`, `cols-gap-1-sm`, `cols-gap-1-md`, `cols-gap-1-lg`, `cols-gap-1-xl`
- `cols-gap-2`, `cols-gap-2-sm`, `cols-gap-2-md`, `cols-gap-2-lg`, `cols-gap-2-xl`
- `cols-gap-3`, `cols-gap-3-sm`, `cols-gap-3-md`, `cols-gap-3-lg`, `cols-gap-3-xl`
- `cols-gap-4`, `cols-gap-4-sm`, `cols-gap-4-md`, `cols-gap-4-lg`, `cols-gap-4-xl`
- `cols-gap-5`, `cols-gap-5-sm`, `cols-gap-5-md`, `cols-gap-5-lg`, `cols-gap-5-xl`

---

- `rows-gap-0`, `rows-gap-0-sm`, `rows-gap-0-md`, `rows-gap-0-lg`, `rows-gap-0-xl`
- `rows-gap-1`, `rows-gap-1-sm`, `rows-gap-1-md`, `rows-gap-1-lg`, `rows-gap-1-xl`
- `rows-gap-2`, `rows-gap-2-sm`, `rows-gap-2-md`, `rows-gap-2-lg`, `rows-gap-2-xl`
- `rows-gap-3`, `rows-gap-3-sm`, `rows-gap-3-md`, `rows-gap-3-lg`, `rows-gap-3-xl`
- `rows-gap-4`, `rows-gap-4-sm`, `rows-gap-4-md`, `rows-gap-4-lg`, `rows-gap-4-xl`
- `rows-gap-5`, `rows-gap-5-sm`, `rows-gap-5-md`, `rows-gap-5-lg`, `rows-gap-5-xl`

```html
<div data-layout="grid-cols-3 cols-gap-1-sm cols-gap-2-md cols-gap-3-lg cols-gap-5-xl rows-gap-1-sm rows-gap-2-md rows-gap-3-lg rows-gap-5-xl">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
</div>
```


## Aligning grid elements

- `cols-top`, `cols-top-sm`, `cols-top-md`, `cols-top-lg`, `cols-top-xl`
- `cols-middle`, `cols-middle-sm`, `cols-middle-md`, `cols-middle-lg`, `cols-middle-xl`
- `cols-bottom`, `cols-bottom-sm`, `cols-bottom-md`, `cols-bottom-lg`, `cols-bottom-xl`

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

- `flex-cols-center`, `flex-cols-center-sm`, `flex-cols-center-md`, `flex-cols-center-lg`, `flex-cols-center-xl`
- `flex-rows-center`, `flex-rows-center-sm`, `flex-rows-center-md`, `flex-rows-center-lg`, `flex-rows-center-xl`

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

- `flex-cols-around`, `flex-cols-around-sm`, `flex-cols-around-md`, `flex-cols-around-lg`, `flex-cols-around-xl`
- `flex-rows-around`, `flex-rows-around-sm`, `flex-rows-around-md`, `flex-rows-around-lg`, `flex-rows-around-xl`

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

- `flex-cols-between`, `flex-cols-between-sm`, `flex-cols-between-md`, `flex-cols-between-lg`, `flex-cols-between-xl`
- `flex-rows-between`, `flex-rows-between-sm`, `flex-rows-between-md`, `flex-rows-between-lg`, `flex-rows-between-xl`

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

- `flex-cols-evenly`, `flex-cols-evenly-sm`, `flex-cols-evenly-md`, `flex-cols-evenly-lg`, `flex-cols-evenly-xl`
- `flex-rows-evenly`, `flex-rows-evenly-sm`, `flex-rows-evenly-md`, `flex-rows-evenly-lg`, `flex-rows-evenly-xl`

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

- `flex-cols-start`, `flex-cols-start-sm`, `flex-cols-start-md`, `flex-cols-start-lg`, `flex-cols-start-xl`
- `flex-rows-start`, `flex-rows-start-sm`, `flex-rows-start-md`, `flex-rows-start-lg`, `flex-rows-start-xl`

```html
<div data-layout="flex-cols cols-start">
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

- `flex-cols-end`, `flex-cols-end-sm`, `flex-cols-end-md`, `flex-cols-end-lg`, `flex-cols-end-xl`
- `flex-rows-end`, `flex-rows-end-sm`, `flex-rows-end-md`, `flex-rows-end-lg`, `flex-rows-end-xl`

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

- `flex-cols-stretch`, `flex-cols-stretch-sm`, `flex-cols-stretch-md`, `flex-cols-stretch-lg`, `flex-cols-stretch-xl`
- `flex-rows-stretch`, `flex-rows-stretch-sm`, `flex-rows-stretch-md`, `flex-rows-stretch-lg`, `flex-rows-stretch-xl`

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

Offset utilities allows a column to be offset on a given row.

- `cols-offset-X`, `cols-offset-X-sm`, `cols-offset-X-lg`, `cols-offset-X-xl`
- `rows-offset-X`, `rows-offset-X-sm`, `rows-offset-X-lg`, `rows-offset-X-xl`

```html
<div data-layout="grid-cols">
  <div data-layout="cols-4">cols-4</div>
  <div data-layout="cols-4 cols-offset-9">cols-4 cols-offset-9</div>
  <div data-layout="cols-3-md cols-offset-4-md">cols-3-md cols-offset-4-md</div>
  <div data-layout="cols-3-md cols-offset-10-md">cols-3-md cols-offset-10-md</div>
  <div data-layout="cols-6-md cols-offset-4-md">cols-6-md cols-offset-4-md</div>
</div>
```

## Nesting grid elements

Grids can be nested within other grids to create more complex layouts.

```html
<div data-layout="grid-cols-2-lg">
  <div>
    <p>2-lg</p>
    <div data-layout="grid-cols-6">
      <div>6</div>
      <div>6</div>
      <div>6</div>
      <div>6</div>
      <div>6</div>
      <div>6</div>
    </div>
  </div>
  <div>
    <p>2-lg</p>
    <div data-layout="grid-cols-2-sm grid-cols-4-md">
      <div>2-sm 4-md</div>
      <div>2-sm 4-md</div>
      <div>2-sm 4-md</div>
      <div>2-sm 4-md</div>
    </div>
  </div>
</div>
```

## Ordering grid elements

Flexbox allows us to reorder columns regardless of the HTML order.

- `first`, `first-sm`, `first-md`, `first-lg`, `first-xl`
- `last`, `last-sm`, `last-md`, `last-lg`, `last-xl`

### First

```html
<div data-layout="grid-cols-4">
  <div>A</div>
  <div>B</div>
  <div>D</div>
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
  <div data-layout="last-md">A</div>
  <div>B</div>
  <div>C</div>
  <div data-layout="first-md">D</div>
</div>
```

## Flex, Fit & Fill

### Flex implicit columns

Implicit uniform columns can define their values at the parent flex element using `flex-cols-?`. There is no need for wrapper elements around each row, see `flex-cols-2` example below.

- `flex-cols-?`, `flex-cols-?-sm`, `flex-cols-?-md`, `flex-cols-?-lg`, `flex-cols-?-xl`

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

- `cols-?`, `cols-?-sm`, `cols-?-md`, `cols-?-lg`, `cols-?-xl`

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

- `cols-fit`, `cols-fit-sm`, `cols-fit-md`, `cols-fit-lg`, `cols-fit-xl`

```html
<div data-layout="flex-cols-4">
  <div>4</div>
  <div>4</div>
  <div data-layout="cols-fit">fit</div>
</div>
```

### Fill explicit columns

An explicit flex element can fill the row using `cols-fill`.

- `cols-fill`, `cols-fill-sm`, `cols-fill-md`, `cols-fill-lg`, `cols-fill-xl`

```html
<div data-layout="flex-cols-4">
  <div>4</div>
  <div>4</div>
  <div data-layout="cols-fill">fill</div>
</div>
```

### Flex implicit rows

Implicit uniform rows can define their values at the parent flex element using `flex-rows-?`.

- `flex-rows-?`, `flex-rows-?-sm`, `flex-rows-?-md`, `flex-rows-?-lg`, `flex-rows-?-xl`

```html
<div data-layout="flex-rows-3" style="height: 350px;">
  <div>3</div>
  <div>3</div>
  <div>3</div>
</div>
```

### Flex explicit rows

Rows that are not uniform can define their row span value directly on the element using `rows-?`.

- `rows-?`, `rows-?-sm`, `rows-?-md`, `rows-?-lg`, `rows-?-xl`

```html
<div data-layout="flex-rows" style="height: 350px;">
  <div data-layout="rows-2">2</div>
  <div data-layout="rows-4">4</div>
  <div data-layout="rows-6">6</div>
</div>
```

### Fit explicit rows

An explicit flex element can shrink to fit the contents using `rows-fit`.

- `rows-fit`, `rows-fit-sm`, `rows-fit-md`, `rows-fit-lg`, `rows-fit-xl`

```html
<div data-layout="flex-rows-4" style="height: 350px;">
  <div>4</div>
  <div>4</div>
  <div data-layout="rows-fit">fit</div>
</div>
```

### Fill explicit rows

An explicit flex element can fill the column using `rows-fill`.

- `rows-fill`, `rows-fill-sm`, `rows-fill-md`, `rows-fill-lg`, `rows-fill-xl`

```html
<div data-layout="flex-rows-4" style="height: 350px;">
  <div>4</div>
  <div data-layout="rows-fill">fill</div>
</div>
```

## Visibility utilities

Multiple helper attributes to show and hide content to the corresponding grid breakpoints.

- `show`, `show-sm`, `show-md`, `show-lg`, `show-xl`
- `hide`, `hide-sm`, `hide-md`, `hide-lg`, `hide-xl`

```html
<div data-layout="grid-cols-2">
  <div data-layout="hide show-md">
    A <span data-layout="hide show-lg">works on inline elements</span>
  </div>
  <div>B</div>
</div>
```

## Text alignment

- `text-left`, `text-left-sm`, `text-left-md`, `text-left-md`, `text-left-lg`
- `text-right`, `text-right-sm`, `text-right-md`, `text-right-md`, `text-right-lg`
- `text-center`, `text-center-sm`, `text-center-md`, `text-center-md`, `text-center-lg`

```html
<div data-layout="grid-cols">
  <div data-layout="cols-6 text-left">text-left</div>
  <div data-layout="cols-6 text-right">text-right</div>
  <div data-layout="cols-12 text-center">text-center</div>
</div>
```

## Float utilities

The float utils make it easy to float a item left, right, or center (margin auto). The `clear-fix` is a common clear fix utility to force content to clear a block element that is floated. Without a clearfix a single floated item will cause content immediately after it to potentially wrap content which may or may not be desired. Read more about [clear fix here](https://css-tricks.com/snippets/css/clear-fix).

- `clear-fix`, `clear-fix-sm`, `clear-fix-md`, `clear-fix-lg`, `clear-fix-xl`
- `float-left`, `float-left-sm`, `float-left-md`, `float-left-lg`, `float-left-xl`
- `float-center`, `float-center-sm`, `float-center-md`, `float-center-lg`, `float-center-xl`
- `float-right`, `float-right-sm`, `float-right-md`, `float-right-lg`, `float-right-xl`

```html
<div data-layout="clear-fix">
	<div data-layout="float-center">A</div>
	<div data-layout="float-left float-right-md">B</div>
	<div data-layout="float-right float-left-md">C</div>
</div>
```

## Container

Basic `container` attribute to set max width and centered page level content. The container defaults to a maximum width of 1000px.

```html
<div data-layout="container">
  <div>Ipsum dolor amet</div>
</div>
```
