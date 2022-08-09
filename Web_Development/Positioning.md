```toc
```
## Introduction to Positioning
Elements are rendered on a web page in the same order as they are placed in HTML code. By default, the elements are positioned in the browser from **left to right** and **top to bottom**.

Nonetheless, proper positioning of elements on a webpage is important. CSS offers the `position` property that allows the change in default position.

These are the 5 different position values that can be used to position an element on the webpage. Each of these values will change the **position and view** of the elements differently:
```css
position: static;
position: relative;
position: absolute;
position: fixed;
position: sticky;
```

After specifying the `position` property, the elements can then be positioned using `top`, `left`, `right`, and `bottom` property. These properties will now work if the `position` property is not set.
**Example**
```css
.abs {
	position: absolute;
	top: 80px;
	right: 0;
}
```

## Static position
The `static` position value is the **default value**. The elements that are positioned using static value are **rendered according to the normal position**. This value does not affect the default position of the element.

> **NOTE**: Statically positioned elements are also not affected by the `top`, `left`, `bottom`, and `right` properties.

## Relative position
This position value means that the **element is relative to its normal position**. If the element's position is set with the value of `relative` and do not use the properties `left`, `right`, `top`, or `bottom` then there is no effect on the element's position.

**Let's take an example**
```html
<!doctype html>
<html>
	<head>
		<style>
			.move {
				position:relative;
				top:10px;
				left:100px;
			}
		</style>
		<title>Position Relative</title>
	</head>
	<body>
		<div class="move">Where is the party tonight!</div>
	</body>
</html>
```
OUTPUT:
![[Pasted image 20220807154317.png]]
In the above code it will move the `<div>` element with the class move, **10px towards the bottom**. Because it will move **10px away from the top** and **100px towards the right** 

## Absolute
This position value allows us to place an element exactly where we want to place it. The position attributes `top`, `bottom`, `right`, and `left` are used to specify the exact position of the element.

If the `absolute` value is used then the element will position itself like there's no other elements present and this will cause other elements to overlap with the `absoluted` positioned element.

Example, if we provide the `top` and `left` properties a value of 0 then it will the element `h1` to the top-left corner of its parent element or browser window.
``` css
h1 {
	position: absolute;
	top: 0; 
	left: 0;
	
}
```

## Fixed
With this value, elements position themselves **relative to the view-port or browser window** and **not relative to the parent element or its siblings**

There can be many use cases for this property, like a fixed navigation bar, fixed sidebar which doesn't move even when the page is scrolled.

## Sticky
In the case of position value `sticky`, an element gets positioned based on the user's scroll position.

The value sticky consists of the **functionality of both relative and fixed positioning**. The element is positioned relative until it meets the specified position value and then the element sticks at that position.
