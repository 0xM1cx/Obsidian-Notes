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
```css
<!doctype html>
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