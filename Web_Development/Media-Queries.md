```toc
```

## What are Media Queries?
These days websites are responsive, meaning they adjust based on the screen size. Making them look pleasing to the eyes and easy of use. We call this **website mobile-friendly**. 

The variable styling of the webpage for different screen sizes is implemented using the **CSS media queries**

A **media query** consists of two components, they are:

- **media-type**: It tells the browser <u>what kind of media</u> this code is for, such as *screen* or *print*
- **expression**: It is used to provide a condition for a particular media feature such as *device width* or *screen resolution*

Syntax:
```css
@media not|only mediatype and (expression){

}
```