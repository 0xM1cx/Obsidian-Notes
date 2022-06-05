# HTML Page Structures
As we know any HTML page must have a `!Doctype` declaration, opening and closing `<html>` tag, head section, body section, title tag inside the head.

## Start from the Top
As our HTML structure is ready, now it's time to build our Web Portfolio.

When start building a website, to make the layout that you want easy to understand always start from the top, left to right. That way when styling the elements it won't get scattered.

[put a sample of your code here]



# Divine Separation
## Deep dive into `<div>`
This tag is widely used for creating sections of information and style them. One more very important point to remember, one pair of `<div>` can be enclosed inside another.

## Span
What does the `<span>` tag do? Nothing! But that's the beauty of it. `<span>` is an inline element/tag, which has no special feature of its own. 

There are many other inline elements present like `<b>` for making text bold, `<i>` for making the text italic etc.

---
### Inline Elements
1. These tags doesn't start from a new line.
2. They take only that much of width which is required by the content inside them.

The best use of `<span>` is to add style, without affecting anything because it doesn't have its own character.

**For example**: You can add style to any HTML tag, but every tag brings in a special default behaviour like `<h1>` which will make the text heading, `<p>` will make it a paragraph, `<table>` is for making a table, but `<span>` does nothing.

So when you want to add just a little style to any text without affecting any other thing, just surround the text with opening and closing `<span>` and use the `style` attribute.

---
#### Difference Between SPAN and DIV
As we have already learnt that `<div>` is a block-level element whereas `<span>` is an inline element. And we have studied the differences too, now lets practically see the difference.

We will be focusing on the following two features:
1. `<div>` always starts with new line, while `<span>` doesn't.
2. `<div>` takes on the full available width while `<span>` doesn't.

```html
<!doctype html>

<html>

    <head>

        <title>My Webpage Title</title>

    </head>

  

    <body>

        I like Cats.

        <span style="background-color: red">span tag used here</span>

        <div style="background-color: yellow">

        div tag used here

        </div>

    </body>

</html>
```

![[Pasted image 20220605122123.png]]