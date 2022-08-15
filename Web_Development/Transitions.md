```toc
```
## What is CSS transition?
CSS offers the `transition` property which is used to change the state of an element smoothly.

This is good because instead of changing the style state of an element suddenly like on `hover`, we can change the state of the HTML element smoothly, in the form of transition animation.

To implement the `transition` effect on HTML elements, we need to specify two things:
- the property on which you want to add the transition effect.
- the duration of the effect.

> **NOTE:** If we don't specify the duration time, then the transition will not happen, or it will happen but we won't be able to see it because it will happen instantaneously, as the **default duration time**

### What is state change?
When you want to change the state of an element, example changing the background color of the `div`. Some do this with the `hover` property, when a mouse hover over that `div` the background color changes instantly. With the `transition` property we can change the color or other CSS properties of an element in intervals(smoothly). 

**Example use case of transition**
```css
div {
	width: 100px;
	height: 100px;
	background: #ac66cc;
	transition: width 2s, height 4s;
}

div:hover {
	width: 300px;
	height: 300px;
}
```

## transition-property
This property is used to specify on which CSS property we want to apply the transition. The properties specified as the value of the `transition-property` are animated during the transition.

This is useful when you are changing multiple CSS properties for an element, e.g. on `hover`, but you want only a certain property to change smoothly during the transition.

**Syntax**
```css
transition-property: (none | all | property | initial | inherit);
```

- **none** - means that the transition is not applied on any property.
- **all** - means that it will be applied on all the style properties that change.
- **property** - this is used to specify a particular property, we can provide its name as the value for the `tranistion-property`.

Say we want to apply a transition effect to the `width` of an element. First set the value of the `transition-property` to `width`. And we will provide the updated `width` value in the changed state CSS, for example on hover.

**Example**
```css
.effect {
	transition-property: font-size;
	transition-duration: 6s;
	color: #4535aa;
		}
.effect:hover {
	font-size: 30px;
}
```

