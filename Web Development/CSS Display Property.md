# CSS Display Property
The CSS `display` property controls the layout of the elements on a web page. It specifies how the HTML element will be displayed on the screen.

Every HTML element has a default display value whether inline or block, which decides whether they will fall in line with others or they will push others to the next line and occupy the complete line by themselves.

The elements with default display value as in line takes only the amount of horizontal space their content needs such as `<i>`, `<span>`, `<strong>`, etc. While the elements with the default value block take the entire width on the screen such as `<div>`, `<p>`, etc.
![[Pasted image 20220415194729.png]]

## Display Inline
The element with default display value as *inline* take only the amount of  space their content needs like the `<span>` tag, or `<i>` tag or `<b>` tag, etc. The *inline* value places the element side by side or horizontally in the same line.

The elements with inline display value will **not accept any additional styling to change their height or width,** they only take the amount of space their content needs.

Some elements with default **inline** display value are `<img>`, `<span>`, `<textarea>`, `<a>`, etc.

## Display Block
The elements with display value `block` are displayed in a separate line and *take the entire width of the screen* irrespective of the content length.

Some of the HTML elements which have the `display` property with default value as **block** are `<div>`, `<p>`, `<table>`, `<section>`, etc.

Some of the HTML elements which have the `display` property with default value as **block** are `<div>`, `<p>`, `<table>`, `<section>`, etc.

## Display None
The CSS display value **none** removes teh HTML element form the webpage but their code remians present in the HTML document and can be seen in the page source, but that element will neighter occupyp any space nor it will be visible on the webpage.

## Display Inline-block
The CSS display value **inline-block** provides the features of both the **inline** value and the **block** value. The elements with value **inline-block** render themselves as an inline element but also accepts other CSS property like `height` and `width`, because of the block value.

This property is used when we want to **place** the HTML element **side by side** (horizontally) and also **want to set** the **height and width** of the element.

## Visibility hidden
The CSS `visibility` property is also similar to the `display` property. It decied whether the lement will be displayed on the webpage or not.

This property with a value of **hidden** hides the  element from the web page without changin the layout of the element which means the **space occupied** by the element remains on the webpage only the element is hidden. Syntax: `visibility: hidden | vidible | collapse`
**hidden**: This will make the HTML element invidisble, but the element will occupy its space.
**visible**: This will make the HTML element visible.
**collpase**: This will hide an element completely, just like `display: none`, but only if the element is a table element.

