
Background

``` css
h1{
background-color : red;
}
```

``` css
div {
background-image: url(drop.jpg);
width: 100%;
height: 100vh;
%%background-repeat : repeat-x;
background-repeat : repeat-y;%%
background-repeat : no-repeat;
background-size : cover;

// first center define x axis and other y axiss
background-position : center center;

background-attachment: fixed
}
```

### CSS Borders

* dotted -  defines a dotted border
* dashed -  defines a dashed border
* solid - defines solid border
* double - defined double border
* groove -  defines a 3D grooved border
* ridge : defines a 3D ridged border
* inset - defines a inset border
* outset - defines a outset border
* none - defines no border
* hidden - defines a hidden border

```
border : 20px solid greenyellow;

or 
border-left : 20px solid red;
border-right : 20px solid red;
border-top : 20px solid red;
border-bottom : 20px solid red;
```

### Oulines

* dotted -  defines a dotted outline
* dashed -  defines a dashed outline
* solid - defines solid outline
* double - defined double outline
* groove -  defines a 3D grooved outline
* ridge : defines a 3D ridged outline
* inset - defines a inset outline
* outset - defines a outset outline
* none - defines no outline

Outline just wraps around the content
Ooutline and border are simillar only the difference is space


#### Height & Width

The height and width properties are used to set the height and width of an element

The height and width properties donot include padding, borders, or margins. It sets the height/width of the area inside the padding, border and margin of the element

```
css

h1 {
width: 500px;
height: 500px;
}



<h1>
shdfvfvkfv
<h1>
```


#### Margin and Padding

* margin properties are used to create space around the elements, outside of any defined borders
* with CSS you can control that for each side (top, right, bottom and left)
* padding properties are used to generate space around elemet content

Explain with page box model

Add the content here

```

h3 {
	padding: 30px;
	padding : 0 0 0 0;
or
padding-left;
padding-right;
padding-top;
padding-bottom;

}
```

``` css
h3 {
	margin: 30px;
	margin : 0 0 0 0;
or
margin-left;
margin-right;
margin-top;
margin-bottom;

}
```

### Text Alignment

The text-align property is used to set the horizontal alaignment of atext

The text can be left or right aligned, centered, or justified

```
text-align : values;
```

Text Decoration
* underline
* wavy
* line-through
* none

```
text-decoration : values;
```

Text transform :
* uppercase
* lowercase
* capitalize

Text Spacing:

It is used to give space to the text:

* Text-indent
* Text-spacing
* word-spacing
*
```
text-indent: 30px;
text-spacing : 20 px;
word-spacing: 
```


#### Font family

Three ways we can add the fonts

* Use googlr link and import
* Download the fonts
* USe basic Fonts
*```

```
font-family: "courier new"
```


``` css
  @import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@1,900&display=swap');


font-family: 'Roboto', sans-serif;
```

### CSS Display Property

* Inline
* Block
* Flex
* Grid
* none

```
<div>

</div>
<div>

</div>
<div>

</div>
<div>

</div><div>

</div>
```

Show only inline, block and none

### Position in CSS

It is the most important part in CSS. if you want to chnage the position of content you must know positioning

* Static : An elemet with this value is not positioned in any speacil way. It is positioned to normal flow
* Relative : An element with this value is positioned related to its real position
* Absolute :  It is positioned relative to the nearest positioned ancestor
* fixed : It is positioned relative to the viewport which means it always stays in same position even if the page is scrolled
* Sticy : It is positioned based on user's scroll position

``` html
<!DOCTYPE html>

<html lang="en">

<head>

    <meta charset="UTF-8">

    <meta http-equiv="X-UA-Compatible" content="IE=edge">

    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Document</title>

    <style>

  

        .head {

            position: relative;

        }

        .thirddiv {

            position: absolute;

            top: 50%;

        }

  

        .fourthdiv {

            position: fixed;

        }

    </style>

</head>

<body>

   <div class="head">

    <div>Lorem ipsum dolor sit amet consectetur adipisicing elit. Magni necessitatibus ducimus nobis quam ipsum natus, vel cum, laboriosam aspernatur qui consequuntur commodi a consequatur, quas ullam optio error sit est?</div>

    <div>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Accusamus eum libero voluptatibus tempora laborum omnis eos officia culpa, delectus asperiores soluta vel a qui tenetur, suscipit, assumenda ab distinctio atque.</div>

    <div class="thirddiv">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Atque a modi ea libero asperiores. Rem molestiae quam ipsum labore. Commodi, numquam blanditiis nemo laboriosam quaerat repellat dolores architecto minima beatae!</div>

    <div class="fourthdiv">Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde blanditiis dolorem, architecto atque consectetur debitis praesentium eos molestiae omnis accusantium et impedit quaerat minima dicta cum totam officiis doloribus beatae!</div>

    <div>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Eum cum debitis cupiditate ratione? Accusantium error neque aut dolor. Excepturi quam nihil quas voluptatum, veritatis quo magni provident commodi esse omnis?</div>

   </div>

</body>

</html>
```


#### Z-index in css

``` html
<!DOCTYPE html>

<html lang="en">

<head>

    <meta charset="UTF-8">

    <meta http-equiv="X-UA-Compatible" content="IE=edge">

    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Document</title>

    <style>

  

        img {

            width: 200px;

            height: 200px;

            position: absolute;

            z-index: -1;

        }

  

    </style>

</head>

<body>

    <img src=""/>

    <h1>Hello this is image</h1>

</body>

</html>
```