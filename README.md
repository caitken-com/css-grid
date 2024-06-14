# CSS Grid
A lightweight layout library for building great responsive mobile first layouts that work everywhere. Open source, built with CSS Grid and Flexbox.

## Useage

```html
<link href="https://cdn.statically.io/gh/caitken-com/css-grid/main/grid.css" rel="stylesheet" />
```

## Layout

This library leverages custom html data attributes to help namespace the layout based CSS. The grid can be 12 columns and/or rows.

### Layout: Implicit Columns

Implicit uniform columns can define their values at the parent grid element using `grid-cols-X`. There is no need for wrapper elements around each row, see example below.

```html
<div data-layout="grid-cols-2">
  <div>2</div>
  <div>2</div>
  <div>2</div>
  <div>2</div>
</div>
```

### Explicit Columns

Columns that are not uniform can define their column span value directly on the column element using `cols-X`. Multiple rows are achieved with filling columns according to the 12 column layout.

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
| `cols-1` to `cols-12`<br>`rows-1` to `rows-12` | Extra small or any | Phones | Always column width.<br>Always row height. |
| `cols-1-sm` to `cols-12-sm`<br>`rows-1-sm` to `rows-12-sm` | Small devices (480px) | Phones / Tablets | 100% width to start, column width at breakpoint.<br>100% height to start, row height at breakpoint. |
| `cols-1-md` to `cols-12-md`<br>`rows-1-md` to `rows-12-md` | Medium devices (720px) | Tablets / Laptops | 100% width to start, column width at breakpoint.<br>100% height to start, row height at breakpoint. |
| `cols-1-lg` to `cols-12-lg`<br>`rows-1-lg` to `rows-12-lg` | Large devices (960px) | Tablets / Laptops | 100% width to start, column width at breakpoint.<br>100% height to start, row height at breakpoint. |
| `cols-1-xl` to `cols-12-xl`<br>`rows-1-xl` to `rows-12-xl` | Extra large devices (1440px) | Hi-res Laptop / Desktop | 100% width to start, column width at breakpoint.<br>100% height to start, row height at breakpoint. |

### Implicit example

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

### Explicit example

```html
<div data-layout="grid-cols">
  <div data-layout="cols-3-md cols-6-lg">3-md 6-lg</div>
  <div data-layout="cols-3-md cols-6-lg">3-md 6-lg</div>
  <div data-layout="cols-3-md cols-4-lg">3-md 4-lg</div>
  <div data-layout="cols-3-md cols-8-lg">3-md 8-lg</div>
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

## Gap spacing

With special modifiers you can remove gap (gutter) in grid layouts.

- `gap-none`, `gap-none-sm`, `gap-none-md`, `gap-none-lg`, `gap-none-xl`
- `gap-cols-none`, `gap-cols-none-sm`, `gap-cols-none-md`, `gap-cols-none-lg`, `gap-cols-none-xl`
- `gap-rows-none`, `gap-rows-none-sm`, `gap-rows-none-md`, `gap-rows-none-lg`, `gap-rows-none-xl`

```html
<div data-layout="grid-cols-3 gap-none">
  <div>A</div>
  <div>B</div>
  <div>C</div>
  <div>D</div>
  <div>E</div>
  <div>F</div>
</div>

<div data-layout="grid-cols-3 gap-cols-none">
  <div>A</div>
  <div>B</div>
  <div>C</div>
  <div>D</div>
  <div>E</div>
  <div>F</div>
</div>

<div data-layout="grid-cols-3 gap-rows-none">
  <div>A</div>
  <div>B</div>
  <div>C</div>
  <div>D</div>
  <div>E</div>
  <div>F</div>
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

## Centered grid elements

You can use the `cols-offset-X` utilities to center elements.

```html
<div data-layout="grid-cols-4">
  <div data-layout="cols-offset-2">A</div>
  <div>B</div>
</div>
```

### Vertical and horizontal column centering

Using a combination of `cols-middle` and `cols-offset-X` we can create centered containers.

```html
<div data-layout="grid-cols cols-middle" style="height: 350px;">
  <div data-layout="cols-4 cols-offset-5">Ipsum dolor amet alcatra landjaeger.</div>
</div>
```

## Flex, Fit & Fill

The `flex`, `fill` and `fit` attributes can be used to align variable size elements. Example use the `flex` attribute to set all immediate children to flex items. Once set use `fit` to adjust element to fit only to its content size and use `fill` to fill in all available space.

- `flex`
- `fit`, `fit-sm`, `fit-md`, `fit-lg`, `fit-xl`
- `fill`, `fill-sm`, `fill-md`, `fill-lg`, `fill-xl`

```html
<div data-layout="flex">
  <div data-layout="fit">
    <div>&lt;</div>
  </div>
  <div data-layout="fill">
    <div>Ipsum dolor amet alcatra</div>
  </div>
  <div data-layout="fit">
    <div>&gt;</div>
  </div>
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
