
``` html 

<!DOCTYPE html>

<html>

<head>

    <title>Signup Page</title>

    <link rel="stylesheet" href="./index.css">

    <meta name="viewport" content="width=device-width, initial-scale=1.0">

</head>

<body>

    <div class="container">

            <form>

                    <h1>Sign up</h1>

                    <label class="labelText">First name</label>

                    <input type="text" placeholder="eg., Mark">

                    <label class="labelText">Last name</label>

                    <input type="text" placeholder="eg., Green">

                    <label>Email</label>

                    <input type="email" placeholder="eg., test@upgrad.com">

                    <label id="password">Password</label>

                    <input type="password" placeholder="eg., xxyyzz">

                    <label>Mobile</label>

                    <input type="tel" placeholder="eg., 1234567890">

            </form>

            <button class="submit-btn">Submit</button>

    </div>

    <script src="./index.js"></script>

</body>

</html>
```

``` css

h1 {

    text-align: center;

}

  

body {

    display: flex;

    align-items: center;

    flex-direction: row;

    justify-content: center;

    font-family: sans-serif;

}

  

.container {

    display: flex;

    flex-direction: column;

    justify-content: center;

    width: 30%;

}

  

form {

    display: flex;

    flex-direction: column;

    justify-content: center;

}

  

.submit-btn {

    background-color: orange;

    color: #fff;

    padding: 2%;

    font-size: 22px;

    margin-top: 10px;

    border: 0;

    cursor: pointer;

}

  

input {

    padding: 2%;

}

  

label {

    font-size: 20px;

    font-weight: bolder;

    margin: 10px 0;

}

  
  
  
  
  

@media (max-width: 500px){

    label {

        color: green;

    }

    .container {

        width: 80%;

    }

  }

  
  

  @media (min-width: 500px) and (max-width: 1000px){

     label {

        color: red;

    }

  }
```