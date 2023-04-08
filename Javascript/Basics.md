### Variables

Variables are the first building blocks you will be introduced to when learning any prigramming language,

Variables are like containers or placeholders in computer programs where data can be stored and manipulated. When a variable is created, a certain amount of memory is reserved for it, and data can be assigned to or retrieved from that memory location by referencing the variable name.

How do i declare a variable in JS?

``` js
var firstName;  %%Declare%%
firstname = "chethan";  %%Initialize%%
firstname = "Shetty"  %%Manipulate%%
```

Other ways 

``` js
let nr1 = 12; 
var nr2 = 8;
const PI = 3.14159;
```

`var` has **global scope** and `let` has **block scope**. `var`'s global scope means that you can use the variables defined with `var` in the entire script. On the other hand, `let`'s block scope means you can only use variables defined with `let` in the specific block of code in which they were defined. Remember, a block of code will always start with `{` and end with `}`, which is how you can recognize them.

On the other hand, `const` is used for variables that only get a value assigned once—for example, the value of pi, which will not change. If you try reassigning a value declared with `const`, you will get an error:

``` js
const someConstant = 3; 
someConstant = 4;
```

### Primitive Data Types

Variables can be used to store different types of data, such as numbers, text, or Boolean values, and they can be manipulated in various ways through programming operations and algorithms. By using variables, programmers can create more flexible and dynamic programs that can adapt to changing conditions and input data.

* .JavaScript is a loosely typed language
* This means that JavaScript determines the type based on the value
* For example, if you declared a value of 5, JavaScript will automatically define it as a number type.

``` js
let singleString = 'Hi there!'; let doubleString = "How are you?";
```

### String 

A string is used to store a text value. It is a sequence of characters. There are different ways to declare a string:

-   Double quotes
-   Single quotes
-   Backticks: special template strings in which you can use variables directly

The single and double quotes can both be used like so

### Number

-   The number data type in JavaScript is used to represent numeric values.
-   JavaScript uses a single data type (number) to represent different types of numbers, including integers, decimals, signed, and unsigned numbers.
-   JavaScript uses a 64-bit floating-point number to store numeric values, which means it can store large numbers with decimal points.
-   The number data type supports various mathematical operations like addition, subtraction, multiplication, and division.

``` js
let intNr = 1;
let decNr = 1.5;
let expNr = 1.4e15;
let octNr = 0o10; //decimal version would be 8 
let hexNr = 0x3E8; //decimal version would be 1000
let binNr = 0b101; //decimal version would be 5
```

## BigInt

The limits of the number data type are between 253-1 and -(253-1). In case you were to need a bigger (or smaller) number, BigInt comes into play. A BigInt data type can be recognized by the postfix `n`:

```
let bigNr = 90071992547409920n;
```

Let's see what happens when we start to do some calculations between our previously made integer Number, `intNr`, and BigInt, `bigNr`:

```
let result = bigNr + intNr;
```

The output will be as follows:

```
Uncaught TypeError: Cannot mix BigInt and other types, use explicit conversions
```

Uh-oh, a `TypeError`! It is very clear about what is going wrong. We cannot mix BigInt with the Number data type to perform operations. This is something to keep in mind for later when actually working with BigInt—you can only operate on BigInt with other BigInts.