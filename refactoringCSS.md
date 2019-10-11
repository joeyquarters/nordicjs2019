# Refactoring (the way we talk about) CSS

by Rachel Andrew (@rachelandrew)

Slides: https://noti.st/rachelandrew

## Understanding `display`

`block` and `inline` are the regular flow of things

_CSS does work for us before we write any CSS_

Changing the value of display changes that element and its **direct children**

### The two display types

There is an _outer_ and an _inner_ display type

```css
div {
  display: block flex; // outer inner
}
```

## Block Formatting Context

```css
.box {
  display: flow-root; /* Adds a new BFC */
}
```

## Writing Modes

Changes block dimension and line dimension

```css
writing-mode: vertical-rtl; /* block-inline */
```

## Logical Properties & Values

Mapping the physical world to the logical flow-relative. Gets around setting `width` and `height`, which are based on the screen.

```css
.example {
  inline-size: 300px;
  block-size: 600px;
}
```

> We need to think in terms of this _flow-relative_, _logical_ world

## Box Alignment

Aligning things in the block and inline dimensions.

Distribution of space and alignment of items within their space.

For `display: grid`:

```css
justify-content: space-between /* inline axis */
align-content: end; /* block axis */
```

## The Box Model

It's becoming less important because we had to assign percentages and lengths to achieve layout.

Now, we need to think about the minimum size and maximum size of this box.

```css
.example {
  grid-template-columns: min-content max-content;
}
```
