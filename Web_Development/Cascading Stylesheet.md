```toc
```
## Box Model

> [!NOTE] Own Words
> The box model is used to help visualize the different section of an HTML element.

#### What is a box model?
Every element created in HTML is considered a box. The Box Model is used to describe the structure of any HTML element on a web-page and how they are rendered on the web-page. It represents the various section of an HTML element. These sections are:
![The CSS Box Model. The CSS box model describes the design… | by Jacob Kagon  | Medium](data:image/png;base64,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)
+ **Content** - This area is where the content of the element is displayed which can be an image or text, etc.
+ **Padding** - It specified the space between the *border* and the *content* of the box.
+ **Border** - It specifies area present around the content box(i.e. the boundary of the element)
+ **Margin** - It specifies the space outside the border of the element, between the current element and other adjacent HTML element.
## The Content Box
The content area is a dedicated section for the ***element's content***. The images, text, or any other media of any element are displayed within the content area. The measurements of the content area are specified using the CSS `height` and `width` properties. Syntax for height and width: 
`height: auto | length | percentage | initial | inherit;width: auto | length | percentage | initial | inherit;`
`width: auto | length | percentage | initial | inherit;width: auto | length | percentage | initial | inherit;`
+ **auto**: This is the *default* value. This means the HTML element will automatically take a height/width based on the requirement of the content in it.
-   **length**: We can also specify the value for height/width in *px*, *inch*, *em*, etc.
-   **%**: We can also specify the value for height/width as percentage values. For example, 50% width means, the HTML element will take a width of 50% of the total width available to it.
-   **initial**: This specifies the value to its default value.
-   **inherit**: If you want an HTML element to take the value of its element, then this value can be used.

NOTE] Reminder
> While most of the HTML element behaves properly with `height` and `width` CSS property, one should be **careful while using these properties with images**, as setting the wrong ratio can **distort your image**
> 
> When working with an image size one must set the other (either height or width to auto). E.g. when setting an images' height you must set the width to auto to adjust per aspect ration 

## Margin
The CSS `margin` property is used to add the blank space around any HTML element or outside the element's border. Syntax: 
```css
margin: value in px, em or % | inherit
```
###### Shorthand
The margin property can take values in negative if we want to overlap elements or want to reduce the space between two elements. The margin property can have four values which indicate *top*, *bottom*, *right* and *left*. If four values are specified, the first value applies to the top margin, the second will be to the right and left while the third value applies to the bottom margin. Lastly, if only two values are specified; the first value will apply to the top and bottom margin and the second value will apply to the left and right margin. E.g. ```margin: 20px 40px;```

> [!NOTE] Note!
> Elements have a default value which varies in size. If you want to reset all margins to zero and then add your own margins, you can use a wildcard rule like `margin: 0;` to clear all margins.
## Padding
The CSS `padding` property is used to add the extra space *between the content and the border of the element.* The added space has no background color, but if we specify the background color for that element then it is applicable on the padded space too. Syntax: `padding: value in px, em or % | inherit`. This property *cannot take* values in *negative* like the `margin` property. Padding also has a shorthand property just like margin [ShortHand Value Margin](#shorthand).
## Border
CSS offers a variety of properties that allows us to customize the border accordingly such as color, width, style, etc. Syntax: `border: <width> <style> <color>;`
The CSS `border` is a shorthand property for the `border-width`, `border-style`, and `border-color` properties. We can also set these properties individually.
- `border-width`: This  property specifies the *thickness* of the border.
- `border-style`: This property specifies the *pattern* of the border. This can be solid, dotted, dashed, etc.
- `border-color`: This property specifies the *color* of the border.
E.g. ```border: 20px solid blue```

### Box-Sizing
In the CSS box model, when we specify the `height` and `width` property along with `border` or `padding` to the content box then it ***will add extra length to the height and width*** and ***increase the size of the box.***
The total length can be measured as: 
*height + width + padding + border = actual length*

To overcome this problem, the `box-sizing` property was introduced. The CSS `box-sizing` property decides whether to include the length of the *padding* and *border* into the total length of height and width, or not. 
Syntax: ```box-sizing: content-box|border-box|initial|inherit;```
The value  *content-box* is the default value and it means that the *width and height will include only the content*, while the border and padding will not be included. Whilst the value *border-box* specifies that the width and height properties will include the content, padding and border of the element.

## [[CSS Borders]]

## [[CSS Display Property]]

## [[Styling Images]]

## [Shadow Effect](Web_Development/Shadow-Effect)

## [Positioning](Web_Development/Positioning)

## [Media Queries](Web_Development/Media-Queries)

## [Transitions](Web_Development/Transitions)
