# Ex04 Simple Calculator - React Project
## Date: 20-11-2026
## Name : Vaideeshwaran G
## Reg No : 212225240178

## AIM
To  develop a Simple Calculator using React.js with clean and responsive design, ensuring a smooth user experience across different screen sizes.

## ALGORITHM
### STEP 1
Create a React App.

### STEP 2
Open a terminal and run:
  <ul><li>npx create-react-app simple-calculator</li>
  <li>cd simple-calculator</li>
  <li>npm start</li></ul>

### STEP 3
Inside the src/ folder, create a new file Calculator.js and define the basic structure.

### STEP 4
Plan the UI: Display screen, number buttons (0-9), operators (+, -, *, /), clear (C), and equal (=).

### STEP 5
Create a new file Calculator.css in src/ and add the styling.

### STEP 6
Open src/App.js and modify it.

### STEP 7
Start the development server.
  npm start

### STEP 8
Open http://localhost:3000/ in the browser.

### STEP 9
Test the calculator by entering numbers and operations.

### STEP 10
Fix styling issues and refine content placement.

### STEP 11
Deploy the website.

### STEP 12
Upload to GitHub Pages for free hosting.

## PROGRAM
```
Calculator.js

import React, { useState } from "react";
import "./Calculator.css";

function Calculator() {
    const [display, setDisplay] = useState("");

    const handleClick = (value) => {
    if (value === "C") {
    setDisplay("");
    } else if (value === "=") {
    try {
        if (!/^[0-9+\-*/.() ]+$/.test(display)) {
        throw new Error("Invalid");
        }
        setDisplay(String(Function('"use strict"; return (' + display + ')')()));
    } catch {
        setDisplay("Error");
    }
    } else {
    setDisplay(display === "Error" ? value : display + value);
    }
};

const buttons = [
    "C", "/", "*", "-",
    "7", "8", "9", "+",
    "4", "5", "6", "=",
    "1", "2", "3", "0",
    "."
];

return (
    <div className="calculator">
    <h2>React Calculator</h2>
    <input type="text" value={display} readOnly />

    <div className="buttons">
        {buttons.map((btn) => (
        <button
            key={btn}
            onClick={() => handleClick(btn)}
            className={
            btn === "C" ? "clear" :
            btn === "=" ? "equal" :
            ["+", "-", "*", "/"].includes(btn) ? "operator" : ""
            }
        >
            {btn}
        </button>
        ))}
    </div>
    </div>
);
}

export default Calculator;
```
```
Calculator.css

* {
box-sizing: border-box;
}

body {
    margin: 0;
font-family: Arial, sans-serif;
background: linear-gradient(135deg, #141e30, #243b55);
}

.calculator {
width: 340px;
margin: 70px auto;
padding: 25px;
background: #ffffff;
border-radius: 20px;
box-shadow: 0 10px 30px rgba(0,0,0,0.3);
}

h2 {
text-align: center;
color: #243b55;
}

input {
width: 100%;
height: 65px;
margin-bottom: 20px;
border: none;
border-radius: 10px;
background: #edf2f7;
text-align: right;
font-size: 26px;
padding: 10px;
}
.buttons {
display: grid;
grid-template-columns: repeat(4, 1fr);
gap: 10px;
}

button {
height: 55px;
border: none;
border-radius: 10px;
background: #e2e8f0;
font-size: 20px;
cursor: pointer;
transition: 0.2s;
}

button:hover {
background: #cbd5e1;
transform: scale(1.05);
}

.operator {
background: #ffb347;
color: white;
}

.clear {
background: #ef4444;
color: white;
}

.equal {
background: #2563eb;
color: white;
}

.equal:hover {
background: #1d4ed8;
}
```
```
App.js
import React from "react";
import Calculator from "./Calculator";

function App() {
  return (
    <div>
      <Calculator />
    </div>
  );
}

export default App;
```
## OUTPUT
<img width="1352" height="437" alt="Screenshot 2026-11-20 104617" src="https://github.com/user-attachments/assets/5ec66071-7891-46d0-8e9b-71dadfc4527f" />

<img width="1920" height="1080" alt="Screenshot 2026-11-20 104624" src="https://github.com/user-attachments/assets/02800919-eecb-4a13-a0a1-281b326e0164" />


## RESULT
The program for developing a simple calculator in React.js is executed successfully.
