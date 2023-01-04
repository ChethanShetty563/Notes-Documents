
## Introduction - Javascript as a systems language

* John Bardeen ,walter Brattain and william Shockley invented the transistor in 1947
* From their revolutionary building block, engineers could design and manufacture digital circuits far more complex than those possible earlier.
*  Each decade that followed has seen a new generation of these devices: smaller, faster, and cheaper, often by orders of magnitude.

* By the 1970s, corporations and universities could afford mainframe computers small enough to fit in a single room, and powerful enough that they could serve multiple users simultaneously.
* _Ken Thompson_ and _Dennis Ritchie_ at Bell Labs developed the operating system Unix, and the programming language **C** to write it
* They built constructs into their system, like processes, threads, streams, and the hierarchical filesystem
* By 1990s A personal computer (PC)_ was light and cheap enough to be found on workplace and dormitory desktops
* It was within this landscape of technology that _Sir Tim Berners-Lee_ invented the _World Wide Web,_ and _Brendan Eich_ created **JavaScript**.
* Given its familiar setting of a webpage, JavaScript makes high-level tasks easy. Web pages are filled with text and tags, so combining two strings is easy:

```javascript
// combine-text.js  
const s1 = "first string";  
const s2 = "second string";  
let s3 = s1 + s2;
```

Try to do the samething c 
```c
// combine-text.c   
const char *s1 = "first string";  
const char *s2 = "second string";  
int size = strlen(s1) + strlen(s2);  
char *buffer = (char *)malloc(size + 1); // One more for the 0x00 byte that terminates strings   
strcpy(buffer, s1);  
strcat(buffer, s2);  
free(buffer); // Never forget to free memory!
```
The two string literals are easy to define, but after that, it gets a lot harder. Without automatic memory management, it's your responsibility as a developer to determine how much memory you need, allocate it from the system, write to it without overwriting the buffer, and then free it afterwards.

* Emerging from genartions of computing decades , people were doing different things with these 2 lang
* there's no real reason the design, purpose, or use that drives these two languages, C and JavaScript, should necessarily come together.
* But they did, because in 2008 Google released Chrome, and in 2009, _Ryan Dahl_ wrote **Node.js.**
* Chrome uses multiple processes to render different tabs, ensuring their isolation.
* Chrome was released open source and built on WebKit, but one part inside was completely new.

With V8 under the hood, how fast can Node run JavaScript? Let's write a little program to show execution speed:

```javascript
// speed-loop.js  
function main() {  
  const cycles = 1000000000;  
  let start = Date.now();  
  for (let i = 0; i < cycles; i++) {  
    /* Empty loop */  
  }  
  let end = Date.now();  
  let duration = (end - start) / 1000;  
  console.log("JavaScript looped %d times in %d seconds", cycles, duration);  
}  
main();

```
The following is the output for speed-loop.js:
```
node -v
v14.13.1
node speed-loop.js
JavaScript looped 1000000000 times in 0.311 seconds

```

Try to compare with other language like C, java and python

Node runs code fast enough so that you don't have to worry that your application might be slowed down by the execution speed.

As V8 compiles JavaScript rather than interpreting it, Node lets you enjoy high-level language features like automatic memory management and dynamic types, without having to give up the performance of a natively-compiled binary.

* Node.js imagines JavaScript as a systems language, like C.
* s a systems language, JavaScript can manipulate memory buffers, processes and streams, and files and sockets.

```
 "Node's goal is to provide an easy way to build scalable network programs."

– Ryan Dahl, creator of Node.js
```

## The Unix design philosophy

* T\As a network application scales, the volume of information it must recognize, organize, and maintain increases
* he volume , in terms of I/O streams , memory usage and processor load, expands as more clients connect.

-   Can a data layer designed for storing a few thousand records accommodate a few million?
-   Are the algorithms used to search a handful of records efficient enough to search many more?
-   Can this server handle 10,000 simultaneous client connections?


Node chose clarity and simplicity instead, echoing a philosophy from decades earlier:

```
"Write programs that do one thing and do it well.  
Write programs to work together.  
Write programs to handle text streams, because that is a universal interface."

-Peter H. Salus, A Quarter-Century of Unix, 1994
```

-   Node's design favors simplicity over complexity
-   Node uses familiar POSIX APIs, rather than attempting an improvement
-   Node does everything with events, and doesn't need threads
-   Node leverages the existing C libraries, rather than trying to reimplement their functionality
-   Node favors text over binary formats

### POSIX - Portable operating system interface

* POSIX defines standard APIs for UNIX.
* Its adopted in all unix based OS
* The IEEE created and maintains POSIX standard
* Refer [https://nodejs.org/api/fs.html] 

### Events for everything

 f a program asks the operating system to open a file on the disk, that task might complete right away. Or, it might take a moment for the disk to spin up, or for other file system activity the operating system is working on to finish before it can perform this new request.
 
 For systems programmers using languages like C and Java, the standard and accepted tool to use to solve this problem is the **thread.**
 
For web developers using HTML and JavaScript, the way to do this is the event as follows:

``` JAvascript
<button onclick="myFunction()">Click me</button>
```

Node showed us that JavaScript doesn't need threads to be useful as a systems language.

###  Standard Libraries
* Node is built on standard C libraries. Ex : TLS and SSL are implemented by OpenSSL
* When the javscript hashes a cryptographic key, its not javascript doing the work. Javscript run by node and has called the API of C code of OPen SSL

Dahl was guided by a few rigid principles:
-    A Node program/process runs on a single thread, ordering execution through an event loop
-    Web applications are I/O intensive, so the focus should be on making I/O fast
-    Program flow is always directed through asynchronous callbacks
-    Expensive CPU operations should be split off into separate parallel processes, emitting events as results arrive
-    Complex programs should be assembled from simpler programs

JavaScript's asynchronous, event-driven design fits neatly into this model. Applications express interest in some future event, and are notified when that event occurs. This common JavaScript pattern should be familiar to you:

```Javascript
Window.onload = function() {  
  // When all requested document resources are loaded,  
  // do something with the resulting environment  
}  
element.onclick = function() {  
  // Do something when the user clicks on this element  
}
```

Node adds an enormous amount of new functionality to JavaScript. Primarily, the additions provide evented I/O libraries offering the developer system access not available to browser-based JavaScript, such as writing to the filesystem or opening another system process.

### Events
 * Many functions in Node API emit events
 * These events are instance of events.EventEmitter
* The following code sets Node's EventEmitter object as the prototype of a function constructor we define

```JAvascript
// File counter.js  
// Load Node's 'events' module, and point directly to EventEmitter there  
const EventEmitter = require('events').EventEmitter;  
// Define our Counter function  
const Counter = function(i) { // Takes a starting number  
  this.increment = function() { // The counter's increment method  
    i++; // Increment the count we hold  
    this.emit('incremented', i); // Emit an event named incremented  
  }  
}  
// Base our Counter on Node's EventEmitter  
Counter.prototype = new EventEmitter(); // We did this afterwards, not before!  
// Now that we've defined our objects, let's see them in action  
// Make a new Counter starting at 10  
const counter = new Counter(10);  
// Define a callback function which logs the number n you give it  
const callback = function(n) {  
  console.log(n);  
}  
// Counter is an EventEmitter, so it comes with addListener  
counter.addListener('incremented', callback);  
counter.increment(); // 11  
counter.increment(); // 12
```

With EventEmitter, Node can handle I/O data streams in an event-oriented manner, performing long-running tasks while keeping true to Node's principles of asynchronous, non-blocking programming:
``` JAvascript
// File stream.js  
// Use Node's stream module, and get Readable inside  
let Readable = require('stream').Readable;  
// Make our own readable stream, named r  
let r = new Readable;  
// Start the count at 0  
let count = 0;  
// Downstream code will call r's _read function when it wants some data from r  
r._read = function() {  
  count++;  
  if (count > 10) { // After our count has grown beyond 10  
    return r.push(null); // Push null downstream to signal we've got no more data  
  }  
  setTimeout(() => r.push(count + '\n'), 500); // A half second from now, push our count on a line  
};  
// Have our readable send the data it produces to standard out  
r.pipe(process.stdout);
```

This example creates a readable stream r, and pipes its output to the standard out. Every 500 milliseconds, code increments a counter and pushes a line of text with the current count downstream
Node consistently implements I/O operations as asynchronous, evented data streams. This design choice enables Node's excellent performance. Instead of creating a thread (or spinning up an entire process) for a long-running task like a file upload that a stream may represent, Node only needs to commit the resources to handle callbacks. Additionally, in the long stretches of time in between the short moments when the stream is pushing data, Node's event loop is free to process other instructions.

As an exercise, re-implement stream.js to send the data r produces to a file instead of the terminal

```JAvascript
// File stream2file.js
// Bring in Node's file system module
const fs = require('fs')
// Make the file counter.txt we can fill by writing data to writeable stream w
const w = fs.createWriteStream('./counter.txt', { flags: 'w', mode: 0666 });
let Readable = require('stream').Readable;
let r = new Readable();
let count = 0;
r._read = function () {
  count++;
  if (count > 10) {
    return r.push(null);
  }
  setTimeout(() => r.push(count + '\n'), 500);
};
// Put w beneath r instead

r.pipe(w);
```

## Modularity

***"Developers should build a program out of simple parts connected by well-defined interfaces, so problems are local, and parts of the program can be replaced in the future versions to support new features. This rule aims to save time on debugging complex code that is complex, long, and unreadable."***

Normally you add the javscript to html in below way 

```
<head>  
<script src="fileA.js"></script>  
<script src="fileB.js"></script>  
<script src="fileC.js"></script>  
<script src="fileD.js"></script>  
...  
</head>
```

The above format works but leads to number of problems :
* The page must declare all the possible dependencies before any are needed are used
* The scripts are not encapsulated. Code in every file writes to same global object. Adding a new dependecy may break an earlier one
* fileA cannot address filB as a collection

Javascript needed a standard way to load and share discreet program and modules and found one in 2009 with the commoJs Module specification

Node follows this specification, making it easy to define and share bits of reusable code called **modules** or **packages.**

Metadata about the package, such as its name, version, and software license, lives in an additional file named package.json. The JSON contents of this file are easily both human and machine-readable. Let's take a look: 
```
{  
  "name": "mypackage1",  
  "version": "0.1.2",  
  "dependencies": {  
    "jquery": "^3.1.0",  
    "bluebird": "^3.4.1",  
  },  
  "license": "MIT"  
}
```

Version numbers follow the **Semantic Versioning (SemVer)** rules, with a pattern like Major.Minor.Patch. Looking at the incremented version numbers of a package your code has been using, here's what that means:
-   **Major:** There's a change in the purpose or outcome of the API. If your code calls an updated function, it may break or produce an unintended result. Figure out what's changed, and determine if it affects your code.
-   **Minor:** The package has added functionality, but remains compatible. Run all your tests, and you're good to go. Check out the documentation if you're curious, as there might be new, more advanced parts of the API alongside the functions and objects you're familiar with.
-   **Patch:** The package fixed a bug, improved performance, or refactored a little. Run all your tests, and you're good to go.

## The network

* Node supports standard network protocols such as HTTP, TLS/SSL and UDP
* With the above support we can easily build scalble programs compartivley to AJAX solutions

Lets write a simple program that sends a UDP packet to another node :
```
const dgram = require('dgram');  
let client = dgram.createSocket("udp4");  
let server = dgram.createSocket("udp4");  
let message = process.argv[2] || "message";  
message = Buffer.from(message);  
server  
.on('message', msg => {  
  process.stdout.write(`Got message: ${msg}\n`);  
  process.exit();  
})  
.bind(41234);  
client.send(message, 0, message.length, 41234, "localhost");
```

### V8, javascript and optimizations

* V8 is Google's javascript engine, written in c++
* It compiles and executes javascript code inside of a VM
* V8 manages Node's main process thread.
* When executing javscript, V8 does so in its own process and its internal behavior is not controlled by Node