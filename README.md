# CSS Grid
A lightweight layout library for building great responsive mobile first UIs that work everywhere. Open Source, built with CSS Grid and Flexbox. This work is based on [blueprintcss.dev](https://blueprintcss.dev) which seems to have disappeared from the internet and github.

## Useage

The original (v3.1.3) is still available via CDN:

```html
<link href="https://unpkg.com/blueprint-css@3.1.3/dist/blueprint.min.css" rel="stylesheet" />
```

## Guide

Blueprint leverages HTML attributes to help namespace layout based CSS. Attributes allow consise layout names and allows us to easily understand the layout of our views. The grid is a 12 column grid.

### Layout: Implicit Columns

Implicit uniform columns can define their values at the parent grid element. Unlike traditional Flexbox or float grid libraries there is no need for wrapper elements around each column.

```html
<div bp="grid 4">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>
```

### Layout: Explicit Columns

Columns that are not uniform can define their column span value directly on the column element. Column properties can be placed directly on the element with no need for wrapper elements.

```html
<div bp="grid">
  <div bp="4">1</div>
  <div bp="8">2</div>
</div>
```

### Layout: No Rows Needed

Most class based grids require a row wrapper element for every given row. This is not needed with blueprint grid. Multiple rows are achieved with filling columns according to the 12 column layout.

```html
<div bp="grid">
  <div bp="6">6</div>
  <div bp="6">6</div>
  <div bp="4">4</div>
  <div bp="4">4</div>
  <div bp="4">4</div>
</div>
```

### Layout: Responsive Columns

Responsive column utilities are available. Column breakpoints can be stacked. Column breakpoints are adjustable using the Sass variables.

<table>
  <thead>
    <tr>
      <th></th>
      <th>Extra small or Any</th>
      <th>Small devices (480px)</th>
      <th>Medium devices (720px)</th>
      <th>Large devices (960px)</th>
      <th>Extra Large devices (1440px)</th>
    </tr>
    
  </thead>
  <tbody>
    <tr>
      <th>Device</th>
      <td>Phones</td>
      <td>Phones/Tablets</td>
      <td>Tablets/Laptops</td>
      <td>Laptop/Desktop</td>
      <td>Hi-res Laptop/Desktop</td>
    </tr>
    <tr>      
      <th>Class</th>
      <td><code>1</code> to <code>12</code></td>
      <td><code>1@sm</code> to <code>12@sm</code></td>
      <td><code>1@md</code> to <code>12@md</code></td>
      <td><code>1@lg</code> to <code>12@lg</code></td>
      <td><code>1@xl</code> to <code>12@xl</code></td>
    </tr>
    <tr>
      <th>Behavior</th>
      <td>Always column width</td>
      <td colspan="4">Width 100% to start, column width at above breakpoints</td>
    </tr>
  </tbody>
</table>

### Column Alignment: Auto Matching Heights

Blueprint grid columns automatically match column heights.

```html
<div bp="grid 3">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>
    Bacon ipsum dolor amet alcatra landjaeger.
  </div>
</div>
```

### Column Alignment: Vertically Center Columns

```html
<div bp="grid 3 vertical-center">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>Ipsum dolor amet alcatra landjaeger.</div>
</div>
```

_Added in v3.2:_

- `vertical-center-sm`
- `vertical-center-md`
- `vertical-center-lg`
- `vertical-center-xl`

### Column Alignment: Vertically Top Align Columns

```html
<div bp="grid 3 vertical-start">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>Ipsum dolor amet alcatra landjaeger.</div>
</div>
```

_Added in v3.2:_

- `vertical-start-sm`
- `vertical-start-md`
- `vertical-start-lg`
- `vertical-start-xl`

### Column Alignment: Vertically Bottom Align Columns

```html
<div bp="grid 3 vertical-end">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>Ipsum dolor amet alcatra landjaeger.</div>
</div>
```

_Added in v3.2:_

- `vertical-end-sm`
- `vertical-end-md`
- `vertical-end-lg`
- `vertical-end-xl`

### Gap Spacing

With special modifiers you can remove gap (gutter) in row layouts. `gap-none` `gap-row-none` `gap-column-none` Example with `gap-none` we can remove the all gap from our row. This is useful for rows that have custom padding or spacing and need to override the grids default.

```html
<div bp="grid 4 gap-none">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
</div>
```

### Column Offset

Offset utilities allows a column to be offset on a given row.

```html
<div bp="grid">
  <div bp="4">2</div>
  <div bp="4 offset-9">4 offset-9</div>
</div>

<div bp="grid">
  <div bp="3@md offset-4@md">3@md offset-4@md</div>
  <div bp="3@md offset-10@md">3@md offset-10@md</div>
</div>

<div bp="grid">
  <div bp="6@md offset-4@md">col 6@md offset-4@md</div>
</div>
```

### Column Nesting

Grids can be nested within other grids to create more complex layouts.

```html
<div bp="grid 6@lg">
  <div>
    <h2>6@lg</h2>
    <div bp="grid 4">
      <div>4</div>
      <div>4</div>
      <div>4</div>
      <div>4</div>
      <div>4</div>
      <div>4</div>
    </div>
  </div>
  <div>
    <h2>6@md</h2>
    <div bp="grid 3 6@md">
      <div>3 6@md</div>
      <div>3 6@md</div>
      <div>3 6@md</div>
      <div>3 6@md</div>
    </div>
  </div>
</div>
```

### Columns Ordering

Flexbox allows us to reorder columns regardless of the HTML order. Reordering has `sm` `md` `lg` breakpoints matching the grid breakpoints. Example: `first` or `first@md`

### Columns Ordering: First

```html
<div bp="grid 3">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div bp="first">4</div>
</div>
```

### Columns Ordering: Last

```html
<div bp="grid 3">
  <div bp="last">1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
</div>
```

### Columns Ordering: Dynamic

```html
<div bp="grid 3">
  <div bp="last@md">1</div>
  <div>2</div>
  <div>3</div>
  <div bp="first@md">4</div>
</div>
```

### Centered Columns

You can use the Blueprint `offset` utilities to center columns.

```html
<div bp="grid 3">
  <div bp="offset-2">1</div>
  <div>1</div>
</div>
```

### Vertical and Horizontal Column Centering

Using a combination of `vertical-center` and `offset` we can create centered containers.

```html
<div bp="grid vertical-center" style="background-color: #f3f3f3; height: 350px;">
  <div bp="4 offset-5">Some centered content goes here.</div>
</div>
```

### Max Width

Using max classes you can set the max width on elements proportionally to the max width of the `container` class. This allows containers and elements to be created that are flexible but do not scale with the view port. Example if we add a `6--max` the element max width will be half of the `container` class width. (1000/2 = 500px). This can be useful for setting a max width on objects such as forms or flexible images. Max classes can be used anywhere and are not restricted to only in `row`.

```html
<div bp="8--max">8/12</div>

<div bp="4--max">4/12</div>
```

### Full Width

Full width values allow you to easily control when an element should be full width or not. This is useful for layout patterns such as forcing elements to be 100% width on smaller screens.

```html
<div bp="2--max full-width-until@sm">full-width-until@sm</div>

<div bp="2--max full-width-until@md">full-width-until@md</div>

<div bp="2--max full-width-until@lg">full-width-until@lg</div>

<div bp="full-width">full-width</div>
```

### Flex, Fit & Fill

The `flex`, `fill` and `fit` classes can be used to align variable size elements. Example use the `flex` class to set all immediate children to flex items. Once set use `fit` to adjust element to fit only to its content size and use `fill` to fill in all available space. The `number` class can be used in combination with the `fill` to adjust to specific sizes.

```html
div bp="flex">
  <div bp="fit">
    <span><</span>
  </div>
  <div bp="fill">
    <div>Content</div>
  </div>
  <div bp="fill 3">
    <div>></div>
  </div>
</div>
```

### Visibility Utilities

Blueprint CSS contains multiple helper classes to show and hide content to the corresponding grid breakpoints.

```html
<div bp="grid 6">
  <div bp="hide show@md">
    col <span bp="hide show@lg">- works on inline elements</span>
  </div>
  <div>col</div>
</div>
```

<table class="table visible-table">
  <thead>
    <tr>
      <th></th>
      <th>Extra Small devices</th>
      <th>Small devices (≥480px)</th>
      <th>Medium devices (≥720px)</th>
      <th>Large devices (≥960px)</th>
      <th>Extra Large devices (≥1440px)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Device</th>
      <td>Phones</td>
      <td>Phones/Tablets</td>
      <td>Tablets/Laptops</td>
      <td>Laptop/Desktop</td>
      <td>Hi-res Laptop/Desktop</td>
    </tr>
    <tr>
      <th>Container width</th>
      <td>auto</td>
      <td>480px</td>
      <td>720px</td>
      <td>960px</td>
      <td>1440px</td>
    </tr>
    <tr>
      <th>show</th>
      <td>Show</td>
      <td>Show</td>
      <td>Show</td>
      <td>Show</td>
      <td>Show</td>
    </tr>
    <tr>
      <th>hide</th>
      <td>Hide</td>
      <td>Hide</td>
      <td>Hide</td>
      <td>Hide</td>
      <td>Hide</td>
    </tr>
    <tr>
      <th>show@sm</th>
      <td>Hide</td>
      <td>Show</td>
      <td>Show</td>
      <td>Show</td>
      <td>Show</td>
    </tr>
    <tr>
      <th>show@md</th>
      <td>Hide</td>
      <td>Hide</td>
      <td>Show</td>
      <td>Show</td>
      <td>Show</td>
    </tr>
    <tr>
      <th>show@lg</th>
      <td>Hide</td>
      <td>Hide</td>
      <td>Hide</td>
      <td>Show</td>
      <td>Show</td>
    </tr>
    <tr>
      <th>show@xl</th>
      <td>Hide</td>
      <td>Hide</td>
      <td>Hide</td>
      <td>Hide</td>
      <td>Show</td>
    </tr>
    <tr>
      <th>hide@sm</th>
      <td>Show</td>
      <td>Hide</td>
      <td>Hide</td>
      <td>Hide</td>
      <td>Hide</td>
    </tr>
    <tr>
      <th>hide@md</th>
      <td>Show</td>
      <td>Show</td>
      <td>Hide</td>
      <td>Hide</td>
      <td>Hide</td>
    </tr>
    <tr>
      <th>hide@lg</th>
      <td>Show</td>
      <td>Show</td>
      <td>Show</td>
      <td>Hide</td>
      <td>Hide</td>
    </tr>
    <tr>
      <th>hide@xl</th>
      <td>Show</td>
      <td>Show</td>
      <td>Show</td>
      <td>Show</td>
      <td>Hide</td>
    </tr>
  </tbody>
</table>

### Spacing Utilities

Spacing helpers provide a set of utility classes for margin and padding. Often we find that we want to make minor adjustments in our layouts without having to write additional view specific CSS. The utility classes can be adjusted site wide with a few simple Sass variables if needed.

```html
<div bp="margin--sm">demo</div>

<div bp="padding-bottom--lg">demo</div>
```

- `margin`
- `margin--xs`
- `margin--sm`
- `margin--lg`
- `margin--none`

---

- `margin-top`
- `margin-top--xs`
- `margin-top--sm`
- `margin-top--lg`
- `margin-top--none`

---

- `margin-right`
- `margin-right--xs`
- `margin-right--sm`
- `margin-right--lg`
- `margin-right--none`

---

- `margin-bottom`
- `margin-bottom--xs`
- `margin-bottom--sm`
- `margin-bottom--lg`
- `margin-bottom--none`

---

- `margin-left`
- `margin-left--xs`
- `margin-left--sm`
- `margin-left--lg`
- `margin-left--none`

---

- `padding`
- `padding--xs`
- `padding--sm`
- `padding--lg`
- `padding--none`

---

- `padding-top`
- `padding-top--xs`
- `padding-top--sm`
- `padding-top--lg`
- `padding-top--none`

---

- `padding-right`
- `padding-right--xs`
- `padding-right--sm`
- `padding-right--lg`
- `padding-right--none`

---

- `padding-bottom`
- `padding-bottom--xs`
- `padding-bottom--sm`
- `padding-bottom--lg`
- `padding-bottom--none`

---

- `padding-left`
- `padding-left--xs`
- `padding-left--sm`
- `padding-left--lg`
- `padding-left--none`

### Text Alignment

```html
<div bp="text-left">text-left</div>

<div bp="text-right">text-right</div>

<div bp="text-center">text-center</div>
```

### Float Utilities

The float utils make it easy to float a item left, right, or center (margin auto). The clear-fix is a common clear fix utility to force content to clear a block element that is floated. Without a clearfix a single floated item will cause content immediately after it to potentially wrap content which may or may not be desired. Read more about [clear fix here](https://css-tricks.com/snippets/css/clear-fix).

```html
<div bp="float-center 4--max">float-center</div>
<div bp="float-left 4--max">float-left</div>
<div bp="float-right 4--max">float-right</div>
<div bp="clear-fix">clear-fix</div>
```

### Container

Blueprint also has a basic container value to set max width and centered page level content. The container defaults to a maximum width of 1000px.

```html
<div bp="container">
  <div>container</div>
</div>
```
