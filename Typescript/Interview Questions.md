1) What is Typescript?
	Typescript is an open source programming language which is built on Javascript and it is maintained by Microsoft.
* It is a strict syntactical superset of javascript and adds optional static typing to the language

2) Why Typescript?
* Static Typed
* Adds another level of compilation
* Itellisense support
* Detects the errors at early stage

3) What are the components of typescript?

* Language
* The typescript compiler
* The typescripy language services

4) What are the basic data types in typescript?
* Number
* String
* boolean
* enum
* void
* null
* undefined
* any
* never
* Array
* unknown
* tuple

5) What is tuple in typescript?

Tuple is new data type which includes two set of values of different data type.

6) What is the difference between null and undefined in typescript?

A value

7) What is the supertype for all data type? why not used?

Answer : Any

8) is typescript understood by browser or Node?

Answer : No

9) How to install typescript?

Answer : npm install -g typescript

10) What is tsconfig?

The presence of tsconfig.json file in a directory indicates that the directory is the root of typescript project. This file specifies the root files and the compiler options required to compile the project

11) What is tsc?
 Answer : Its a transpiler

12) How to create typescript config file?

answer : tsc --init

13) What is a polyfill?

A polyfill is a piece of code used to provide the modern functionlity on ilder broweser that donot nativley support.

tssconfig option :
using lib

14) ypescript vs babel?

Typescript is lnguage and babel is transpiler

15) ES6 vs Typescript?

ES6 refers to version 6 of ECMA sript. Its a standardized name or version which was released in 2011.

Typescript is a language

16) What is static typing in typescript?
Its a tightly coupled and static typed which means it forces to give the type to all the objects

17) Whar are decorators in typesscript?
	   A decorator is a special kind of declartion that can be attached to a class declaration, method, accessor, property or value. Decorator use the form @expression where expression must evalute to function that will be clled at runtim with information about the decorated declartion
	   
18) What is module in typescript?
	In Typescript, just as in ECMAScript 2015, any file containing a top level import or export is considered a module

19) What is namespace in typescript?
	The namespace is a logical grouping of functionalities. It can include interfaces, classes , functions and variables to support a single or a group of related functionalities

20) is namespace available in Javascript?
	1) Answer : No
	
21) What is a SorceMAp file?
	Enable the option in tsconfig.js yhe option is "sourceMap: true"
	
	A sourceMap is basically what it says, a map from one language to another. so the debugger can run the javascript code but show you the line that actually generated it

22)  Inerface are availbe in Typescript? is it availble in Javascript?
	1) It is available in typescript not in javascript
	   
23) Does it allow converting to javascript from JSX?
	1) Inorder to use JSX you must do 2 things
		1) NAme you files with .tsx
		2) Enable jsx option
24) How to publish your typescript application?
	    main : "./output/promise.js"
	    types : "./output/promise.d.ts"
	








