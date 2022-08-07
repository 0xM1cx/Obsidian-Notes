```toc
```
## Text-Shadow
The CSS `text-shadow` property is used to add shadow to the text. The shadow property adds a **3D effect** to the text.

The `text-shadow` effect is generally used for headings to make the text stand out if it is written on some background image.

***Syntax***
```css
text-shadow: [x-offset] [y-offset] [blur] [color];
```

The shadow effect is specified using a combination of **x and y offset** from the element, **blur radius**, and **color**. 

***x-offset*** -> It specifies the position of the shadow on the x-axis. If we supply a **positive value** then the direction of the shadow will be towards the right of the text and negative will be towards the left.
***y-offset*** -> It specifies the position of the shadow on the y-axis. If we specify a **positive value** then the position of the shadow will be towards the bottom of the text and if we specify a **negative value** then the shadow will be towards the **top of the text**
***blur*** -> It specifies how blurry the shadow should be. The higher the value the more blurry the shadow will be. Its **default** value is 0, which means **no blur**.
***color*** -> It specifies the color of the shadow. The **default** color is **black**.

## Multiple Text Shadow
CSS allows us to add multiple shadow effects on text using the `text-shadow` property. There is nothing tricky in this. We just have to add multiple values to the `text-shadow` property and **separate** each pair of value using a comma.

Syntax:
```css
text-shadow: value1, value2;
```
```css
<!-- Example -->
h1{

text-shadow: 3px 3px 5px #4535AA, 5px 5px 5px #FFB643;

}
```

## Adding shadow effect using `box-shadow`
### Horizontal offset
It specifies the horizontal position of the shadow along the x-axis. If we specify a **positive value** then the direction of the shadow will be towards the **right of the text**, and if we specify a **negative value** then the direction of the shadow will be towards the **left of the text**

### Vertical offset
It specifies the vertical position of the shadow along the y-axis. If we specify a **positive value** then the position of the shadow will be towards the bottom of the text and if we specify a **negative value** then the shadow will be towards the **top of the text**

### Blur radius
If the value is set to 0 then the shadow will be sharp or solid. The larger the value the more blurry and bigger the shadow will be. If the value is not specified then it will be 0 by default. **Negative Values are not allowed**

### Spread radius
The positive value will increase the size of the shadow and the negative value will shrink the size of the shadow. The default value is 0 and the size of the shadow will be equal to the size of the element.

### Color
We can specify the color using **Hex**, **RGB**, **RGBA**, and color names.

### Specifying values for multiple effects
If we want to specify more than one shadow effect then separate the list of values using a **comma**
```css
box-shadow: 2px 2px 5px red, 3px 3px 6px pink;
```