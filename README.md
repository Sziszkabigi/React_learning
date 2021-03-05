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




Componens
- Statles Components
 /Create a new component Book.js(every componant need to import React from 'react'
 cinst Book =() +> {     
  retun <div> Book </div>
 }
 export default Book  /we need to export than we can call from another file...(for example in the index JS files.../
