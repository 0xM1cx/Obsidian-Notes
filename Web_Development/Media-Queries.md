```toc
```

## What are Media Queries?
These days websites are responsive, meaning they adjust based on the screen size. Making them look pleasing to the eyes and easy of use. We call this **website mobile-friendly**. 

The variable styling of the webpage for different screen sizes is implemented using the **CSS media queries**

A **media query** consists of two components, they are:
- **media-type**: It tells the browser <u>what kind of media</u> this code is for, such as *screen* or *print*
- **expression**: It is used to provide a condition for a particular media feature such as *device width* or *screen resolution*. The media expression will either return **true** or **false**. If the expression/s is true then the CSS defined in the media query block gets executed.

Syntax:
```css
@media not|only mediatype and (expression){

}
```

## Adding breakpoints for different screen sizes
When we create a webpage, we test it on various browsers and different screen sizes. Google recommends following the **mobile-first approach**, which means the website should be developed for mobile devices first then moved to desktop and big screens.

### What is a breakpoint?
A **breakpoint** is nothing but the width of the screen where the style changes. We can define multiple breakpoints while writing our CSS code.

**Syntax to add a breakpoint:**
```css
@media (min-width|max-width: {value in px}){
	selector {
		/*CSS property*/
	}
}
```

### Common Device Sizes
1. **Extra small screens**
For extra small devices such as mobile phones or other devices having screen size **600px** and less.
```css 
@media(max-width: 600px){
	selector {
		/*CSS properties*/
	}
}
```
2. **Small screens**
For small devices such as portrait tables and large phones having screen size **600px** and more.
```css
@media(min-width: 600px){
	selector {
		/*CSS property*/
	}
}
```
3. **Medium screens**
For medium devices such as landscape tables having screen size **768px** and more.
```css
@media only screen and (min-width: 768px){
	selector {
		/*CSS property*/
	}
}
```
4. **Large screens**
For large devices such as laptops and desktops having screen sizes **992px** and above.
```css
@media only screen and (min-width: 992px){
	selector {
		/*CSS property*/
	}
}
```
5. **Extra Large screens**
For extra-large devices such as large laptops and desktops having screen sizes **1200px** and more. 
```css
@media only screen and (min-width: 1200px){
	selector{
		/*CSS property*/
	}
}
```

## Hiding elements using media queries
