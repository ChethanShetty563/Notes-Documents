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

  

    </div>

</body>

</html>
```

``` 
* {

    padding: 0;

    margin: 0;

}

  

.container {

    width: 100px;

    height: 100px;

    background-color: yellow;

    position: absolute;

    animation-name: move;

    animation-duration: 2s;

    animation-iteration-count: infinite;

    animation-direction: alternate;

  

}

  

@keyframes move {

    0%{ left : 5px}

  

    100%{

        left : 300px

    }

}
```