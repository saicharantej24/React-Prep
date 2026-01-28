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
Using objects:
```js
import React from "react";
const App=()=>{
    
    const ob1={
        fn:"sai",
        ln:"charan",
    };
    const fun=(ob1)=>
    {
        return  "Hello"+" "+ob1.fn+" "+ob1.ln;
    }
return (
<div>
<h1> Good morning {fun(ob1)}
</h1>
</div>
);
}

export default App;
```
# Timer 
Index.js:
```js
import React from "react";
// to inject js into html, we need to import react dom
import ReactDOM from "react-dom/client";
import App from "./App";

const root=ReactDOM.createRoot(document.getElementById("root"));
setInterval(()=> 
{
    root.render(<App/>);

},1000);
```
App.js:
```js
import React from "react";
const App=()=>{
   return(
    new Date().toLocaleTimeString()
   )
}
export default App;

```
# Working with Image components:
```js
import React from "react";
const App=()=>{
   return<Imagecalling/>;
};
   const Imagecalling=()=>
{
   return ( 
      <article>
         <Imagecomponent/>
      </article>
   )
}
const Imagecomponent=()=>
{   return(
   <img
   src="data:image/png;base64,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"
   alt="Netfliximg"/>
);
};
export default App;
```
=======
# Styling 
```js
import React from "react";
const App=()=>{
   return<Imagecalling/>;
};
   const Imagecalling=()=>
{
   return ( 
      <article>
         <Imagecomponent/>
         <Title/>
      </article>
   )
}
const Imagecomponent=()=>
{   return(
   <img
   src="data:image/png;base64,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"
   alt="Netfliximg"/>
);
};
const Title=()=>
{
   return(
      <h3 style={{color:"blue",fontSize:23}}>Movie-Stranger things</h3>
   )
};
export default App;
```
```text
1 st brace is to indicate its js code, 2nd { is to indicate the objects.
```
# Using reusable styles
```js
import React from "react";
const App=()=>{
   return<Imagecalling/>;
};
   const Imagecalling=()=>
{
   return ( 
      <article>
         <Imagecomponent/>
         <Title/>
      </article>
   )
}
const Imagecomponent=()=>
{   return(
   <img
   src="data:image/png;base64,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"
   alt="Netfliximg"/>
);
};
const Title=()=>
{
   const Styles=
   {
             heading:
             {
               color:"blue",
               fontSize:30,
             },
             smallHeading:
             {
               color:"red",
               fontSize:40 ,
             },
   };
   return(
      <>
      <h3 style={Styles.heading}>Movie-Stranger things</h3>
       <h3 style={Styles.smallHeading}>Netflix</h3>
       </>
   )
};
export default App;
```
```text 
As of now we learned inline css but we now move to external css for that we need to create a file called index.css
```
Add- import "./index.css"; in index.js
# index.css:
```css
*{
    padding:0 px;
    margin:0 px;
    box-sizing:border-box;
    background-color: aquamarine;
}
```
# using as variables:
Apps.js:
```js
import React from "react";
let title="Stranger things ep-1"
const App=()=>{
   return<Imagecalling/>;
   

};
   const Imagecalling=()=>
{
   return ( 
      <article>
         <Imagecomponent/>
      </article>
   )
}
const Imagecomponent=()=>
{   return(
   <article className="movie">
   <img
   src="data:image/png;base64,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"
   alt="Netfliximg"/>
   <h1>{title}</h1>
   </article>
);
};
 
export default App;
```
# Another ex to use props:
```js
import React from "react";
let obj={
 title:"Stranger things ep-1",
 imgURL:"data:image/png;base64,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",
}
let obj2={
 title:"Netflix FIFA",
 imgURL:"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQO6f-9z8pwUb8ILYRD-pl5rzXiNNHBbxEvaw&s",
}
const App=()=>{
   return(

      <section className="container">
         <Imagecalling title={obj.title} imgurl={obj.imgURL}/>
         <Imagecalling title={obj2.title} imgurl={obj2.imgURL}/>
      </section>
   )
};
   const Imagecalling=(props)=>
{
   return ( 
      <article>
         <Imagecomponent {...props}/>
      </article>
   )
}
const Imagecomponent=(props)=>
{   
   return(
   <article className="movie">
   <img src={props.imgurl}
   alt="Netfliximg"/>
   <h1>{props.title}</h1>
   </article>
);
};
 
export default App;
```
Using objects:
```js
import React from "react";
const App=()=>{
    
    const ob1={
        fn:"sai",
        ln:"charan",
    };
    const fun=(ob1)=>
    {
        return  "Hello"+" "+ob1.fn+" "+ob1.ln;
    }
return (
<div>
<h1> Good morning {fun(ob1)}
</h1>
</div>
);
}

export default App;
```
# Timer 
Index.js:
```js
import React from "react";
// to inject js into html, we need to import react dom
import ReactDOM from "react-dom/client";
import App from "./App";

const root=ReactDOM.createRoot(document.getElementById("root"));
setInterval(()=> 
{
    root.render(<App/>);

},1000);
```
App.js:
```js
import React from "react";
const App=()=>{
   return(
    new Date().toLocaleTimeString()
   )
}
export default App;

```
# Working with Image components:
```js
import React from "react";
const App=()=>{
   return<Imagecalling/>;
};
   const Imagecalling=()=>
{
   return ( 
      <article>
         <Imagecomponent/>
      </article>
   )
}
const Imagecomponent=()=>
{   return(
   <img
   src="data:image/png;base64,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"
   alt="Netfliximg"/>
);
};
export default App;
```
=======
# Styling 
```js
import React from "react";
const App=()=>{
   return<Imagecalling/>;
};
   const Imagecalling=()=>
{
   return ( 
      <article>
         <Imagecomponent/>
         <Title/>
      </article>
   )
}
const Imagecomponent=()=>
{   return(
   <img
   src="data:image/png;base64,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"
   alt="Netfliximg"/>
);
};
const Title=()=>
{
   return(
      <h3 style={{color:"blue",fontSize:23}}>Movie-Stranger things</h3>
   )
};
export default App;
```
```text
1 st brace is to indicate its js code, 2nd { is to indicate the objects.
```
# Using reusable styles
```js
import React from "react";
const App=()=>{
   return<Imagecalling/>;
};
   const Imagecalling=()=>
{
   return ( 
      <article>
         <Imagecomponent/>
         <Title/>
      </article>
   )
}
const Imagecomponent=()=>
{   return(
   <img
   src="data:image/png;base64,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"
   alt="Netfliximg"/>
);
};
const Title=()=>
{
   const Styles=
   {
             heading:
             {
               color:"blue",
               fontSize:30,
             },
             smallHeading:
             {
               color:"red",
               fontSize:40 ,
             },
   };
   return(
      <>
      <h3 style={Styles.heading}>Movie-Stranger things</h3>
       <h3 style={Styles.smallHeading}>Netflix</h3>
       </>
   )
};
export default App;
```
```text 
As of now we learned inline css but we now move to external css for that we need to create a file called index.css
```
Add- import "./index.css"; in index.js
# index.css:
```css
*{
    padding:0 px;
    margin:0 px;
    box-sizing:border-box;
    background-color: aquamarine;
}
```
# using as variables:
Apps.js:
```js
import React from "react";
let title="Stranger things ep-1"
const App=()=>{
   return<Imagecalling/>;
   

};
   const Imagecalling=()=>
{
   return ( 
      <article>
         <Imagecomponent/>
      </article>
   )
}
const Imagecomponent=()=>
{   return(
   <article className="movie">
   <img
   src="data:image/png;base64,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"
   alt="Netfliximg"/>
   <h1>{title}</h1>
   </article>
);
};
 
export default App;
```
# Another ex to use props:
```js
import React from "react";
let obj={
 title:"Stranger things ep-1",
 imgURL:"data:image/png;base64,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",
}
let obj2={
 title:"Netflix FIFA",
 imgURL:"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQO6f-9z8pwUb8ILYRD-pl5rzXiNNHBbxEvaw&s",
}
const App=()=>{
   return(

      <section className="container">
         <Imagecalling title={obj.title} imgurl={obj.imgURL}/>
         <Imagecalling title={obj2.title} imgurl={obj2.imgURL}/>
      </section>
   )
};
   const Imagecalling=(props)=>
{
   return ( 
      <article>
         <Imagecomponent {...props}/>
      </article>
   )
}
const Imagecomponent=(props)=>
{   
   return(
   <article className="movie">
   <img src={props.imgurl}
   alt="Netfliximg"/>
   <h1>{props.title}</h1>
   </article>
);
};
 
export default App;
```

# Another prog:
```text
In this we will learn how to wrtite alt text and in prev prog we find it difficult to create multiple objects so now we will make it all in single object.
```
# App.js:
```js
   import React from "react";
   const data =[
      {
   title:"Stranger things ep-1",
   imgURL:"data:image/png;base64,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",
   },
   {
   // title:"Netflix FIFA",
   imgURL:"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQO6f-9z8pwUb8ILYRD-pl5rzXiNNHBbxEvaw&s",
   },
   ]
   const App=()=>{
      return(
         <section className="container">
            <Imagecalling title={data[0].title} imgurl={data[0].imgURL}/>
            <Imagecalling title={data[1].title} imgurl={data[1].imgURL}/>
         </section>
      )
   };
      const Imagecalling=(props)=>
   {
      return ( 
         <article>
            <Imagecomponent {...props}/>
         </article>
      )
   }
   const Imagecomponent=(props)=>
   {   
      return(
      <article className="movie">
      <img src={props.imgurl}
      alt="Netfliximg"/>
      <h1>{props.title || "Random title"}</h1>
      </article>
   );
   };
   
   export default App;
```
```text
Here we are writing the data like below:
<section className="container">
            <Imagecalling title={data[0].title} imgurl={data[0].imgURL}/>
            <Imagecalling title={data[1].title} imgurl={data[1].imgURL}/>
         </section>

But everytime if data changes we have to write again.
So,we will convert array of objects in to array of HTML elements:
```
# App.js:
```js






