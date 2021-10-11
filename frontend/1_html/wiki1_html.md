# HTML Document Example
Here is an example of HTML code

```doctest
<!DOCTYPE html>

<html>

<head>
    <title>Page Title</title>
</head>

<body>
    <h1>A Photo of a Beautiful Landscape</h1>
    <a href="https://www.w3schools.com/tags">HTML tags</a>
    <p>Here is the photo</p>
    <img src="photo.jpg" alt="Country Landscape">
</body>

</html>
```
## Explanation of the HTML document
As you progress through the lesson, you'll find that the `<head>` tag is mostly for housekeeping like specifying the page title and adding meta tags. Meta tags are in essence information about the page that web crawlers see but users do not. The head tag also contains links to javascript and css files, which you'll see later in the lesson.

The website content goes in the `<body>` tag. The body tag can contain headers, paragraphs, images, links, forms, lists, and a handful of other tags. Of particular note in this example are the link tag `<a>` and the image tag `<img>`.

Both of these tags link to external information outside of the html doc. In the html code above, the link `<a>` tag links to an external website called w3schools. The `href` is called an attribute, and in this case `href` specifies the link.

The image `<img>` tag displays an image called "photo.jpg". In this case, the jpg file and the html document are in the same directory, but the documents do not have to be. The src attribute specifies the path to the image file relative to the html document. The alt tag contains text that gets displaced in case the image cannot be found.

## Full List of Tags and How to Use Them
This is a link to one of the best references for html. Use this website to look up html tags and how to use them. [W3Schools HTML Tags](https://www.w3schools.com/tags/default.asp)

In fact, the [W3Schools website](https://www.w3schools.com/) has a lot of free information about web development syntax.

## Checking your HTML
It's a good idea to check the validity of your HTML. Here is a website that checks your HTML for syntax errors: [W3C Validator](https://validator.w3.org/#validate_by_input). Try pasting your HTML code here and running the validator. You can read through the error messages and fix your HTML.
