# HTML

### Learning Resources

[Learn HTML for Web Development - Studytonight](https://www.studytonight.com/code/html-course/)

> [!NOTE] Reminder
> 💡 Different Between HTML elements and tag HTML Tags refer to the name surrounded by open and closing bracket. E.g. `<body>`. HTML elements on the other hand is nothing but a HTML tag along  with its content. HTML elements are like this `<p> Content </p>.`



# What is HTML?

HTML stands for Hypertext Markup Language and is used to for the website’s content and structure. HTML is the **language in which most websites are written**. HTML is used to create pages and make them functional.

### History of HTML
HTML was first created by Tim <u>Berners-Lee</u>, <u>Robert Cailliau</u>, and others starting in *1989*. It stands for Hyper Text Markup Language.

Hypertext means that the document contains **links that allow the reader to jump to other places** in the document or to another document altogether. The latest version is known as [HTML5](https://html.com/html5/).

A **Markup Language** is a way that computers speak to each other to control how text is processed and presented. To do this HTML uses two things: tags and **attributes**.

### HTML Tags and Attributes

[Tags](https://html.com/tags/) are used to **mark up the start of an HTML element** and they are usually enclosed in angle brackets. An example of a tag is: `<h1>`.

[Attributes](https://html.com/attributes/) contain **additional pieces of information**. Attributes take the form of an opening tag and additional info is **placed inside**. An example of an attribute is:

`<img src="mydog.jpg" alt="A photo of my dog.">`

### Golden Rules to Remember

1. The vast majority of tags must be **opened** (`<tag>`) and **closed** (`</tag>`) with the element information such as a title or text resting between the tags.
2. When using multiple tags, the tags must be **closed in the order in which they were opened**. For example:`<strong><em>This is really important!</em></strong>`

### Tags
- **Body Tag** - This is is where we add the content which is designed for viewing by human eyes. <body></body>
- **Title Tag** — This is where we **insert the page name** as it will appear at the top of the browser window or tab. <title></title>
- **Meta Tag** — This is where information *about* the document is stored: character encoding, name (page context), description. Syntax: `<meta>`
- **Heading Tags** — These are tags to create heading. It automatically adds one line before and after the tag
    - Syntax: `<h1>, <h2>, <h3>, <h4>, <h5>...`
- **Paragraph Tag** — This tag is used to create paragraphs. Syntax: `<p>`
- **Break Tag** — The break tag inserts a single line break and this tag has to closing tag. Whenever you want to change lines add this tag and the text after this tag will come on the next line. This is a good tag because manually spacing content does not work  in html because html ignores spaces.Syntax `<br>`
- **Horizontal Tag** — This tag inserts a horizontal line and this tag also doesn’t have a closing tag. Syntax: `<hr>`
- **Comments** — This tag is ignored and are not displayed in the browser. This can be used to add comments in the HTML document. Syntax: `<!-- comment goes in here -->`

#### Formatting Text

- **Bold Tag** — words or sentences between these tag will appear bold. Syntax: `<b>`
- **Strong Tag** — This works similarly with the bold tag but semantic wise this has an importance set to it, like when someone uses a screen reader the dialogue will say is with more emphasis. Syntax: `<strong>`
- **Italics Tag **— This tag is used to give italics style. Syntax: `<i>`
- **Emphasis Tag** — This tag is used to also give an italic look but just like the strong tag it gives more importance to the information semantically. Syntax: `<em>`
- **Underline Tag **— This tag is used to underline text. Syntax: `<u>`
- **Small Tag** — This tag is used to make text small as compared to others around it. Syntax: `<small>`

**Creating Hyperlink** - It is a link to another resource and the link behind the hypertext

- **Anchor Element** — This used to create a link to another resource (webpage, specific part of the website, file, etc.). Syntax: `<a>`
    - *href attribute* - This attribute unlike other attributes associated with the anchor tag is mandatory. This is used to put/create the hyperlink. <u>href</u> is short for hypertext reference.
- **Image Tag** — This tag is used to add images to your website. This tag is an empty tag like break line and horizontal line tags. Syntax: `<img>`
    - *src* — the source attribute is used to specify the location of the image to be added.
    - *alt* — the alt attribute meas alternatives, this is used to replace the image with text, usually text describing the image, when the an error occurs relating the image that disallows it to be displayed.

Table of elements and their purpose

| Element  | Meaning | Purpose |
| --- | --- | --- |
| `<b>` | Bold | Highlight important information |
| `<strong>` | Strong | Similarly to bold, to highlight key text |
| `<i>` | Italic | To denote text |
| `<em>` | Emphasized Text | Usually used as image captions |
| `<mark>` | Marked Text | Highlight the background of the text |
| `<small>` | Small Text | To shrink the text |
| `<strike>` | Strike Out Text | To place a horizontal line across the text |
| `<u>` | Underlined Text | Used for links or text highlights |
| `<ins>` | Inserted Text | Displayed with an underline to show an inserted text |
| `<sub>` | Subscript Text | Typographical stylistic choice |
| `<sup>` | Superscript Text | Another typographical presentation style |

#### HTML Lists
**Ordered List** — This creates an ordered list in html meaning it has numbers or any other hierarchical system like letters. Syntax: `<ol></ol>`.
There are three attributes for ordered list:
1. reversed
2. start
3. type

Adding **reversed** attribute to the `ol` tag specifies that the list order should be descending.
```html
<ol reversed>
</ol>
```
Adding **start** attribute with a value,specifies the start value for an ordered list.
```html
<ol start="10">
</ol>
```
Adding **type** attribute specifies the type of marker to use for the list items.
```html
<ol type="A">
<ol>
```

**Unordered List** — This is the opposite of the ordered list, this list has symbols that denote no order like bullet points, star, etc. Syntax ```<ul></ul>```

**List item** — This tag is always nested within list, this specify the items in a list. Syntax: `<li></li>`

**Description List** — This tag represents the description of the list. The description list allows you to create a list of terms and then provide one or more descriptions for each term. Syntax: `<dl></dl>` 

## Working with Images
You can include pictures in your web page using HTML `<img>` tag. This is an empty tag and it has `/` just before the closing angular bracket. E.g. 
```html
<img src="Path/to/image" />
```
---

## Introduction to Tables
