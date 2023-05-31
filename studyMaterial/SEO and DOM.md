# SEO and DOM

SEO (Search Engine Optimization) is the process of making a website more visible in search results, also termed improving search rankings.
Search engines crawl the web, following links from page to page, and index the content found. When you search, the search engine displays the indexed content. Crawlers follow rules. If you follow those rules closely when doing SEO for a website, you give the site the best chances of showing up among the first results, increasing traffic and possibly revenue (for e-commerce and ads).
Search engines give some guidelines for SEO, but big search engines keep result ranking as a trade secret. SEO combines official search engine guidelines, empirical knowledge, and theoretical knowledge from science papers or patents.
SEO methods fall into three broad classes:
Technical: Tag the content using semantic HTML. When exploring the website, crawlers should only find the content you want indexed.
Copywriting: Write content using your visitors' vocabulary. Use text as well as images so that crawlers can understand the subject.
Popularity: You get most traffic when other established sites link to your site.

The Document Object Model (DOM) is the data representation of the objects that comprise the structure and content of a document on the web.
The DOM is a programming interface for web documents. It represents the page so that programs can change the document structure, style, and content. The DOM represents the document as nodes and objects; that way, programming languages can interact with the page.
A web page is a document that can be either displayed in the browser window or as the HTML source. In both cases, it is the same document but the Document Object Model (DOM) representation allows it to be manipulated. As an object-oriented representation of the web page, it can be modified with a scripting language such as JavaScript.
The DOM is built using multiple APIs that work together. The core DOM defines the entities describing any document and the objects within it. This is expanded upon as needed by other APIs that add new features and capabilities to the DOM.

Fundamental data types:

Document: When a member returns an object of type document (e.g., the ownerDocument property of an element returns the document to which it belongs), this object is the root document object itself. The DOM document Reference chapter describes the document object.
Node: Every object located within a document is a node of some kind. In an HTML document, an object can be an element node but also a text node or attribute node.
Element: The element type is based on node. It refers to an element or a node of type element returned by a member of the DOM API. Rather than saying, for example, that the document.createElement() method returns an object reference to a node, we just say that this method returns the element that has just been created in the DOM. element objects implement the DOM Element interface and also the more basic Node interface, both of which are included together in this reference. In an HTML document, elements are further enhanced by the HTML DOM API's HTMLElement interface as well as other interfaces describing capabilities of specific kinds of elements (for instance, HTMLTableElement for <table> elements).
NodeList: A nodeList is an array of elements, like the kind that is returned by the method document.querySelectorAll(). Items in a nodeList are accessed by index in either of two ways:
list.item(1)
list[1]
These two are equivalent. In the first, item() is the single method on the nodeList object. The latter uses the typical array syntax to fetch the second item in the list.
Attr: When an attribute is returned by a member (e.g., by the createAttribute() method), it is an object reference that exposes a special (albeit small) interface for attributes. Attributes are nodes in the DOM just like elements are, though you may rarely use them as such.
NamedNodeMap: A namedNodeMap is like an array, but the items are accessed by name or index, though this latter case is merely a convenience for enumeration, as they are in no particular order in the list. A namedNodeMap has an item() method for this purpose, and you can also add and remove items from a namedNodeMap.



Sources: https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction, https://developer.mozilla.org/en-US/docs/Glossary/SEO 
