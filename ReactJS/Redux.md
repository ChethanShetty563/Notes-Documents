### 1.) What is Redux?

A State managment system for cross- component or app-wide state.

We have already used the state using the react hooks such as useState and useReducer hooks.
And we have already seen the state in before project

We can split the definition of state into 3 parts :
* Local state
	* A state when data chnages it will be reflected in UI and it  belongs to a single component
	* Ex : Listening to user input  in a input field and toggling a "Show more" details field
	* Should be managed component-internal with useState()/useReducer()
* Cross Component state
	* State that affects multiple component
	* Ex : opne/closed state of a modal overlay
	* Require prop chaining/prop drilling
* App-wide state
	* State that affects the entire app (most/all the components)
	* Ex : user authentication status
	* Require "prop chains"/ prop drilling

Redux and React Context solves the same problem

### REdux vs React Context

React Contecxt : Complex Setup/ Managment, Performance

### How redux works?

Redux is all about having one central data(state) store for application
One store for all your state in application

Ex : If authentiction state chnages we have to get to know so that we can react accordingly

Components subscribe to the store. Components gets the data whenever they change

How do we change the data in store?
Compoenent never directly manipulate the store data
We don't have the data flow in other direction

For this we have Reducer function
We have to set uo thereducer whihc manipulate the data

Reducer function is function which takes the input and transform that input


When do we chnage the data whenever we make some action

So Component trigger the action or Dispatch

Action is normal javascript object which describes the kind of operation that reducer should perfoem
![[Pasted image 20230129112410.png]]

















