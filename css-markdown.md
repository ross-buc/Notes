<h1> CSS Notes </h1>
<h2>March 26, 2023 - 11:42 AM</h2>

- Cascading Style Sheets <br>
- <code>\<body style="background-color: #BDCDD6;"></code> *-how to set the background colour of a html site using inline CSS*
- <code>\<link rel="stylesheet" href="/css/styles.css"></code> *-create a link to the styles css sheet where we can store all design params*
- implement all of the style changes for a website within the styles.css file. Not within the html index
- **selector{property:value;}** - Who? What? How? ex. <code>h1{color:red;}</code>
- <code>\/*</code> - if you want to comment out a section of code in css then <code>\*/</code> to close the comment out section
- <code>\.example</code> - tap into a class called example and be able to apply different styles to that class specifically 
- <code>\#example</code> - tap into an ID called example and be able to apply different styles to that ID specifically 
- Class and ID selectors over-ride the default style settings
- ID selectors must be unique
- Class selectors can be used for multiple elements
- You can have multiple class on the same HTML element for example <code>\<img class="circular bacon" src="https://www.example.png" width="350" alt="Bacon PNG Image" /></code>
- <code>img:hover {background-color: gold;}</code> This will change the background color when the mouse is hovered on an image
- 