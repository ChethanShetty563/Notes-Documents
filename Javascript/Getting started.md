###  Introduction 
* Welcome to the world of web development! Have you ever wondered how websites are able to provide interactive features like accepting cookies, filtering products, and engaging with virtual assistants? Well, the answer lies in JavaScript!

*  JavaScript is a programming language that is commonly used by web developers to add interactive features to websites. When you enter a webpage, the website may prompt you to accept cookies, and when you click on the button, the pop-up disappears. This functionality is powered by JavaScript, which enables websites to respond to user input in real-time.

* Another example of JavaScript in action is when you filter products on an e-commerce website. You can select various criteria such as price range, color, size, and the website instantly updates the product listings based on your selection.

* Have you ever visited a website where a chat window pops up after a few seconds? This is yet another example of JavaScript in action! The website is using JavaScript to display the chat window and provide automated responses to your queries.

* In conclusion, JavaScript plays a crucial role in making websites interactive and engaging. It enables developers to create dynamic and customized web experiences that respond to user input. So, the next time you browse a website and encounter an interactive feature, remember that it is most likely powered by JavaScript!

* Well adding to the  above statements JavaScript is a programming language that can be used on both the server side and client side of applications. The server side of an application is the backend logic that usually runs on computers in data centers and interacts with the database, while the client side is what runs on the device of the user, often the browser for JavaScript.

### Why someone should learn Javascript?

There are many reasons to learn Javascript ose of them are given below

* JavaScript was created in 1995 and is the most widely used programming language for web development.
* JavaScript doesn't require anything extra to run since it's natively supported by web browsers.
* JavaScript is beginner-friendly and you can start building cool apps sooner than you might think.
* You can use JavaScript for a variety of purposes, including programming for the web browser, communication with databases, automation scripts, and game development.
* Once you get the basics of JavaScript down, you can use libraries and frameworks to enhance your software development experience, such as React, Vue.js, jQuery, Angular, and Node.js.
* The JavaScript community is huge and provides an abundance of resources and support.


### # How does the browser understand JavaScript?

JavaScript is an interpreted language, which means that the computer understands it while running it. Some languages get processed before running, this is called compiling, but not JavaScript. The computer can just interpret JavaScript on the fly. The "engine" that understands JavaScript will be called the interpreter here.

Ex : Google V8 engine

HTML determines what is on the page; the content of the page is in there. If there is a paragraph on the page, the HTML of the page contains a paragraph. And if there is a heading, HTML was used to add a heading, and so forth. HTML consists of elements, also called tags

CSS is the layout of the web page. So for example, if the text color is blue, this is done by CSS. Font size, font family, and position on the page are all determined by CSS


JavaScript is the final piece in the puzzle, which defines what the web page can do and how it can interact with the user or the backend.

Browsers use the ECMAScript specification to support JavaScript, which includes topics such as the Document Object Model (DOM). While there may be slight differences in implementations, ECMAScript is the basic specification that all JavaScript implementations must include.


### Using the Browser Console

Inorder to use the developer tools press F12 in webpage or right click and click on "Inspect ".

This screenshot contains multiple tabs at the top. We are now looking at the element tabs, which contain all the HTML and CSS (remember those?). If you click on the console tab, you will find at the bottom of the panel a place where you can insert some code directly.

The console is used by developers to log what is going on and do any debugging. Debugging is finding the problem when an application is not displaying the desired behavior. The console gives some insights as to what is happening if you log sensible messages. This is actually the first command we are going to learn:

``` Javascript
console.log('Hello World!')
```

How to add Js to HTML?

``` html
<html> <script type="text/javascript"> alert("Hi there!"); </script> </html>
```

Another  Example

``` html 
<!DOCTYPE html> <html> <head> <title>This goes in the tab of your browser</title> </head> <body> The content of the webpage <script> console.log("Hi there!"); </script> </body> </html>
```

Linking an external file to our web page

create a file called alert.js

``` js
alert("Saying hi from a different file!");
```

Link the file to html as below


``` html
<html> <script type="text/javascript" src="ch1_alert.js"></script> </html>
```