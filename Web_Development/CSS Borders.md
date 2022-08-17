# CSS Borders
A **Border** is a line(solid, dotted, dashed, etc.) or a boundary, created around an HTML element to make it look like its wrapped in a rectangular box.

###### border-style
CSS provides us with multiple values that we can use to change the border style. It can be solid(normal border), dotted lines, dashed lines, or double lines, etc.

*Syntax*
`border-style: none | solid | dotted | dashed | double | groove | ridge | inset | outset;`

When we provide 4 values, the values are considered *clockwise* - **top**, **right**, **bottom**, **left**.
![[Pasted image 20220410140236.png]]
*Providing 4 values*
`border-style: solid dashed double dotted;`

###### border-width
CSS allows us to specify the thinkness of the border using the border-width property. We can set the width in *px*, *cm*, *pt*, etc. Or, we can use the predefined values; which are **thin**, **medium**, and **thick**

> [!NOTE] Reminder
> This property is used with the `border-style` property to adjust the thickness of the border. If you use the `border-width` property alone, nothing will happen.

*Syntax* 
```border-width: thin | thick | medium | value in px,cm, pt, in....```

###### border-color
We can also change the color of the border using the `border-color` property. 
*Syntax*
```border-color: color [color color color];```
We can provide the following values to the `border-style` property:
1. **HEX** value for color.
2. **color name** like red, green, blue, etc.
3. **RGB** or **RGBA** values.

> [!NOTE] NOTE
> This property is used with the `border-style` property to change the color of the border. If you use this property alone nothing will happen.

###### border property
The `border` property is a shorthand property of the following properties.
+ `border-width`
+ `border-style`
+ `border-color`
We can specify the value of all three properties in one property to reduce the CSS code that we write.

*Syntax*
```border: width (in px|cm|%...) style color```

*Example*
```css
#myborder {
	border: dashed 2px purple;
}
```

###### border-radius
The CSS `border-radius` property is used to make the corners of any HTML element rounded. We can use it with images, borders, fieldset, etc. HTML elements, to make their corners rounded. This property can even make an HTML element appear completely circular if we increase the value of `border-radius` property to more than half of the edge of the HTML element.

*Syntax*
`border-radius: length in px, cm, in...`
