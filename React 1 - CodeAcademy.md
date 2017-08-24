# React 1 - CodeAcademy
React create-app [github](https://github.com/paulhanna1933/create-react-app)
React [Cheatsheet](https://ihatetomatoes.net/wp-content/uploads/2017/01/react-cheat-sheet-v1.pdf)
React [Cheatsheet](https://d3cxrxf04bhbwz.cloudfront.net/cheat-sheets/egghead-react-cheat-sheet-0-14-7.pdf?Expires=1503429443&Signature=jn9l8U4TLiLZaFT5qEO8WuySmGmRVXDaqwftXKyxRGjZIr8UcpNxEJGmQLAct7u1L82E4j9OJE7d9cUTqA0~IJ7FRaOmUnfeuJBN-8GVF8pVTz9SSOW-HrrwqRCBc0R9Co4QxYGwPsgOMevFLQPw0CFL1SfkfBnBBEMzk-vsLOk4sWOHE--JuUmvF31G3hmepKxQYsE1wGk1ONj8aia-oNAmvcF32qd3x2I5RCVqvFnVmJ0xAYlwVRsdnmryotI37V~0kOxNptjJIM8yaOwiFfApm~hfpWXlBU0p9523Q3z4WL6FuGTDdCcbLspgeO0UMyOi0NBso4TJhoOipL7SDQ__&Key-Pair-Id=APKAIEGNPCBY26T6OCUQ)
React [Website](https://facebook.github.io/react/)
React [EventListeners](https://facebook.github.io/react/docs/events.html#supported-events)
JSX [InDepth](https://facebook.github.io/react/docs/jsx-in-depth.html)


Here's an example of a JSX element being saved in a variable:

```javascript
const navBar = <nav>I am a nav bar</nav>;
```


A JSX attribute is written using HTML-like syntax: a name, followed by an equals sign, followed by a value. The value should be wrapped in quotes, like this:

```javascript
my-attribute-name="my-attribute-value"
```


Here are some JSX elements with attributes:

```javascript
<a href="http://www.example.com">Welcome to the Web</a>;

const title = <h1 id="title">Introduction to React.js: Part I</h1>;
```


A single JSX element can have many attributes, just like in HTML:

```javascript
const panda = <img src="images/panda.jpg" alt="panda" width="500px" height="500px" />;
```


a JSX expression must have exactly one outermost element. In other words, this code will work:

```javascript
const paragraphs = (
  <div id="i-am-the-outermost-element">
    <p>I am a paragraph.</p>
    <p>I, too, am a paragraph.</p>
  </div>
);
```


But this code will not work:

```javascript
const paragraphs = (
  <p>I am a paragraph.</p> 
  <p>I, too, am a paragraph.</p>
);
```


You've learned how to write JSX elements! Now it's time to learn how to render them. To render a JSX expression means to make it appear onscreen. The following code will render a JSX expression:

```javascript
ReactDOM.render(<h1>Hello world</h1>, 
document.getElementById('app'));
```


ReactDOM is the name of a JavaScript library. This library contains several React-specific methods, all of which deal with the DOM in some way or another. ReactDOM.render() is the most common way to render JSX. Example: 

```javascript
// Write code here:
ReactDOM.render(
<h1>Render me!</h1>,
document.getElementById('app')
);
```


Move to the right a little more, and you will see this expression:

```javascript
document.getElementById('app')
```


You just learned that ReactDOM.render() makes its first argument appear onscreen. But where on the screen should that first argument appear? The first argument is appended to whatever element is selected by the second argument.


ReactDOM.render()'s first argument should evaluate to a JSX expression, it doesn't have to literally be a JSX expression.
The first argument could also be a variable, so long as that variable evaluates to a JSX expression.

```javascript
const toDoList = (
  <ol>
    <li>Learn React</li>
    <li>Become a Developer</li>
  </ol>
);

ReactDOM.render(
  toDoList, 
  document.getElementById('app')
);
```



```javascript
// Write code here:
const myList = (
<ul>
  <li>one</li>
  <li>two</li>
  <li>three</li>
  <li>four</li>
</ul>
);

ReactDOM.render(
myList, 
document.getElementById('app')
);
```


Grammar in JSX is mostly the same as in HTML, but there are subtle differences to watch out for. Probably the most frequent of these involves the word class. In HTML, it's common to use class as an attribute name:

```markup
<h1 class="big">Hey</h1>
```
In JSX, you can't use the word class! You have to use className instead:

```markup
<h1 className="big">Hey</h1>
```


When you write a self-closing tag in HTML, it is optional to include a forward-slash immediately before the final angle-bracket:

```markup
Fine in HTML with a slash:

  <br />

Also fine, without the slash:

  <br>
```


In JSX, you have to include the slash. If you write a self-closing tag in JSX and forget the slash, you will raise an error:

```markup
Fine in JSX:

  <br />

NOT FINE AT ALL in JSX:

  <br>
```



```javascript
const profile = (
  <div>
    <h1>I AM JENKINS</h1>
    <img src="images/jenkins.png" /> //self closing with jsx requires to end with />
    <article>
      I LIKE TO SIT
      <br/>
      JENKINS IS MY NAME
      <br/>
      THANKS HA LOT
    </article>
  </div>
);
```


You need a way to write code that says, "Even though I am located in between JSX tags, treat me like ordinary JavaScript and not like JSX." You can do this by wrapping your code in curly braces.

```javascript
// Write code here:
ReactDOM.render(
<h1>{2 + 3}</h1>,
 document.getElementById('app')
);
```


You can access variables while inside of a JSX expression, even if those variables were declared on the outside:

```javascript
// Declare a variable:
const name = 'Gerdo';

// Access your variable 
// from inside of a JSX expression:
const greeting = <p>Hello, {name}!</p>;
```


When writing JSX, it's common to use variables to set attributes.

```javascript
// Use a variable to set the `height` and `width` attributes:

const sideLength = "200px";

const panda = (
  <img 
    src="images/panda.jpg" 
    alt="panda" 
    height={sideLength} 
    width={sideLength} />
);
```



```javascript
const pics = {
  panda: "http://bit.ly/1Tqltv5",
  owl: "http://bit.ly/1XGtkM3",
  owlCat: "http://bit.ly/1Upbczi"
}; 

const panda = (
  <img 
    src={pics.panda} 
    alt="Lazy Panda" />
);

const owl = (
  <img 
    src={pics.owl} 
    alt="Unimpressed Owl" />
);

const owlCat = (
  <img 
    src={pics.owlCat} 
    alt="Ghastly Abomination" />
);
```


JSX elements can have event listeners, just like HTML elements can. Programming in React means constantly working with event listeners. You create an event listener by giving a JSX element a special attribute. Here's an example:

```javascript
<img onClick={myFunc} />
```


An event listener attribute's name should be something like onClick or onMouseOver: the word on, plus the type of event that you're listening for.

```javascript
function myFunc() {
  alert('Make myFunc the pFunc... omg that was horrible i am so sorry');
}

<img onClick={myFunc} />
```


Note that in HTML, event listener names are written in all lowercase, such as onclick or onmouseover. In JSX, event listener names are written in camelCase, such as onClick or onMouseOver.


Here's a rule that you need to know: you can not inject an if statement into a JSX expression.
This code will break:

```javascript
(
  <h1>
    {
      if (purchase.complete) {
        'Thank you for placing an order!'
      }
    }
  </h1>
)
```


This is a common way to express conditionals in JSX.

```javascript
let message;

if (user.age >= drinkingAge) {
  message = (
    <h1>
      Hey, check out this alcoholic beverage!
    </h1>
  );
} else {
  message = (
    <h1>
      Hey, check out these earrings I got at Claire's!
    </h1>
  );
}

ReactDOM.render(
  message, 
  document.getElementById('app')
);
```



```javascript
function coinToss() {
  // This function will randomly return either 'heads' or 'tails'.
  return Math.random() < 0.5 ? 'heads' : 'tails';
}

const pics = {
  kitty: 'https://s3.amazonaws.com/codecademy-content/courses/React/react_photo-kitty.jpg',
  doggy: 'https://s3.amazonaws.com/codecademy-content/courses/React/react_photo-puppy.jpeg'
};
let img;

// if/else statement begins here:
if (coinToss() === 'heads') {
  img = (
    <img src={pics.kitty} />
  );
} else {
  img = ( 
    <img src={pics.doggy} />
  );
}

ReactDOM.render(img, document.getElementById('app'));
```


There's a more compact way to write conditionals in JSX: the ternary operator.
Here's how you might use the ternary operator in a JSX expression:

```javascript
const headline = (
  <h1>
    { age >= drinkingAge ? 'Buy Drink' : 'Do Teen Stuff' }
  </h1>
);
```


We're going to cover one final way of writing conditionals in React: the && operator. Example:

```javascript
const tasty = (
  <ul>
    <li>Applesauce</li>
    { !baby && <li>Pizza</li> }
    { age > 15 && <li>Brussels Sprouts</li> }
    { age > 20 && <li>Oysters</li> }
    { age > 25 && <li>Grappa</li> }
  </ul>
);
```


The array method .map() comes up often in React. It's good to get in the habit of using it alongside JSX.
If you want to create a list of JSX elements, then .map() is often your best bet. It can look odd at first:

```javascript
const strings = ['Home', 'Shop', 'About Me'];

const listItems = strings.map(string => <li>{string}</li>);

<ul>{listItems}</ul>
```


When you make a list in JSX, sometimes your list will need to include something called keys:

```javascript
<ul>
  <li key="li-01">Example1</li>
  <li key="li-02">Example2</li>
  <li key="li-03">Example3</li>
</ul>
```


You can write React code without using JSX at all!
The following JSX expression:

```javascript
const h1 = <h1>Hello world</h1>;
```
can be rewritten without JSX, like this:

```javascript
const h1 = React.createElement(
  "h1",
  null,
  "Hello, world"
);
```


React applications are made out of components.
What's a component? A component is a small, reusable chunk of code that is responsible for one job. That job is often to render some HTML.

```javascript
import React from 'react';
import ReactDOM from 'react-dom';

class MyComponentClass extends React.Component {
  render() {
    return <h1>Hello world</h1>;
  }
};

ReactDOM.render(
  <MyComponentClass />,
  document.getElementById('app')
);
```


Here's another fact about components: every component must come from a component class. A component class is like a factory that creates components. If you have a component class, then you can use that class to produce as many components as you want.

To make a component class, you use a base class from the React library: React.Component. React.Component is a JavaScript class. To create your own component class, you must subclass React.Component. You can do this by using the syntax:

```javascript
class YourComponentNameGoesHere extends React.Component {}.
```


Component class variable names must begin with capital letters! This adheres to JavaScript's class syntax. It also adheres to a broader programming convention in which class names are written in UpperCamelCase. 


Like all JavaScript classes, this one needs a body. The body will act as a set of instructions, explaining to your component class how it should build a React component.

```javascript
{
  render() {
    return <h1>Hello world</h1>;
  }
}
```


A component class is like a factory that builds components. It builds these components by consulting a set of instructions, which you must provide. Let's talk about these instructions! For starters, these instructions should take the form of a class declaration body. That means that they will be delimited by curly braces, like this:

```javascript
class ComponentFactory extends React.Component {
    // instructions go here, between the curly braces
}
```
There is only one property that you have to include in your instructions: a render method.

```javascript
class ComponentFactory extends React.Component {
  render() {}
}
```
A render method must contain a return statement. Usually, this return statement returns a JSX expression:

```javascript
class ComponentFactory extends React.Component {
  render() {
    return <h1>Hello world</h1>;
  }
}
```


So, let's make a React component! It only takes one more line:

```javascript
<MyComponentClass />
```



```javascript
class MyComponentClass extends React.Component
{ // everything in between these curly-braces is instructions for how to build components

  render() {
    return <h1>Hello world</h1>;
  }
}
```


Whenever you make a component, that component inherits all of the methods of its component class. MyComponentClass has one method: MyComponentClass.render(). Therefore, <MyComponentClass /> also has a method named render. You could make a million different <MyComponentClass /> instances, and each one would inherit this same exact render method. To call a component's render method, you pass that component to ReactDOM.render(). Notice your component, being passed as ReactDOM.render()'s first argument:

```javascript
ReactDOM.render(
  <MyComponentClass />,
  document.getElementById('app')
);
```



```javascript
import React from 'react';
import ReactDOM from 'react-dom';

class MyComponentClass extends React.Component {
  render() {
    return <h1>Hello world</h1>;
  }
}

// component goes here:
ReactDOM.render(
<MyComponentClass />,
  document.getElementById('app')
)
```


Take a look at this HTML:

```markup
<blockquote>
  <p>
    The world is full of objects, more or less interesting; I do not wish to add any more.
  </p>
  <cite>
    <a target="_blank"
      href="http://bit.ly/1WGzM4G">
      Douglas Huebler
    </a>
  </cite>
</blockquote>
```
How might you make a React component that renders this HTML? Like this: 

```javascript
import React from 'react';
import ReactDOM from 'react-dom';

class QuoteMaker extends React.Component {
  render() {
    return (
      <blockquote>
        <p>
          The world is full of objects, more or less interesting; I do not wish to add any more.
        </p>
        <cite>
          <a target="_blank"
            href="http://bit.ly/1WGzM4G">
            Douglas Huebler
          </a>
        </cite>
      </blockquote>
    );
  }
};

ReactDOM.render(
  <QuoteMaker />,
  document.getElementById('app')
);
```


Take a look at this JavaScript object named redPanda:

```javascript
const redPanda = {
  src: 'http://bit.ly/1U92LL3',
  alt: 'Red Panda',
  width:  '200px
};
```
How could you render a React component, and get a picture with redPanda's properties?

```javascript
class RedPanda extends React.Component {
  render() {
    return (
      <div>
        <h1>Cute Red Panda</h1>
        <img 
          src={redPanda.src} 
          alt={redPanda.alt} 
          width={redPanda.width} />
      </div>
    );
  }
}

ReactDOM.render(
  <RedPanda />,
  document.getElementById('app')
);
```



```javascript
import React from 'react';
import ReactDOM from 'react-dom';


const owl = {
  title: "Excellent Owl",
  src: "https://s3.amazonaws.com/codecademy-content/courses/React/react_photo-owl.jpg"
};

class Owl extends React.Component{
  render(){
    return(
    	<div>
        <h1>{owl.title}</h1>
        <img 
          src={owl.src} 
          alt={owl.title} 
           />
      </div>
    );
  };
}

ReactDOM.render(
<Owl />,
document.getElementById('app')
)
```


A render() function can also be a fine place to put simple calculations that need to happen right before a component renders. Here's an example of some calculations inside of a render function:

```javascript
class Random extends React.Component {
  render() {

    // First, some logic that must happen
    // before rendering:
    const n = Math.floor(Math.random()*10+1);

    // Next, a return statement
    // using that logic:
    return <h1>The number is {n}!</h1>;
  }
}
```


Watch out for this common mistake:

```javascript
class Random extends React.Component {

  // This should be in the render function:
  const n = Math.floor(Math.random()*10+1);

  render() {
    return <h1>The number is {n}!</h1>;
  }
};
```


How might you use a conditional statement inside of a render() function?

```javascript
class TodaysPlan extends React.Component {
  render() {
    let task;
    if (!apocalypse) {
      task = 'learn React.js'
    } else {
      task = 'run around'
    }

    return <h1>Today I am going to {task}!</h1>;
  }
}
```
Notice that the if statement is located inside of the render function, but before the return statement. This is pretty much the only way that you will ever see an if statement used in a render function.

```javascript
const fiftyFifty = Math.random() < 0.5;

// New component class starts here:
class TonightsPlan extends React.Component {
  render() {
    if (fiftyFifty) {
      return <h1>Tonight I'm going out WOOO</h1>;
    } else {
      return <h1>Tonight I'm going to bed WOOO</h1>;
    }
  }
}

ReactDOM.render(
	<TonightsPlan />,
	document.getElementById('app')
);
```


The word this gets used in React a lot! You are especially likely to see this inside of the body of a component class declaration. Here's an example:

```javascript
class IceCreamGuy extends React.Component {
  //This is a getter method
  get food() {
    return 'ice cream';
  }

  render() {
    return <h1>I like {this.food}.</h1>;
  }
}
```



```javascript
import React from 'react';
import ReactDOM from 'react-dom';

class MyName extends React.Component {
	// name property goes here:
// This is a getter function
get name() {
  return 'Paul Hanna';
}

  render() {
    return <h1>My name is {this.name}.</h1>;
  }
}

ReactDOM.render(<MyName />, document.getElementById('app'));
```


Render functions often contain event listeners. Here's an example of an event listener in a render function:

```javascript
render() {
  return (
    <div onHover={myFunc}>
    </div>
  );
}
```
In React, you define event handlers as methods on a component class. Like this:

```javascript
class MyClass extends React.Component {
  myFunc() {
    alert('Stop it.  Stop hovering.');
  }

  render() {
    return (
      <div onHover={this.myFunc}>
      </div>;
    );
  }
}
```
Notice above that the component class has two methods: .myFunc() and .render(). .myFunc() is being used as an event handler. .myFunc() will be called any time that a user hovers over the rendered <div></div>.



```javascript
import React from 'react';
import ReactDOM from 'react-dom';

class Button extends React.Component {
  scream() {
    alert('AAAAAAAAHHH!!!!!');
  }

  render() {
    return <button onClick={this.scream}>AAAAAH!</button>;
  }
}

ReactDOM.render(
<Button />,
document.getElementById('app')
)
```


























