# HTML Notes
## March 21, 2023 - 18:24 PM
- HTML is the structure of a website
- CSS is the design of the website
- JS is the function of the website
- <code>\<br></code> break line 
- <h1> heading h1
- <h2> heading h2
- <h3> heading h3
- <h4> heading h4
- <h5> heading h5
- <h6> heading h6
-  <code>\</h3></code> to end a specific tag
- <code>\<hr></code> horizontal rule
- <code>\</hr size="3"></code> to specify the size of the horizontal rule
- <code>\<center></code> center align text or heading
- <code>\<meta charset="UTF-8"></code> declares the character encoding of the page or script.
## March 22, 2023 - 20:02 PM
- <code>\<em>Example\</em></code> this will change the text to <em>italic</em>
- <code>\<strong>Example\</strong></code> this will change the text to <strong>bold</strong>
- <code>\<ul></code> to create a un-ordered list in html
- <code>\<ol></code> to create an ordered list
- <code>\<li></code> list item inside an ordered or unorderd list
- <code>\<img src="www.google.com/example.jpg" alt="an example photo"></code> how to insert a photo from the internet into a html
- <code>\<img src="example.jpg" alt="an example photo"></code> how to insert a photo from the local directory into a html
- <code>\<a href="www.google.com">google\</a></code> this is to create a link to google
- <code>\<a href="hobbies.html">click here\</a></code> this is to create a link to a local html file called hobbies
## March 23, 2023 - 06:11 AM
- <table>
            <thead>
                <tr>
                    <th>Create</th>
                    <th>Table</th>
                </tr>
            </thead>
  </table>            
- <code>\<tr></code> this is to create a table row
- <code>\<td></code> this is the text to be created into table row
- <code>\<table cellspacing="20"></code> creates some space around the cell in a table
## March 26, 2023 - 06:58 AM
- **<code>\<form class= "" action=""
    <br>\<label>Your Name:</label>
    <br>\<input type="text">
    <br>\<input type="password">
    <br>\<input type="submit">
<br>\</form></code>** - *creating a contact us page with input examples*
- **<code>\<textarea name="name" rows="10" cols="30">\</textarea></code>** - *create a text input area on a html website*
- **<code>\<form class= "" action="mailto:example@gmail.com" method="post"></code>** -*will open a default email application and set the mail to address as example@gmail.com once submit has been clicked*
## March 27, 2023 - 16:46 PM
- <code>\<span> class = "example">example\</span></code> -*is a common inline element and will open span the width of the text*
- Other common inline elements include images (\<img>) and (\<a>) anchors  
- Some examples of block elements by default are (\<p>) paragraph and (
\<h1>) headings. 
- This can be changed by setting the "display" to "inline-block"
## March 28, 2023 - 05:29 AM
- Static and relative positioning
- **Position static** -*all elements by default are static*
- **Position relative** <code> img{position: relative; left: 30px;}</code>-*the element will be placed to the right 30px of the default static image, because it will create space/margin on the left-hand side*
## May 16, 2023 - 05:35 AM
Bootstrap notes
````
<title>Bootstrap Components</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha2/dist/css/bootstrap.min.css" rel="stylesheet"
    integrity="sha384-aFq/bzH65dt+w6FI2ooMVUpc+21e0SRygnTpmBvdBgSdnuTN7QbdgL+OapgHtvPp" crossorigin="anonymous">
````
- Setting up a bootstrap connection on the HTML page
 ```` 
 <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha3/dist/js/bootstrap.bundle.min.js" integrity="sha384-ENjdO4Dr2bkBIFxQpeoTz1HIcje39Wm4jDKdf19U8gI4ddQ3GYNS7NTKfAdVQSZe" crossorigin="anonymous"></script>
 ````
 - Connecting the javascript onto the HTML page
 
 ````Notation
Spacing utilities that apply to all breakpoints, from xs to xl, have no breakpoint abbreviation in them. This is because those classes are applied from min-width: 0 and up, and thus are not bound by a media query. The remaining breakpoints, however, do include a breakpoint abbreviation.

The classes are named using the format {property}{sides}-{size} for xs and {property}{sides}-{breakpoint}-{size} for sm, md, lg, and xl.

Where property is one of:

m - for classes that set margin
p - for classes that set padding
Where sides is one of:

t - for classes that set margin-top or padding-top
b - for classes that set margin-bottom or padding-bottom
l - for classes that set margin-left or padding-left
r - for classes that set margin-right or padding-right
x - for classes that set both *-left and *-right
y - for classes that set both *-top and *-bottom
blank - for classes that set a margin or padding on all 4 sides of the element
Where size is one of:

0 - for classes that eliminate the margin or padding by setting it to 0
1 - (by default) for classes that set the margin or padding to $spacer * .25
2 - (by default) for classes that set the margin or padding to $spacer * .5
3 - (by default) for classes that set the margin or padding to $spacer
4 - (by default) for classes that set the margin or padding to $spacer * 1.5
5 - (by default) for classes that set the margin or padding to $spacer * 3
auto - for classes that set the margin to auto
````
- To change the whole website to Dark mode use the following code.
````
<!DOCTYPE html>
<html lang="en" data-bs-theme="dark">
````

