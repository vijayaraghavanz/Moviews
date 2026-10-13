PROGRAM – 14 

App.js:


import { useState } from "react"; 
import "./App.css"; 
function App() { 
const products = [ 
{ id: 1, name: "Rice", price: 60 }, 
{ id: 2, name: "Milk", price: 30 }, 
{ id: 3, name: "Apple", price: 120 }, 
{ id: 4, name: "Bread", price: 40 } 
]; 
const [cart, setCart] = useState([]); 
const addToCart = (product) => { 
const existing = cart.find( 
item => item.id === product.id 
); 
if (existing) { 
setCart(cart.map(item => 
item.id === product.id 
? { ...item, qty: item.qty + 1 } 
: item 
) 
); 
} else { 
setCart([ 
...cart, 
{ ...product, qty: 1 } 
]); 
} 
}; 
const total = cart.reduce( 
(sum, item) => 
sum + item.price * item.qty, 
0 
); 
const placeOrder = () => { 
if (cart.length === 0) { 
alert("Cart is Empty"); 
} else { 
alert("Order Placed Successfully!"); 
setCart([]); 
} 
}; 
return ( 
<div className="container"> 
<h1>Grocery Delivery App</h1> 
<h2>Available Products</h2> 
<div className="products"> 
{products.map(product => ( 
<div className="card" key={product.id}> 
<h3>{product.name}</h3> 
<p>₹{product.price}</p> 
<button 
onClick={() => addToCart(product)} 
> 
Add to Cart 
</button> 
</div> 
))} 
</div> 
<h2>Shopping Cart</h2> 
{cart.length === 0 ? ( 
<p>Your cart is empty</p> 
) : ( 
cart.map(item => ( 
<p key={item.id}> 
{item.name} 
{" - "} 
₹{item.price} 
{" × "} 
{item.qty} 
</p> 
)) 
)} 
<h2>Total: ₹{total}</h2> 
<button onClick={placeOrder}> 
Place Order 
</button> 
</div> 
); 
} 
export default App; 

App.css 


body { 
font-family: Arial, sans-serif; 
background-color: #f2f2f2; 
margin: 0; 
} 
.container { 
text-align: center; 
padding: 30px; 
} 
h1 { 
color: green; 
} 
.products { 
display: flex; 
justify-content: center; 
gap: 20px;
flex-wrap: wrap; 
} 
.card { 
background-color: white; 
width: 180px; 
padding: 20px; 
border-radius: 10px; 
box-shadow: 0 0 8px gray; 
} 
.card h3 { 
color: darkgreen; 
} 
button { 
background-color: green; 
color: white; 
padding: 10px 18px; 
border: none; 
border-radius: 5px; 
cursor: pointer; 
} 
button:hover { 
background-color: darkgreen; 
}


STEPS 

1. Open Visual Studio Code and open the terminal.

2.npx create-react-app grocery-app

3. cd grocery-app

4. Open the project in VS Code:

5. Open the src folder.

6. Replace the contents of App.js, App.css 

7.npm start
__________________________________

PROGRAM – 12 

<!DOCTYPE html> 
<html> 
<head> 
 <title>Registration Form Validation</title> 

 <style> 
 body { 
 font-family: Arial; 
 background-color: #f2f2f2; 
 } 
 .form-box { 
 width: 350px; 
 margin: 80px auto; 
 padding: 25px; 
 background-color: white; 
 box-shadow: 0 0 10px gray; 
 border-radius: 10px; 
 } 
 input { 
 width: 95%; 
 padding: 10px; 
 margin: 8px 0; 
 } 
 button { 
 width: 100%; 
 padding: 10px; 
 background-color: blue; 
 color: white; 
 border: none; 
 } 
 #message { 
 margin-top: 15px; 
 font-weight: bold; 
 } 
 </style> 
</head> 
<body> 
 <div class="form-box"> 
 <h2>Registration Form</h2> 
 <input type="text" id="name" 
placeholder="Enter Name"> 
 <input type="text" id="mobile" 
placeholder="Enter Mobile Number"> 
 <input type="text" id="email" 
placeholder="Enter E-mail"> 
 <button onclick="validateForm()"> 
 Register 
 </button> 
 <p id="message"></p> 
 </div> 
 <script> 
 function validateForm() { 
 let name = 
document.getElementById("name").value; 
 let mobile = 
document.getElementById("mobile").value; 
 let email = 
document.getElementById("email").value; 
 let namePattern = /^[A-Za-z][A-Zaz0-9]{5,}$/; 
 let mobilePattern = /^[0-9]{10}$/; 
let emailPattern = 
/^[^\s@]+@[^\s@]+\.[^\s@]+$/; 
 if (!namePattern.test(name)) { 
document.getElementById("message").inner
HTML = "Invalid Name"; 
 return; 
 } 
 if (!mobilePattern.test(mobile)) { 
document.getElementById("message").inner
HTML = "Invalid Mobile Number"; 
 return; 
 } 
 if (!emailPattern.test(email)) { 
document.getElementById("message").inner
HTML = "Invalid E-mail"; 
 return; 
 } 
document.getElementById("message").inner
HTML = "Registration Successful"; 
 } 
 </script> 
</body> 
</html>

STEPS 

1.Create a folder named Program12 and open it in VS Code.

2.Create a file named index.html.open in live server
__________________________________

PROGRAM – 11 

index.html 

<!DOCTYPE html> 
<html> 
<head> 
 <title>My Simple Webpage</title> 
</head> 
<body> 
 <center> 
 <h1>Welcome to My Webpage</h1> 
 <p>This is a simple webpage created 
using HTML.</p> 
 </center> 
 <hr> 
 <h2>About Me</h2> 
 <p> 
 I am learning HTML, CSS, and 
JavaScript to develop websites and web 
applications. 
 </p> 
 <h2>My Skills</h2> 
 <ul> 
 <li>HTML</li> 
 <li>CSS</li> 
 <li>JavaScript</li> 
 <li>Java Programming</li> 
 </ul> 
 <h2>My Favorite Subjects</h2> 
 <ol> 
 <li>Web Development</li> 
 <li>Data Structures</li> 
 <li>Database Management System</li> 
 </ol> 
 <h2>Sample Image</h2> 
 <img src="https://picsum.photos/300/200" 
alt="Sample Image"> 
 <h2>Useful Link</h2> 
 <a href="https://www.google.com"> 
 Visit Google 
 </a> 
 <hr> 
 <p align="center"> 
 © 2026 My Webpage 
 </p> 
</body> 
</html> 

DOCKER FILE 

FROM nginx:alpine 
COPY index.html 
/usr/share/nginx/html/index.html 
EXPOSE 80


STEPS
1. Create a folder named Program11 and open it in VS Code.

2. Create these two files inside the folder:

index.html

Dockerfile

3. Copy the given code into index.html Dockerfile:

6. Build the Docker image:

docker build -t mywebpage .

7. Run the Docker container:

docker run -d -p 8080:80 mywebpage

8. Open a browser and go to:

http://localhost:8080

9. The webpage will be displayed through the Nginx Docker container.


10. To stop the container:

docker ps
docker stop <container_id>
__________________________________

PROGRAM 10

<!DOCTYPE html> 
<html> 
<head> 
 <title>Star Rating System</title> 
 <script 
src="https://code.jquery.com/jquery-
3.7.1.min.js"></script> 
 <style> 
 body { 
 font-family: Arial, sans-serif; 
 text-align: center; 
 margin-top: 100px; 
 background-color: #f2f2f2; 
 } 
 .container { 
 width: 400px; 
 margin: auto; 
 background-color: white; 
 padding: 30px; 
 border-radius: 10px; 
 box-shadow: 0 0 10px gray; 
 } 
 .star { 
 font-size: 50px; 
 color: gray; 
 cursor: pointer; 
 } 
 .selected { 
 color: gold; 
 } 
 #result { 
 margin-top: 20px; 
 font-size: 22px; 
 font-weight: bold; 
 } 
 </style> 
</head> 
<body> 
 <div class="container"> 
 <h2>Star Rating System</h2> 
 <span class="star" datavalue="1">★</span> 
 <span class="star" datavalue="2">★</span> 
 <span class="star" datavalue="3">★</span> 
 <span class="star" datavalue="4">★</span> 
 <span class="star" datavalue="5">★</span> 
 <div id="result"> 
 Select your rating 
 </div> 
 </div> 
 <script> 
 $(document).ready(function() { 
 $(".star").click(function() { 
 let rating = $(this).data("value"); 
 $(".star").removeClass("selected"); 
 $(".star").each(function() { 
 if ($(this).data("value") <= 
rating) { 
 $(this).addClass("selected"); 
 } 
 }); 
 $("#result").text("You selected " + 
rating + " star(s)"); 
 }); 
 }); 
 </script> 
</body> 
</html>

STEPS 

1.Create a folder named Program10 and open it in VS Code.
2.Copy and paste into index.html and Open it in browser
__________________________________


Program -9

index.html

<!DOCTYPE html>
<html>
<head>
    <title>Password Strength Checker</title>

    <script src="https://code.jquery.com/jquery-3.7.1.min.js"></script>

    <style>
        body {
            font-family: Arial;
            text-align: center;
            background: #f2f2f2;
            margin-top: 100px;
        }

        .container {
            width: 400px;
            margin: auto;
            padding: 30px;
            background: white;
            border-radius: 10px;
            box-shadow: 0 0 10px gray;
        }

        input {
            width: 90%;
            padding: 12px;
            font-size: 16px;
        }

        #strength {
            margin-top: 20px;
            font-size: 20px;
            font-weight: bold;
        }

        .weak { color: red; }
        .medium { color: orange; }
        .strong { color: green; }
    </style>
</head>

<body>

<div class="container">
    <h2>Password Strength Checker</h2>
    <input type="password" id="password" placeholder="Enter your password">
    <div id="strength">Enter a password</div>
</div>

<script>
$(function() {
    $("#password").keyup(function() {
        let p = $(this).val(), score = 0;

        if (p.length >= 8) score++;
        if (/[a-z]/.test(p) && /[A-Z]/.test(p)) score++;
        if (/[0-9]/.test(p)) score++;
        if (/[^A-Za-z0-9]/.test(p)) score++;

        let s = $("#strength").removeClass();

        if (!p) s.text("Enter a password");
        else if (score <= 1) s.text("Weak Password").addClass("weak");
        else if (score <= 3) s.text("Medium Password").addClass("medium");
        else s.text("Strong Password").addClass("strong");
    });
});
</script>

</body>
</html>

STEPS 
1. Create a folder named Ex-9 and open it in VS Code.
2. Create index.html.
3. Paste the above code and save.
4.open index. HTML in browser

__________________________________

Program -8

App. Js

import { useState } from "react";
import "./App.css";

function App() {
  const [a, setA] = useState(0);
  const [b, setB] = useState(0);
  const [c, setC] = useState(0);

  return (
    <div className="container">
      <h1>Voting Application</h1>

      <div className="card">
        <h2>Candidate A</h2>
        <p>Votes: {a}</p>
        <button onClick={() => setA(a + 1)}>Vote</button>
      </div>

      <div className="card">
        <h2>Candidate B</h2>
        <p>Votes: {b}</p>
        <button onClick={() => setB(b + 1)}>Vote</button>
      </div>

      <div className="card">
        <h2>Candidate C</h2>
        <p>Votes: {c}</p>
        <button onClick={() => setC(c + 1)}>Vote</button>
      </div>
    </div>
  );
}

export default App;

App. Css

body {
  margin: 0;
  font-family: Arial;
  background: #f2f2f2;
}

.container {
  text-align: center;
  padding: 40px;
}

h1 {
  color: darkblue;
}

.card {
  background: white;
  width: 300px;
  margin: 20px auto;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 0 10px gray;
}

.card h2 {
  color: darkgreen;
}

.card p {
  font-size: 22px;
  font-weight: bold;
}

button {
  background: darkblue;
  color: white;
  padding: 10px 25px;
  border: 0;
  border-radius: 5px;
}

STEPS

Open terminal and run:
1.npx create-react-app voting-app
2.cd voting-app
3.code .(Open it in VS Code:) 
4.replace codes
4.npm start

__________________________________

Program -7

const express = require("express");
const session = require("express-session");

const app = express();

app.use(session({
    secret: "secretKey",
    resave: false,
    saveUninitialized: true
}));

app.get("/", (req, res) => {
    req.session.views = (req.session.views || 0) + 1;

    res.send(`
    <html>
    <head>
        <title>Visitor Counter</title>
        <style>
            body{
                font-family: Arial;
                text-align: center;
                margin-top: 100px;
                background: #f2f2f2;
            }
            .box{
                display: inline-block;
                padding: 20px;
                background: white;
                border-radius: 8px;
                box-shadow: 0 0 8px gray;
            }
            h2{color: navy;}
            p{font-size:20px;color:green;}
        </style>
    </head>
    <body>
        <div class="box">
            <h2>Website Visitor Counter</h2>
            <p>You visited this page ${req.session.views} time(s).</p>
        </div>
    </body>
    </html>
    `);
});

app.listen(3000, () => {
    console.log("Server running at http://localhost:3000");
});


STEPS:

1. Create a new folder named Ex-7.
2. Open the folder 
3. Open the integrated terminal 
4. npm init -y
5. npm install express express-session
6. Create a file named server.js inside the project folder.
7. Copy and paste 
8. node server.js

__________________________________


Program - 6

App. js

import { useState } from "react";
import "./App.css";

function App() {
  const [input, setInput] = useState("");

  return (
    <div className="calc">
      <h2>Calculator</h2>

      <input value={input} readOnly className="display" />

      <div className="btns">
        {["C","/","*","-","7","8","9","+","4","5","6","=","1","2","3","0","."].map((b) => (
          <button
            key={b}
            className={b === "." ? "dot" : ""}
            onClick={() => {
              if (b === "C") setInput("");
              else if (b === "=") {
                try { setInput(eval(input).toString()); }
                catch { setInput("Error"); }
              } else setInput(input + b);
            }}
          >
            {b}
          </button>
        ))}
      </div>
    </div>
  );
}

export default App;

App. css


body{
  margin:0;
  display:flex;
  justify-content:center;
  align-items:center;
  height:100vh;
  font-family:Arial;
  background:#eef2f7;
}

.calc{
  width:300px;
  padding:20px;
  background:#fff;
  border-radius:10px;
  box-shadow:0 0 10px gray;
}

h2{text-align:center;}

.display{
  width:100%;
  height:45px;
  font-size:20px;
  text-align:right;
  margin-bottom:10px;
}

.btns{
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:8px;
}

button{
  height:50px;
  font-size:18px;
}

.dot{
  grid-column:span 4;
}


STEPS:
Open Visual Studio Code.
Open the terminal 
npx create-react-app calculator-app
cd calculator-app
 Open folder (code.) 
Replace App. js and App. css
npm start
__________________________________

Program -5 

Index. Html
Create sample html code
Main. Js:
const { app, BrowserWindow } = require("electron");

app.whenReady().then(() => {
    const win = new BrowserWindow({
        width: 800,
        height: 600
    });

    win.loadFile("index.html");
});

app.on("window-all-closed", () => {
    if (process.platform !== "darwin") app.quit();
});


Package. Json
Make sure these exist in this file
Main:main.js
Start:electron

STEPS:
Create a new folder named Ex-5.
Open the folder in Visual Studio Code.
Open the terminal
npm init -y
npm install --save-dev electron
Create the following files:
index.html
main.js

Save all the files.
npm start

__________________________________
Program 4

<!DOCTYPE html>
<html>
<head>
    <title>Chatbot</title>
    <link rel="stylesheet" href="style4.css">
</head>
<body>

<div id="chatBox">

    <div class="container">
        <img src="a2.png" alt="Bot">
        <p>Hello! Welcome to CodeGenesis.</p>
        <span class="time-right">10:00 AM</span>
    </div>

    <div class="container darker">
        <img src="a1.jpeg" class="right" alt="User">
        <p>Hello! I want to register.</p>
        <span class="time-left">10:01 AM</span>
    </div>

    <div class="container">
        <img src="a2.png" alt="Bot">
        <p>Please enter your name and email.</p>
        <span class="time-right">10:02 AM</span>
    </div>

    <div class="container darker">
        <img src="a1.jpeg" class="right" alt="User">
        <p>Priya, priya@example.com</p>
        <span class="time-left">10:03 AM</span>
    </div>

    <div class="container">
        <img src="a2.png" alt="Bot">
        <p>Registration completed successfully!</p>
        <span class="time-right">10:04 AM</span>
    </div>

</div>

</body>
</html>

style4.css
body{
    font-family: Arial;
    background:#f2f2f2;
    margin:0;
}

#chatBox{
    width:60%;
    margin:20px auto;
}

.container{
    background:#fff;
    padding:10px;
    margin:10px 0;
    border-radius:8px;
    overflow:auto;
}

.darker{
    background:#ddd;
}

img{
    width:40px;
    float:left;
    border-radius:50%;
    margin-right:10px;
}

.right{
    float:right;
    margin-left:10px;
    margin-right:0;
}

.time-right{
    float:right;
    color:gray;
    font-size:12px;
}

.time-left{
    float:left;
    color:gray;
    font-size:12px;
}
__________________________________
Program 3

<!DOCTYPE html>
<html>
<head>
    <title>Registration Form</title>

    <style>
        body{
            font-family: Arial;
            background:#f2f2f2;
        }
        .container{
            width:350px;
            margin:50px auto;
            padding:20px;
            background:#fff;
            border-radius:10px;
            box-shadow:0 0 10px gray;
        }
        input{
            width:100%;
            padding:8px;
            margin:8px 0;
        }
    </style>

    <script>
        function validateForm(){
            let name=document.getElementById("name").value;
            let email=document.getElementById("email").value;
            let password=document.getElementById("password").value;
            let mobile=document.getElementById("mobile").value;

            if(name==""){
                alert("Enter Name");
                return false;
            }

            if(!email.includes("@")){
                alert("Invalid Email");
                return false;
            }

            if(password.length<6){
                alert("Password must be at least 6 characters");
                return false;
            }

            if(mobile.length!=10){
                alert("Enter a 10-digit Mobile Number");
                return false;
            }

            alert("Registration Successful!");
            return true;
        }
    </script>
</head>

<body>

<div class="container">
    <h2>Registration Form</h2>

    <form onsubmit="return validateForm()">
        <input type="text" id="name" placeholder="Name">
        <input type="email" id="email" placeholder="Email">
        <input type="password" id="password" placeholder="Password">
        <input type="text" id="mobile" placeholder="Mobile Number">

        <input type="submit" value="Register">
        <input type="reset" value="Clear">
    </form>
</div>

</body>
</html>
__________________________________
Program 2

<!DOCTYPE html>
<html lang="en">
<head>
 <meta charset="UTF-8">
 <meta name="viewport" 
content="width=device-width, initialscale=1.0">
 <title>Simple Web Page</title>
 <style>
{
 margin:0;
 padding:0;
 box-sizing:border-box;
 font-family:Arial, sans-serif;
 }
 body{
 background:linear-gradient(to 
right,#4facfe,#00f2fe);
 display:flex;
 justify-content:center;
 align-items:center;
 height:100vh;
 }
 .container{
 background:white;
 padding:30px;
 border-radius:12px;
 text-align:center;
 width:350px;
 box-shadow:0 5px 15px 
rgba(0,0,0,0.3);
 }
 h1{
 color:#333;
 margin-bottom:15px;
 }
 p{
 color:#555;
 margin-bottom:20px;
 }
 button{
 background:#007BFF;
 color:white;
 border:none;
 padding:10px 20px;
 border-radius:5px;
 cursor:pointer;
 font-size:16px;
 }
 button:hover{
 background:#0056b3;
 }
 </style> </head>
<body>
 <div class="container">
 <h1 id="title">Welcome!</h1>
 <p id="message">
 This is a simple webpage created using 
HTML, CSS, and JavaScript. </p>
 <button 
onclick="changeContent()">Click 
Me</button>
 </div>
 <script>
 function changeContent() {
document.getElementById("title").innerHTM
L = "Hello, User!"; 
document.getElementById("message").innerH
TML ="You clicked the button successfully. 
JavaScript changed this content.";
}
</script>
</body> 
</html>
__________________________________
Program 1

<!DOCTYPE html>
<html>
<head>
 <title>My First Webpage</title>
</head>
<body>
 <h1>Welcome to My Webpage</h1>
 <p>This is a simple webpage created using 
HTML.</p>
 <h2>About Me</h2>
 <p>I am learning HTML and web 
development.</p>
 <a href="https://www.google.com">Visit 
Google</a>
</body>
</html>






