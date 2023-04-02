* It is the advanced topic
* Defining the whole journey
* I can visulize how it can move from point A to point B

Example
``` html
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

    <div>

  

    </div>

</body>

</html>
```

``` css
* {

    padding: 0;

    margin: 0;

  

}

  

div {

    width: 200px;

    height: 200px;

    margin: 100px auto;

    background-color: rgb(9, 87, 156);

    transition-property: width;

    /* transition-delay: 1s;

     */

     /* transition-duration: 2s;

     transition-timing-function: cubic-bezier(); */

     transition: background-color 1s ease-in, width 2s ease-in, height 2s ease-in;

}

  

div:hover {

    width: 600px;

    height: 400px;

    background-color: rgb(177, 150, 0);

}
```