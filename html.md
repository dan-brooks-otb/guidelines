# Coding standards for HTML

Welcome to our coding standards for writing HTML.

If you don't like something here, want to add to it or want to change/rock our world create a pull request and we'll go from there!

## Coding style

* Use spaces instead of tabs with a 2 space indent
* Make use HTML5 tags where appropriate, e.g. `<header>` or `<input type="email">`

### Grid classes

Where possible, divs that use grid classes (e.g. `row` or `column-(n)`) should not have any additional classes applied to them. However on occasion it is unavoidable, for example if using flexbox to overwrite grid functionality on smaller screen sizes.

For example,

#### Bad

```
<div class="column-6 flight-info">
  ...
</div>
```

#### Good

```
<div class="column-6">
  <div class="flight-info">
    ...
  </div>
</div>
```

### Text elements

Text elements such as headings and paragraphs should have the opening and closing tags on the same line, with the text content between them, e.g.

```
<p>Some text goes here</p>
```
