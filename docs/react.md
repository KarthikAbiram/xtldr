---
hide:
  - navigation
---
# React
## Install
1. Download and Install [LTS NodeJS](https://nodejs.org/en/download/).

## Create React App
Command to create react app from command prompt:
`npx create-react-app my-app`

### To Upgrade Dependencies
Install npm-check-updates globally using the command:
`npm install -g npm-check-updates`

Then use below commands to upgrade and install the dependencies:
```
ncu -u
npm install
npm start
```

## React Style Guide
1. [Airbnb React Style Guide](https://github.com/airbnb/javascript/tree/master/react)
## Simple React App Example
Here is a very simple example for React application, to be written in index.js:
```
import React from "react";
import ReactDOM from "react-dom";

const lucky_number = 3;

ReactDOM.render(
  <div>
    <h1>Hello</h1><p>My lucky number is {lucky_number} and here is a random number:{Math.floor(Math.random() * 10)}</p>
    <p className='para' contentEditable='true' spellCheck='false'>Enter your name by clicking here</p>
      </div>,
  document.querySelector("#root")
);
```
Note: You can include javascript expressions (not javascript statement/code) within the HTML code within { }. 

Now, include the index.js in index.html like you normally would, with a minor change of specifying type as 'JSX' instead of 'Javascript' as shown below.
```
<script  src="index.js" type="text/JSX"></script>
```
When applying attributes to HTML elements in JSX, you need to use camel case equivalent. Eg: `contentEditable` instead of `contenteditable`.
## Concepts
### JSX
TBD
### Babel
Babel is a toolchain that is mainly used to convert latest version of javascript code into a backwards compatible version of JavaScript that would be supported by older browsers.

## CSS Inline Style
For CSS inline style, they need to use javascript objects with key-value pairs. The values need to be strings.
```
import React from "react";
import ReactDOM from "react-dom";

var cssInlineStyle = {
  color: "green",
  textDecoration: "underline"
};

ReactDOM.render(
  <div>
    <h1 style={cssInlineStyle}>My Favourite Foods</h1>
    <img
      src="https://i.ytimg.com/vi/CCab5oh0ZOc/maxresdefault.jpg"
      alt="dosa"
    ></img>
  </div>,
  document.getElementById("root")
);
```
## React Components
Use Pascal case for naming React components. Eg: `Heading`
Create a separate jsx file for each React component, which can then be imported and used, similar to a HTML tag. 

Example: 
Heading.jsx, parallel to index.js contains:
```
import React from "react";

function Heading() {
  return <h1>My Favourite Foods</h1>;
}

export default Heading;
```
index.js imports and uses `Heading.jsx` present parallel to index.js:
```
import React from "react";
import ReactDOM from "react-dom";
import Heading from "./Heading"

ReactDOM.render(
  <div>
    <Heading />
    <ul>
      <li>Bacon</li>
      <li>Jamon</li>
      <li>Noodles</li>
    </ul>
  </div>,
  document.getElementById("root")
);
```
### React ES6 Import Export
There can be only one default export from a jsx file. To export multiple items:

`Pi.jsx` file contents:
```
const pi = 3.14;

function DoublePi() {
  return pi * 2;
}

function TriplePi() {
  return pi * 3;
}

export default pi;
export { DoublePi, TriplePi };
```
To import in index.jsx:
```
import React from "react";
import ReactDOM from "react-dom";
import * as pi from "./Pi"

console.log("Various imported items from pi are", pi.default, pi.DoublePi(), pi.TriplePi())
```
Or alternatively:
```
import React from "react";
import ReactDOM from "react-dom";
import pi, {DoublePi, TriplePi} from "./Pi"

console.log("Various imported items from pi are", pi, DoublePi(), TriplePi())
```

Any name can be used while importing the default export (pi). For non-default ones, the exact names have to be used while importing (DoublePi, TriplePi).