# React-Prep
# React 1st App
```text
terminal:
npx create-react-app demo1
cd demo1
npm start
```
```text
This prog is  just to know how to build from scartch
Initially I deleted all the src folder
Created Index.js
```
# Index.js
```js
import React from "react";
// to inject js into html, we need to import react dom
import ReactDOM from "react-dom/client";
// Normal function
/*
function PrintName()
{
    return <h1>Hello charan</h1>
}
*/
//Arrow function
const PrintName=()=>
{
    return <h1>Hi sai charan, its arrow func</h1>
}


const root=ReactDOM.createRoot(document.getElementById("root"));
root.render(
    <>
    <PrintName/>
    </>
)
```
```text
return <h1>Hi sai charan, its arrow func</h1>
This is written in JSX-Java Script XML.
If we dont use this code will look like below:
```
# App.js
```js
import React from "react";
function App()
{
    // return React.createElement("h1",{className:"heading" },"Hello sai charan");
    return React.createElement(
        "div",{className:"container"},React.createElement("h1",{className:"heading"},"This is written in container")
);

}
export default App;
```
The problem with JSX is we cant return 2 stats once like below. If we do so it returns error.
```js
import React from "react";
function App()
{
return <h1>sai charan</h1>
 <h1>Not possib to return 2 stats in JSX</h1>
}
export default App;
```
```js
So we have to combine them in div to make it happen
App.js
import React from "react";
function App(){
return (<div>
<h1>sai charan</h1>
<h1>Not possib to return 2 stats in JSX so we merged in div</h1>
</div>
);
}
export default App;
```
We cant write js in html but we can write js inside jsx:
```js
import React from "react";
const App=()=>{
    const fn="sai";
return (<div>
<h1>Hello {fn}</h1>
</div>
);
}

export default App;
```


