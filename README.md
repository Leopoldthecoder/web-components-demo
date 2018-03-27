# web-components-demo

> This demo is runnable in latest Chrome. Not tested in other browsers.

A table component based on Web Components, which is made up of four parts:
- [Custom Elements](https://www.w3.org/TR/custom-elements/)
- [Shadow DOM](https://w3c.github.io/webcomponents/spec/shadow/)
- [HTML Imports](https://w3c.github.io/webcomponents/spec/imports/)
- [The Template Element](https://html.spec.whatwg.org/multipage/scripting.html#the-template-element)

## API

The table is registered as a custom element `my-table`. You can pass to it an attribute named `rows`, defining all the cells and rows.

Attribute | Type
----------|-----
rows | Object[]

<br>

It has a slot for its title. When you need a title for your table, you can:
```html
<my-table>
  <h1>Title of My Table</h1>
</my-table>
```

<br>

Each row has a checkbox. Checking it will fire an event called `select-change` with a parameter `event`. In `event.detail` you'll know which row has been checked and its checking status.

Event | Parameter
------|----------
select-change| { detail: { row, checked } }

## v0 vs. v1
As the specs evolves, there're different writings for shadow DOMs, slots, custom element registrations, etc. I implemented the same table component in both old and new writings (I call them v0 and v1 respectively). You can switch the `href` prop in `index.html` to see the differences.

Note that in order for both components to work properly in Chrome, I didn't implement the v1 component with all v1 new features (e.g. slots) because some of them may cause error or simply won't work in the latest Chrome.

## Oops
One thing this demo doesn't cover is something called *customized built-in element* (you can find its definition in the custom elements spec). Both components in this repo are *autonomous custom element*, if you want to know the terminology.

I didn't do customized built-in elements because according to [caniuse](https://caniuse.com/#search=web%20components), Chrome doesn't support it yet:

<img src="https://user-images.githubusercontent.com/10095631/37965152-ae9ea7e4-31f6-11e8-9c8f-162dd26d6629.png" alt="caniuse" width="480px">
