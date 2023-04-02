* It is the most important topic in CSS
* It is used to create the layout in CSS
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

    <div class="container">

        <div class="items item1">Section 1</div>

        <div class="items item2">Section 2</div>

        <div class="items item3">Section 4</div>

        <div class="items item4">Section 4</div>

        <div class="items item5">Section 5</div>

    </div>

</body>

</html>

```

``` css
.container {

    background-color: aqua;

    display: flex;

    flex-direction: row;

  
  

}

  

.items {

    width: 200px;

    height: 200px;

    margin: 10px;

}

  

.item1 {

    background-color: #873232;

}

  

.item2 {

    background-color: #2f4c9c;

}

.item3 {

    background-color: #aa2181;

}

.item4 {

    background-color: #ba7233;

}

.item5 {

    background-color: #2f9c50;

}
```

Vlaues of flex :

flex-direction : roe or column
flex