# Shape and Color Changing Webpage

This project demonstrates a simple webpage that allows users to interactively change the shape and color of a circle element using HTML, CSS, and JavaScript.

## Introduction

This project showcases a basic example of using HTML, CSS, and JavaScript to create an interactive webpage. The webpage features a circle element that can change its color and shape based on user interactions with buttons.

## Usage

1. Clone the repository or download the source code files.
2. Open the `index.html` file in a web browser.
3. Interact with the "Change Color" and "Change Shape" buttons to see the circle element's appearance change.

## Features

- Change Color: Clicking the "Change Color" button cycles through a predefined list of colors, updating the background color of the circle element.
- Change Shape: Clicking the "Change Shape" button toggles between a circle and a triangle shape for the circle element.

## How it Works

The project consists of three main components:

1. **HTML:** The `index.html` file contains the structure of the webpage, including the circle element and the two buttons.

2. **CSS:** The `style.css` file contains the styling rules for the webpage elements. It defines the appearance of the circle and triangle elements.

3. **JavaScript:** The `script.js` file contains the interactivity logic. It uses JavaScript's `addEventListener` to listen for button clicks and perform the necessary actions to change the color and shape of the circle element.

   - When the "Change Color" button is clicked, the script cycles through a predefined array of colors and updates the background color of the circle element.
   - When the "Change Shape" button is clicked, the script toggles between the circle and triangle shapes by manipulating the CSS class of the shape element.

## HTML

The HTML code creates a container div with a circle div inside it. The circle div has a shape div inside it. The shape div is initially a circle, but can be changed to a triangle by clicking the "change shape" button.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Change Shape and color</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
    <div id="circle">
        <div class="shape"></div>
    </div>
    <button id="color">change color</button>
    <button id="changeShape">change shape</button>
</div>
    <script src = "script.js">
    </script>
</body>
</html>
```

## CSS

The CSS code styles the container div, the circle div, and the shape div. The container div is centered on the page and has a width and height of 500px. The circle div is positioned absolutely inside the container div and has a width and height of 200px. The shape div is positioned absolutely inside the circle div and has a width and height of 100px.

```css
.container{
    text-align: center;
    width: 100vw;
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    gap: 30px;
}
#circle{
    width: 150px;
    height: 150px;
    border-radius: 50%;
    background-color: red;
    text-align: center;
    display: flex;
}
.shape{

    position: relative;
    width: 70px;
    height: 70px;
    background-color: blue;
    z-index: 100;
    margin-top: 40px;
    margin-left: 40px;
   
}
.triangle{
    background-color: transparent;
    position: relative;
    left: 38px;
    top: 40px;
    width: 0;
    height: 0;
    border-bottom: 75px solid blue;
    border-right: 75px solid transparent;
}

```

## JavaScript

The JavaScript code adds event listeners to the "change color" and "change shape" buttons. The "change color" button changes the background color of the circle div to a random color from the Color array. The "change shape" button changes the shape of the shape div from a circle to a triangle and vice versa.

```javascript
        var Color = [
  "red",
  "green",
  "cyan",
  "black",
  "voilet",
  "blue",
  "yellow",
  "purple",
  "orange",
  "lightgreen",
  "lemon",
];
var index = 0 ;
const circle = document.getElementById("circle");
        const shape = document.querySelector(".shape");
        const Changecolor = document.querySelector("#color");
        const changeShape = document.querySelector("#changeShape");
        Changecolor.addEventListener("click",()=>{
          
        if (index === Color.length) {
        index = 0;
  }
        circle.style.backgroundColor = Color[index];
        index++;
        })
        var Tringle = false;
        changeShape.addEventListener("click",()=>{
            if(!Tringle){
                var Shape = document.querySelector(".shape");
                Shape.className = "triangle";
                Tringle = true;
            }
            else{
                var shape = document.querySelector(".triangle");
                shape.className = "shape";
                Tringle = false;
            }
        })
      

```
