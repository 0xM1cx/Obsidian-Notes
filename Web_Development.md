Source: [Bootstrapbay](https://bootstrapbay.com/blog/day-2-bootstrap-4-grid-system-tutorial-examples/)
## Bootstrap 4 Containers
A Bootstrap 4 container is an element with the class `.container`. The container is the root of the Bootstrap 4 grid system and it is used to control the width of the layout. It contains all the elements in a page. This means your page should have the following structure: first the body of the HTML page, inside of it you add the container and all the other elements inside the container.

```html
<body>
    <div class="container">
    ...
    </div>
</body>
```

The simple `.container` class sets the width of the layout depending on the width of the screen. It places the content in the middle of the page aligning it horizontally. There is equal space between the Bootstrap 4 container and the left and the right edge of the page. The .`container` scales down in width as the screen width narrows and becomes full-width on mobile. The width of the container is defined inside the Bootstrap 4 library for every screen size. You can see the exact [sizes here](https://getbootstrap.com/docs/4.1/layout/grid/#grid-options).

A full-width container takes 100% of the screen size regardless of the screen width. To use it you need to add the class .`container-fluid`.
```html
<div class="container-fluid">
	This is a full width container
</div>
```

## Bootstrap 4 Rows
Bootstrap 4 rows are horizontal slices of the screen. They are used wrappers for columns. To use them, you need the `.row` class.
```html
<div class="row">
	...
</div>
```

**They are only used for containing columns.** If you place other elements inside the row along with columns you will not get the expected result.

**They have to be placed in containers.** Containers can hold any element, but a row must be placed inside a container. If you don’t do this, you will get a horizontal scroll on your page. This happens because rows have negative left and right margins of 15. The container has 15px paddings so it counteracts the margins.

**The columns have to be children of the row.** Otherwise they will not align. The rows and columns are created to work together in this strict hierarchy.

## Bootstrap 4 Columns
Columns help you divide the screen horizontally. If you place a single column in your row, it will take up all the width. If you add two columns, they will each take 1/2 from the width. And so it goes for any number of columns.
```html
<div class="container">
  <div class="row">
    <div class="col">
      ...
    </div>
  </div>
  <div class="row">
    <div class="col">
      ...
    </div>
     <div class="col">
       ...
     </div>
  </div>
  <div class="row">
     <div class="col">
      ...
     </div>
     <div class="col">
       ...
     </div>
     <div class="col">
      ...
     </div>
     <div class="col">
       ...
     </div>
  </div>
</div>
```

## Setting Sizes
Using the `.col` class sets the width for the column dynamically. That means that depending on the number of columns in a row, the width of a column will be the width of the container divided by the number of columns.

But there is another way to define columns. You can use classes for columns and define their size. By default, the Bootstrap 4 grid consists of 12 columns. You can select any size from 1 to 12 for your column. If you want 3 equal columns, you can use `.col-4` for each one (because 3 x 4 cols each = 12). Or you can set different sizes for them. Here are some examples:
```html
<div class="row">
  <div class="col-6">
    ...
  </div>
  <div class="col-6">
     ...     
  </div>
</div>

<div class="row">
  <div class="col-5">
    ...
  </div>
  <div class="col-7">
     ...     
  </div>
</div>

<div class="row">
  <div class="col-3">
    ...
  </div>
  <div class="col-4">
     ...     
  </div>
</div>

<div class="row">
  <div class="col-6">
    ...
  </div>
  <div class="col-7">
     ...     
  </div>
</div>
```

If the sum of the `.col` in you row doesn't get up to 12, then they don't fill the whole row. And if it goes beyond 12 then it will move to the next line(it will only display the sum of the fist elements <= 12 on the first line)

## Setting Breakpoints
If you take the example above and want to display it on mobile, you may run into some problems. Displaying 5 columns on mobile will make the content unreadable. In order to have different layouts on different screens you won’t need to write media queries, instead you can use the column breakpoints.

Let's say you want to display, for example, 2 columns one after another vertically on small screens and on the same line bigger screens. You will need to specify the breakpoints where the columns go on the same line.

In our example, we want the columns to arrange horizontally starting with the laptop. The breakpoint for the laptop resolution is `.col-lg`
```html
<div class="row">
  <div class="col-lg">
    ...
  </div>
  <div class="col-lg">
     ...   
  </div>
</div>
```

If you wanted the columns to go on the same line starting with larger mobile phones (>= 576px) you would use `.col-sm`, for tablets (>= 768) `.col-md` and for extra large screens (>= 1200px) `.col-xl`

It is useful to keep in mind that up to the given breakpoint, your columns will align vertically. This is one example of the fact that Bootstrap 4 is mobile-first. The default styling is for mobile devices and you specifically need to write what’s the behaviour for bigger screens. And for the resolutions bigger than your breakpoint they will align horizontally.