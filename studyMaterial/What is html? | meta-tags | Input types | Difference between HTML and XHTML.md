# What is html? | meta-tags | Input types | Difference between HTML and XHTML

What is HTML?
HTML (HyperText Markup Language) is the most basic building block of the Web. It defines the meaning and structure of web content. 

Meta tags are HTML tags used to provide additional information about a page to search engines and other clients. Clients process the meta tags and ignore those they don't support. meta tags are added to the <head> section of your HTML page and generally look like this:
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="description" content="Author: A.N. Author, Illustrator: P. Picture, Category: Books, Price:  £9.24, Length: 784 pages">
    <meta name="google-site-verification" content="+nxGUDJ4QpAZ5l9Bsjdi102tLVC21AIh5d1Nl23908vVuFHs34=">
    <title>Example Books - high-quality used books for children</title>
    <meta name="robots" content="noindex,nofollow">
  </head>
</html>



Input types:
The <input> HTML element is used to create interactive controls for web-based forms in order to accept data from the user; a wide variety of types of input data and control widgets are available, depending on the device and user agent. 
How an <input> works varies considerably depending on the value of its type attribute, hence the different types are covered in their own separate reference pages. If this attribute is not specified, the default type adopted is text.

The available types are as follows:
button A push button with no default behavior displaying the value of the value attribute, empty by default.
checkbox A check box allowing single values to be selected/deselected.
color A control for specifying a color; opening a color picker when active in supporting browsers.
date A control for entering a date (year, month, and day, with no time). Opens a date picker or numeric wheels for year, month, day when active in supporting browsers.
datetime-local A control for entering a date and time, with no time zone. Opens a date picker or numeric wheels for date- and time-components when active in supporting browsers.
email A field for editing an email address. Looks like a text input, but has validation parameters and relevant keyboard in supporting browsers and devices with dynamic keyboards.
file A control that lets the user select a file. Use the accept attribute to define the types of files that the control can select.
hidden A control that is not displayed but whose value is submitted to the server. There is an example in the next column, but it's hidden!
image A graphical submit button. Displays an image defined by the src attribute. The alt attribute displays if the image src is missing.
month A control for entering a month and year, with no time zone.
number A control for entering a number. Displays a spinner and adds default validation. Displays a numeric keypad in some devices with dynamic keypads.
password A single-line text field whose value is obscured. Will alert user if site is not secure.
radio A radio button, allowing a single value to be selected out of multiple choices with the same name value.
range A control for entering a number whose exact value is not important. Displays as a range widget defaulting to the middle value. Used in conjunction min and max to define the range of acceptable values.
reset A button that resets the contents of the form to default values. Not recommended.
search A single-line text field for entering search strings. Line-breaks are automatically removed from the input value. May include a delete icon in supporting browsers that can be used to clear the field. Displays a search icon instead of enter key on some devices with dynamic keypads.
submit A button that submits the form.
tel A control for entering a telephone number. Displays a telephone keypad in some devices with dynamic keypads.
text The default value. A single-line text field. Line-breaks are automatically removed from the input value.
time A control for entering a time value with no time zone.
url A field for entering a URL. Looks like a text input, but has validation parameters and relevant keyboard in supporting browsers and devices with dynamic keyboards.
week A control for entering a date consisting of a week-year number and a week number with no time zone.

HTML stands for Hypertext Markup Language, whereas XHTML stands for Extensible Hypertext Markup Language. XHTML is basically an extension of HTML, which is stricter than HTML. 
For example: HTML is SGML based; whereas XHTML is an XML-based language. HTML is not a case-sensitive language; XHTML is a case-sensitive language. HTML empty elements do not require a closing tag at the end, not even a "/" symbol to signify the end of the tag; XHTML empty elements must always be closed; that is, there must be a "/" symbol at the end of the empty element.

Sources: https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input, https://developer.mozilla.org/en-US/docs/Web/HTML, https://developers.google.com/search/docs/crawling-indexing/special-tags, https://www.scaler.com/topics/difference-between-html-and-xhtml/ 

Data-attributes in HTML: 
HTML is designed with extensibility in mind for data that should be associated with a particular element but need not have any defined meaning. data-* attributes allow us to store extra information on standard, semantic HTML elements without other hacks such as non-standard attributes, or extra properties on DOM.

The syntax is simple. Any attribute on any element whose attribute name starts with data- is a data attribute. Say you have an article and you want to store some extra information that doesn't have any visual representation. Just use data attributes for that:

<article
  id="electric-cars"
  data-columns="3"
  data-index-number="12314"
  data-parent="cars">
  ...
</article>


Source: https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes
  
Input types | Accessibility | Semantic HTML 

Semantics refers to the meaning of a piece of code — for example "what effect does running that line of JavaScript have?", or "what purpose or role does that HTML element have" (rather than "what does it look like?".)
In HTML, for example, the h1 element is a semantic element, which gives the text it wraps around the role (or meaning) of "a top level heading on your page."

<h1>This is a top level heading</h1>


By default, most browser's user agent stylesheet will style an h1 with a large font size to make it look like a heading (although you could style it to look like anything you wanted).

On the other hand, you could make any element look like a top level heading. Consider the following:

<span style="font-size: 32px; margin: 21px 0;">Not a top-level heading!</span>


This will render it to look like a top level heading, but it has no semantic value, so it will not get any extra benefits as described above. It is therefore a good idea to use the right HTML element for the right job.

HTML should be coded to represent the data that will be populated and not based on its default presentation styling. Presentation (how it should look), is the sole responsibility of CSS.

Some of the benefits from writing semantic markup are as follows:
-Search engines will consider its contents as important keywords to influence the page's search rankings (see SEO)
-Screen readers can use it as a signpost to help visually impaired users navigate a page
-Finding blocks of meaningful code is significantly easier than searching through endless divs with or without semantic or namespaced classes
-Suggests to the developer the type of data that will be populated
-Semantic naming mirrors proper custom element/component naming

A few semantic elements: <article>, <aside>, <details>, <figcaption>, <figure>, <form>, <footer>, <header>, <main>, <mark>, <nav>, <section>, <summary>, <time>

Source: https://developer.mozilla.org/en-US/docs/Glossary/Semantics 



