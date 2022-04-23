## Set Height and Width
The CSS `height` and `width` property can be used with any HTML element. Yes, you can use it with a `<table>`, `<div>`, `<p>`, or any other **block** or **inline-block** HTML element.

> [!NOTE] <u>NOTE</u>
> While using the `height` and `width` property with an image, we should check the aspect ratio of the image, otherwise, if we provide the height and width value in a different ratio then the image may appear distorted on the webpage.
## Image Round Corners
We can also set round corners using the `border-radius` property. We can use this property without the `border` property being specified. The `border-radius` property is a shorthand for the ff property:
- *border-top-left-radius*
- *border-top-right-radius*
- *border-bottom-right-radius*
- *border-bottom-left-radius*

## float property
By default all the HTML elements are placed on a webpage **starting from the left side** of the page. There are many properties in CSS using which we can change the position of any HTML element on a webpage. One such property is `float`.

Using the `float` property, we can position an HTML element to extreme right side of the webpage(or the parent element) or extreme left of the webpage, using a single property. It makes the element float over every other html element. 
*syntax*: `float: none | left | right`

## Centering an Image
The HTML `<img>` tag is an inline tag, which means it takes only the space required by its content and doesn't take the entire line. To make an image centered on a webpage or inside the parent container, we first have to make the `<img>` tag **block**, using the `display` property.

Once we have made the `<img>` element as **block** element using the `display` property, we can then use the margin property to **set equal margin** on **both the left and right sides** of the image using the **auto** value.
Example is the ff code, which sets the margin at top and the left and right to auto which will take equal margin on both left and right sides.
```
margin 0 auto;
```