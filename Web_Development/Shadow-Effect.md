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