#### Basic information about elements
```html
# Element is an essential unit of HTML
<p>Hello World!</p> 

# The body
<body>

</body>

# Example of HTML structure
<body>
	<h1>HELLO WORLD!</h1>
	<p>This sentence is the child of body paragraph</p>
	<div>
		<p>This sentence is a child of div paragraph and grandchild of body paragraph.</p>
	</div>
</body>

# Headings 
<h1> <h2> .. <h6>

# Division: Seperate into different sections
<div>
  <p>This is one sentence in this section</p>
  <p>Remember to 2 space for each element after div</p>
</div>

# Attributes: In the opening tag and can be used in different ways
# Example
<div id ='intro'>

</div>

# <p> contain a block of plain txt
# <span> contains short pieces of text or other HTML. Usually used for inline text that needed to be seperate in a paragraph

<em>Italic text</em>
<strong>Bold Text</strong>

<p>Line break<br>, and it only have starting tag</p> 

# Unordered list 
<ul>
  <li>Object 1</li>
  <li>Object 2</li>
</ul>

# Ordered list
<ol>
  <li>Object 1</li>
  <li>Object 2</li>
</ol>

# <img> is a self-closing tag
<img src="image-location.jpg" alt="Description of picture" />

# Video with controls (play, pause)
<video src="myVideo.mp4" width="320" height="240" controls>  
  Video not supported  
</video>

```

#### HTML Document Standards
```html
<!--Comment-->
<!DOCTYPE html> <!--This Declaration is very important-->
<html>
  <head>
    <title>My Coding Tutorial</title>
  </head>
  <body>
    <a href="https://www.wikipedia.org/">This Is will open a new window</a>
    <a href="https://www.wikipedia.org/" target="_blank">This Link open in a new tab</a>
    <a href="./contact.html">This Contact page is in the root directory</a>
  </body>

</html>

# Picture contain link
<a href='./link.html' target='_blank'><img src='picture.jpg' alt='Description'/><a>

# Link to section
<body>
  <div id='intro'>
    <p>Paragraph 1</p>
  </div>
  <div>
    <ul>
      <a href="#intro"><li>Description</a></li>
    <ul>
  </div>
</body>
```

#### Tables
```html
<table>
  <thead>
	  <tr> <!--Rows is <tr>-->
	    <th scope="col">Header for 1st cell</th>
	    <th scope="col">Header for 2nd cell</th>
	    <th scope="col">Header for 3rd cell</th>
	  </tr>
  </thead>
  <tbody>
	  <tr>
		<th scope="row">Header for this row</th>
	    <td colspan="2">Cell 1</td> <!--colspan is for spanning a cell into more cells, means it takes more cell-->
	    <td rowspan="2">Cell 2</td><!--colspan is for spanning a cell into more cells, means it takes more rows-->
	    <td>Cell 3</td>
	  </tr>
  </tbody>
  <tfoot>
	  <tr>
	    <td>Cell 1 Last</td>
	    <td>Cell 2 Last</td>
	  </tr>	
  </tfoot>
</table>
```
border ([[CSS 101|css]])
```css
table, td {  
  border: 1px solid black;  
}

th {
  border: 1px solid blue;
}
```

### Selecting Web Fonts using <link>
- Related to [[CSS 101|css]]
```html
<head>
	<link href="https://fonts.googleapis.com/css2?family=Roboto+Slab:wght@500&display=swap" rel="stylesheet">
</head>
```

^e013d1

```css
p {
	font-family: 'Roboto Slab', sans-serif;
}
```
