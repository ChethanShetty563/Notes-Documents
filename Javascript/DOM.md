The Document Object Model (DOM) is a programming interface for web documents that offers dynamic and interactive access to the HTML or XML content of a web page, enabling developers to manipulate it in various ways such as 
* changing its content and style, 
* adding or removing elements,
* and responding to user events like clicks,
* scrolls, and key presses. 

Its versatility also allows for its use with different document types such as SVG and MathML, making it a crucial tool for creating responsive and interactive web applications, and certainly more exciting than its name might suggest."

### The BOM
* The Browser Object Model (BOM), which is sometimes referred to as the window browser object, is a powerful tool that enables JavaScript code to communicate with the browser.
* It is often considered a "magic" element due to its ability to facilitate a wide range of functionalities, such as manipulating browser windows and history, managing cookies, and interacting with user interfaces.
* The window object has global variables and functions, and these can all be seen when we explore the window object
* The exact implementation of the BOM depends on the browser and the version of the browser

Some of the most important objects of the BOM  are:

-   History
-   Navigator
-   Location

Inorder to see the window objects go to browser console  and try below code

``` javascript
console.dir(window);;
```

Note : The `console.dir()` method shows a list of all the properties of the specified object.


The BOM contains many other objects. We can access these like we saw when we dealt with objects, so for example, we can get the length of the history (in my browser) accessing the `history` object of the window and then the length of the `history` object, like this:

``` javascript
window.history.length;

```

Add another exmpale of Width

## Window history object

The window browser object also contains a `history` object. This object can actually be written without the prefix of `window` because it has been made globally available, so we can get the exact same object by using the `console.dir(window.history)` or simply the `console.dir(history)` command in the console:

``` javascript
window.history.go(-1);
```

## Window navigator object

This property is particularly interesting because it contains information about the browser we are using, such as what browser it is and what version we are using, and what operating system the browser is running on.

This can be handy for customizing the website for certain operating systems. Imagine a download button that will be different for Windows, Linux, and macOS.

``` javascript
console.dir(navigator);
```


## Window location object

* "Another fascinating and distinctive feature of the window object is the location object, which stores the current web page's URL. If you modify this object, either partially or entirely, you can force the browser to navigate to a different web page.

``` javascript
console.dir(window.location);
```

```html 
<!DOCTYPE html>

<html>

  <head>

    <title>Window Location Example</title>

  </head>

  <body>

    <h1>Click the button to go to Google</h1>

    <button onclick="navigateToGoogle()">Go to Google</button>

    <script>

      function navigateToGoogle() {

        // Set the location object's href property to the desired URL

        window.location.href = "https://www.google.com";

      }

    </script>

  </body>

</html>

```


### DOM

-   The logical tree structure of an HTML document can be displayed using a technique called the Document Object Model (DOM).
-   The DOM represents the structure of an HTML document as a tree-like structure, with each node in the tree representing an HTML element or attribute.
-   This tree-like structure is made possible by the rule that inner elements need to be closed before their outer elements.
-   The DOM can be used to manipulate and interact with the HTML document by accessing and modifying its nodes and attributes.
-   The ability to represent the HTML document as a logical tree is a powerful feature of the DOM that allows for dynamic and interactive web development.

Show this in DOM way
``` html

<html> <head> <title>Tab in the browser</title> </head> <body> <h1>DOM</h1> <div> <p>Hello web!</p> <a href="https://google.com">Here's a link!</a> </div> </body> </html>
```

Additional DOM Properties can be seen via

``` javascript
console.dir(document);

```

Conclude the introduction to DOM and BOM


### Selecting Page Elements

-   The Document Object contains numerous properties and methods that allow for dynamic and interactive web development.
-   To modify elements on a web page, you must first find or select them using the DOM API.
-   Selecting an element involves identifying it in the document tree and obtaining a reference to it using a DOM method.
-   Once an element is selected, you can manipulate its properties and contents to achieve the desired behavior or effect.

* To select page elements to use within your JavaScript code and in order to manipulate elements, you can use either the `querySelector()` or `querySelectorAll()` method.
* Both of these can be used to select page elements either by tag name, ID, or class.
* The `document.querySelector()` method will return the first element within the document that matches the specified selectors. If no matching page elements are found, the result `null` is returned.
To return multiple matching elements, you can use the method `document.querySelectorAll()`.

The `querySelectorAll()` method will return a static `NodeList`, which represents a list of the document's elements that match the specified group of selectors. We will demonstrate the usage of both `querySelector()` and `querySelectorAll()` with the following HTML snippet:

``` html
<!doctype html> <html> <head> <title>JS Tester</title> </head> <body> <h1 class="output">Hello World</h1> <div class="output">Test</div> </body> </html>
```

``` javascript

const ele1 = document.querySelector("h1"); console.dir(ele1);
```


``` javascript
const ele1 = document.querySelector("h1"); console.dir(ele1);
```

After selecting, you can start using the dynamic features of the DOM: you can manipulate the elements using JavaScript.


# Dynamic Element Manipulation Using the DOM

We will take our DOM knowledge one step further and learn how to manipulate the DOM elements on the page with JavaScript. First, we need to learn how to navigate the DOM and select the elements we want. We will learn how we can add and change attributes and values, and how to add new elements to the DOM.

### Basic DOM Traversing


This document object contains all the HTML and is a representation of the web page. Traversing over these elements can get you to the element you need in order to manipulate it.

This is not the most common way to do it, but this will help understand how it works later. And sometimes, you might actually find yourself needing these techniques as well. 

``` html 
<!DOCTYPE html> <html> <body> <h1>Let's find the treasure</h1> <div id="forest"> <div id="tree1"> <div id="squirrel"></div> <div id="flower"></div> </div> <div id="tree2"> <div id="shrubbery"> <div id="treasure"></div> </div> <div id="mushroom"> <div id="bug"></div> </div> </div> </div> </body> </html>
```


We now want to traverse the DOM of this snippet to find the treasure.

. It is easiest to do this exercise in the console in the browser, because that way you'll get direct feedback about where in the DOM you are.

We should get a really long object. There are a few ways from this object to get to our treasure. To do so, let's discuss the children and `childNodes` property.

`childNodes` is more a complete term than children. Children just contain all the HTML elements, so are really the nodes. `childNodes` also contain text nodes and comments. With children, however, you can use the ID, and therefore they are easier to use.

``` javascript
console.dir(document.body.children.forest.children.tree2.children.shrubbery.children.treasure);
```


To get to the treasure using `childNodes` you would have to use your console a lot because text and comment nodes are also in there. `childNodes` is an array, so you will have to select the right index to select the right child. There is one advantage here: it is a lot shorter because you won't need to select the name separately.

``` javascript
console.dir(document.body.childNodes[3].childNodes[3].childNodes[1].childNodes[1]);
```

You could also combine them:

``` Javascript
console.dir(document.body.childNodes[3].childNodes[3].childNodes[1].children.treasure);
```

So far, we have seen how we can move down the DOM, but we can also move up. Every element knows its parent. We can use the `parentElement` property to move back up. For example, if we use the treasure HTML sample and type this into the console:

``` javascript
document.body.children.forest.children.tree2.parentElement;
```
Not only can we move up and down, we can also move sideways. For example, if we select `tree2` like this:

```
document.body.children.forest.children.tree2;
```

We can get to `tree1` using:

```
document.body.children.forest.children.tree2.previousElementSibling;
```

And from `tree1` we can get to `tree2` using:

```
document.body.children.forest.children.tree1.nextElementSibling;
```


### Selecting elements as objects

```
<!DOCTYPE html>
<html>
  <body>
    <h1>Welcome page</h1>
    <p id="greeting">
      Hi!
    </p>
  </body>
</html>
```

We can traverse to the `p` element, for example, by using this code:

```
document.body.children.greeting;
```


This gives us the power to manipulate the properties of the element, and the element itself, directly! Let's execute this newly gained power in the next section.


### Changing innerText

The `innerText` property focuses on the text between the opening and closing of the element, like so:

```
<element>here</element>
```

The retrieved value would be `here` as plain text. For example, if we go to the console and we type:

```
document.body.children.greeting.innerText = "Bye!";
```

`innerText` returns the content of the element as plain text, which is not a problem in this case because there is only text in there. However, if there is any HTML inside the element you need to select, or if you want to add HTML, you cannot use this method. It will interpret the HTML as text and just output it on the screen. So if we executed this:

``` jaavascript
document.body.children.greeting.innerText = "<p>Bye!</p>";
```

It will output to the screen `<p>Bye!</p>`, with the HTML around it, as if it was intended as a text string. To get around this, you need to use `innerHTML`.

### Changing innerHTML

If you did not only want to work with plain text, or perhaps specify some HTML formatting with your value, you could use the `innerHTML` property instead. This property doesn't just process be plain text, it can also be inner HTML elements:

```
document.body.children.greeting.innerHTML = "<b>Bye!</b>";
```


# Accessing elements in the DOM

There are multiple methods to select elements from the DOM. After getting the elements, we are able to modify them.

 In the following sections, we will discuss how to get elements by their ID, tag name, and class name, and by CSS selector.
Instead of traversing it step by step as we just did, we are going to use built-in methods that can go through the DOM and return the elements that match the specifications.

``` html
<!DOCTYPE html> 
<html>
<body>
<h1>Just an example</h1>
<div id="one" class="example">Hi!</div>
<div id="two" class="example">Hi!</div>
<div id="three" class="something">Hi!</div>
</body> 
</html>
```

## Accessing elements by ID

* We can select elemets by ID with getElementsById() method
* This returns one element with the specified ID. IDs should be unique, as only one result will be returned from the HTML document
There are not a lot of rules for valid IDs; they cannot contain spaces and must be at least one character. As with the conventions for naming variables, it is a best practice to make it descriptive and avoid special characters.

If we want to select the element with an ID of `two` right away, we could use:

``` javascript
document.getElementById("two");
```

This would return the full HTML element:

```
<div id="two" class="example">Hi!</div>
```

To reiterate, if you have more than one element with the same ID, it will just give you back the first one it encounters. You should avoid this situation in your code though.

This is what the full file looks like with the JavaScript inside the HTML page, instead of simply querying the browser console:

```
<html>
  <body>
    <h1 style="color:pink;">Just an example</h1>
    <div id="one" class="example">Hi!</div>
    <div id="two" class="example">Hi!</div>
    <div id="three" class="something">Hi!</div>
  </body>
  <script>
    console.log(document.getElementById("two"));
  </script>
</html>
```

## Accessing elements by tag name

* If we ask for elements by tag name, we get an array as a result. This is because there could be more than one element with the same tag name.
*  It will be a collection of HTML elements, or `HTMLCollection`, which is a special JavaScript object. It's basically just a list of nodes.
``` javascript

document.getElementsByTagName("div"); 
```

We can access them using the `item()` method to access them by index, like this:

```
document.getElementsByTagName("div").item(1);
```

This will return:

```
<div id="two" class="example">Hi!</div>
```

We can also access them by name, using the `namedItem()` method, like this:

```
document.getElementsByTagName("div").namedItem("one");
```

And this will return:

```
<div id="one" class="example">Hi!</div>
```

When there is only one match, it will still return an `HTMLCollection`. There is only one `h1` tag, so let's demonstrate this behavior:

```
document.getElementsByTagName("h1");
```

This will output:

```
HTMLCollection [h1]
```


## Accessing elements by class name

We can do something very similar for class names. In our example HTML, we have two different class names: `example` and `something`. If you get elements by class name, it gives back an HTMLCollection containing the results. The following will get all the elements with the class `example`:

```
document.getElementsByClassName("example");
```

This returns:

```
HTMLCollection(2) [div#one.example, div#two.example, one: div#one.example, two: div#two.example]
```

As you can see, it only returned the `div` tags with the `example` class. It left out the `div` with the `something` class

## Accessing elements with a CSS selector

We can also access elements using a CSS selector. We do this with `querySelector()` and `querySelectorAll()`. We then give the CSS selector as an argument, and this will filter the items in the HTML document and only return the ones that satisfy the CSS selector

If we state `p` as a CSS selector, it means all the elements with tag `p`. This would look like this:

```
document.querySelectorAll("p");
```

### Using querySelector()

This first option will select the first element that matches the query. So, enter the following in the console, still using the HTML snippet introduced at the start of the section:

```
document.querySelector("div");
```

It should return:

```
<div id="one" class="example">Hi!</div>
```

It only returns the first `div`, because that's the first one it encounters. We could also ask for an element with the class .`something`. If you recall, we select classes using dot notation like this:

```
document.querySelector(".something");
```

This returns:

```
<div id="three" class="something">Hi!</div>
```

With this method, you can only use valid CSS selectors: elements, classes, and IDs.

### Using querySelectorAll()

Sometimes it is not enough to return only the first instance, but you want to select all the elements that match the query. For example when you need to get all the input boxes and empty them. This can be done with `querySelectorAll()`:

```
document.querySelectorAll("div");
```

This returns:

```
NodeList(3) [div#one.example, div#two.example, div#three.something]
```

As you can see, it is of object type `NodeList`. It contains all the nodes that match the CSS selector. With the `item()` method we can get them by index, just as we did for the `HTMLCollection`.
# Element click handler

HTML elements can do something when they are clicked. This is because a JavaScript function can be connected to an HTML element. Here is one snippet in which the JavaScript function associated with the element is specified in the HTML:

```
<!DOCTYPE html>
<html>
  <body>
    <div id="one" onclick="alert('Ouch! Stop it!')">Don't click here!</div>
  </body>
</html>
```

Whenever the text in the `div` gets clicked, a pop up with the text `Ouch! Stop it!` opens. Here, the JavaScript is specified directly after `onclick`, but if there is JavaScript on the page, you can also refer to a function that's in that JavaScript like this:

```
<!DOCTYPE html>
<html>
  <body>
    <script>
      function stop(){
        alert("Ouch! Stop it!");
      }
    </script>
    <div id="one" onclick="stop()">Don't click here!</div>
  </body>
</html>
```

This code is doing the exact same thing. As you can imagine, with bigger functions this would be a better practice. The HTML can also refer to scripts that get loaded into the page.

There is also a way to add a click handler using JavaScript. We select the HTML element we want to add the click handler to, and we specify the onclick property.

Here is a HTML snippet:

```
<!DOCTYPE html>
<html>
  <body>
    <div id="one">Don't click here!</div>
  </body>
</html>
```

This code is at the moment not doing anything if you click it. If we want to dynamically add a click handler to the `div` element, we can select it and specify the property via the console:

```
document.getElementById("one").onclick = function () {alert("Auch! Stop!"); 
}
```

# This and the DOM

The `this` keyword always has a relative meaning; it depends on the exact context it is in. In the DOM, the special `this` keyword refers to the element of the DOM it belongs to. If we specify an `onclick` to send `this` in as an argument, it will send in the element the `onclick` is in.

Here is a little HTML snippet with JavaScript in the `script` tag:

```
<!DOCTYPE html>
<html>
  <body>
    <script>
      function reveal(el){
        console.log(el);
      }
    </script>
    <button onclick="reveal(this)">Click here!</button>
  </body>
</html>
```

And this is what it will log:

```
<button onclick="reveal(this)">Click here!</button>
```

As you can see, it is logging the element it is in, the `button` element.

We can access the parent of `this` with a function like this:

```
function reveal(el){
    console.log(el.parentElement);
}
```

In the above example, the body is the parent of the button. So if we click the button with the new function, it will output:

```
<body>
    <script>
      function reveal(el.parentElement){
        console.log(el);
      }
    </script>
    <button onclick="reveal(this)">Click here!</button>
  </body>
```

We could output any other property of the element the same way; for example, `console.log(el.innerText);` would print the inner text value as we saw in the _Changing innerText_ section.

So, the `this` keyword is referring to the element, and from this element we can traverse the DOM like we just learned. This can be very useful, for example, when you need to get the value of an input box. If you send `this`, then you can read and modify the properties of the element that triggered the function.

# Manipulating element style

After selecting the right element from the DOM, we can change the CSS style that applies to it. We can do this using the `style` property. This is how to do it:

1.  Select the right element from the DOM.
2.  Change the right property of the style property of this element.

We are going to make a button that will toggle the appearing and disappearing of a line of text. To hide something using CSS, we can set the `display` property of the element to `none`, like this for a `p` (paragraph) element:

```
p {
  display: none;
}
```

And we can toggle it back to visible using:

```
p {
  display: block;
}
```

We can add this style using JavaScript as well. Here is a little HTML and JavaScript snippet that will toggle the displaying of a piece of text:

```
<!DOCTYPE html>
<html>
  <body>
    <script>
      function toggleDisplay(){
        let p = document.getElementById("magic");
        if(p.style.display === "none") {
          p.style.display = "block";
        } else {
          p.style.display = "none";
        }
      }
    </script>
    <p id="magic">I might disappear and appear.</p>
    <button onclick="toggleDisplay()">Magic!</button>
  </body>
</html>
```

As you can see, in the `if` statement we are checking for whether it is currently hiding, if it is hiding, we show it. Otherwise, we hide it. If you click the button and it is currently visible, it will disappear. If you click the button when the text is gone, it will appear.

You can do all sorts of fun things using this style element. What do you think this does when you click the button?

```
<!DOCTYPE html>
<html>
  <body>
    <script>
      function rainbowify(){
        let divs = document.getElementsByTagName("div");
        for(let i = 0; i < divs.length; i++) {
          divs[i].style.backgroundColor = divs[i].id;
        }
      }
    </script>
    <style>
      div {
        height: 30px;
        width: 30px;
        background-color: white;
      }
    </style>
    <div id="red"></div>
    <div id="orange"></div>
    <div id="yellow"></div>
    <div id="green"></div>
    <div id="blue"></div>
    <div id="indigo"></div>
    <div id="violet"></div>
    <button onclick="rainbowify()">Make me a rainbow</button>
  </body>
</html>
```