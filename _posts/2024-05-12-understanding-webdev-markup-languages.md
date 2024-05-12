---
layout: post
date: 2024-05-12 21:00:00 +1000
title: 4. Understanding Web Development Markup Languages
---

A Markup language is a method for defining the layout of information on a website or a digital document. Information refers to text and images, and layout refers to how this information are displayed to a user. 
Often people think markup language is a programming language, but it’s not. A programming language executes a specific set of functions, whereas a markup language focuses on the formatting, structure and the look of a website.

<ul>
<li>HTML5 (hypertext markup language)</li>
<li>XML (extensible markup language)</li>
<li>XHTML (extensible hypertext markup language)</li>
<li>SGML (standard generalized markup language)</li>
<li>KML (key whole markup language)</li>
<li>MathML (mathematical markup language)</li>
<li>Markdown language</li>
</ul>

In today’s programming world, HTML5 and Markdown are extensively used.  

#### Important components of markup language
Taking HTML as the primary markup language for this essay, the 3 main components are:
<ol>
<li>Elements</li>
<li>Attributes</li>
<li>Text</li>
</ol>

**Elements** are the building blocks and determine the structure and content of a website. It tells a web browser how the content of a webpage should be displayed.  

All markup languages have an opening tag (<) and a closing tag (> and />), within which is specified the content or the information. 

A web document begins with:
<ul>
<li>A Root element, represented as <html> and ends with </html>. The complete structure of the webpage is contained within.</li>
<li>A Head element, represented as <head> and ends with </head>. This is not seen by the user and contains information related to the web page in question, which are used by other web designers to understand what the page is about.</li>
<li>A Title element, represented as <title> and ends with </title>, aims at giving a name to the page, which is seen by a user on the browser tab of their computer. It’s basically a label. </li>
<li>A Body element, represented as <body> and ending with </body>, sits outside the Head and Title elements, but within the main Root element (<html>), and all the design layout is specified here, which eventually will be seen by a user.</li>
</ul>

```html
<html>
    <head>
        <title>
            Demonstrating the structure of a web document
        </title>
    </head>

    <body>
        <p>
            I am writing a small sentence here to show you how paragraph works!
        </p>

        <p>
            If you want to check a website, check out <a href="https://emanoj1.github.io/"> Manoj's code blog! </a>
        </p>
    </body>
</html>
```

In the above example, “p” refers to the beginning of a paragraph. The content that it contains, starts a new line.  

The < a > is an Anchor element that lets you link an external website, and as seen above it’s nested inside another < p > tag.  

The other common and important elements are:

<ul>
<li>Headings (h1, h2, h3, h4, h5, h6)</li>
<li>List (ordered and unordered, basically bullet or numbered points)</li>
<li>Image (to upload images)</li>
<li>Navigation (used for a list within a menu)</li>
<li>The div (used as a generic container) for a specific section</li>
<li>Footer (the bottom-most part of a webpage or an HTML doc)</li>
</ul>  
