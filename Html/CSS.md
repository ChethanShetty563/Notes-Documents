The latest version of CSS is 3
* CSS stands for cascading style sheet
* CSS describes hoe HTML elements are to be dislayed on Screnn, paper or other media
* CSS saves lot of work. It can control the layout of multiple web pages all at once
* External stylesheets are stored in CSS files

``` css
Syntax of CSS

selector  {
property : value;
}

%% Example %%
h1 {
coloe: blue;
font-size: 20px;
}

```

### Types of CSS

There are 3 ways to inserting style sheet:

* External CSS
* Internal CSS
* Inline CSS

The difference between HTML and CSS is that in HTML we need write various attributes but in CSS we need to write the properties and values

#### Inline CSS

The below code shows the how to write the inline CSS

``` HTML
<!DOCTYPE html>

<html lang="en">

<head>

    <meta charset="UTF-8">

    <meta http-equiv="X-UA-Compatible" content="IE=edge">

    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Document</title>

</head>

<body>

    <h1 style="color: aqua; background-color: green;">Welcome Page</h1>

</body>

</html>
```


#### Internal CSS

To write the internal CSS add the "style" tag in head and add h2 tag to above code and write css values for it

``` HTML & CSS
<h2>Hello world for h2</h2>

CSS
h2 {
color : greenyellow;
background-color: honeydew;
}
```

### How do i select the Selector

There are 3 ways we can select the selectors

* ID
* Class
* Tag

Style By ID

use # operator to select the ID
Id should be unique to all the attributes
``` HTML
<h3 id="heading">Style By ID</h3>

CSS
#id {
color : red;
}
```

Style By Class

Use dot operator to select the class

```
 <h4 class="h3-class">Style By Class</h4>

 .h3-class {
            color: green;
        }
 
```

Style By Tag

Use tag name to apply the style
```
 <h5>Style By Tag</h5>

 h5{
   color: aqua;
 }
```

#### Priorities of Selectors

What if style is applied in all 3 selector to same element

* The top most priority is given to ID
* The second priority is given to class
* The last priority is given to Tag

```
 #h1-id {
     color: aqua;
     }
 .h1-tag {
     color: green;
    }
        h1{

            color: red;

        }
   <h1 class="h1-tag" id="h1-id">Priority Tag</h1>

```


#### External CSS

Add the below line in head to link  the external CSS

```
<link rel="stylesheet" href="./index.css"/>
```

The full code goes like this

``` HTML
<!DOCTYPE html>

<html lang="en">

<head>

    <meta charset="UTF-8">

    <meta http-equiv="X-UA-Compatible" content="IE=edge">

    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Document</title>

    <link rel="stylesheet" href="./index.css"/>

</head>

<body>

    <h1 class="h1-tag" id="h1-id">Priority Tag</h1>

</body>

</html>
```

``` CSS
#h1-id {
    color: aqua;
}
.h1-tag {
    color: green;
}
h1{
    color: red;
}
```

Priorities of types of CSS

* First priority goes to Inline and next internal and then External
* Show with Example

### CSS Selectors (Advanced)

CSS selectors are used to find the HTML elements you want to style

* Simple Selectors (Select elements based on name, id, class)
* Combinator selectors (Select elements based on a specific relationship between them)
* Pseudo class selectors(select elements based on certain state)
* Pseudo element selectors (select and style a part of an element)
* Attribute Selectors(Select elements based on attribute or attribute level)

#### CSS Colors

Colors are specified using predefined color names, ot RGB, HEX, HSL, RGBA values