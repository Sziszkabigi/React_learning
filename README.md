# React_learning

- Create a react app in terminal / 
  npx create-react-app my-app
  cd my-app
  npm start
  
- Create index.js (for example)
we have to import from React... 
/
import React from 'react';
import ReactDOM from 'react-dom';

const element = <h1> Hello World!</h1>;
console.log(element);
ReactDOM.render(element, document.getElementById('root'));
/
- Import bootstrap / import 'bootstrap/dist/css/bootstrap.css';  /




  ---- COMPONENS ----
  
-  Stateles Components

  / in ----index ---- .js we need to render our componens /
 ReactDom.render(
 <div>
  <Book title="Avatar"/> 
 </div>
 );

 /Create a new component ---- Book.js ----- (every componant need to import React from 'react'
 
 const BookTitle = (props) => {
  return  <di> 
            <BookTitle title={props.title} </>
          </div>
   )
 }
 
 const Book =(props) +> {     
  retun <div>  </div>
 }
 export default Book  /we need to export than we can call from another file...(for example in the index JS files.../
