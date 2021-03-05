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




  ---- COMPONENTS ----
  
-->  Stateles Components

  / in ----index ---- .js we need to render our componens /
 ReactDom.render(
 <div> 
  <Book title="Avatar"/> 
 </div>

 document.getElemenById('root');

 /Create a new component ---- Book.js ----- (every componant need to import React from 'react'
 
 const BookTitle = (props) => {
  return (
     <div> 
       <BookTitle title={props.title} </>
     </div>
   )
 }
 
 const Book =(props) +> {     
  return <div>  </div>
 }
 export default Book  /we need to export than we can call from another file...(for example in the index JS files.../
 
 
 
 --> ----  Class Components  ----/ using Booklist.js for an example/
 
 import React,{Component} from 'react'
 
 class BookList extends Component {
 state =  { //classes can have their own componens//
  books: [
    {
      title: 'Star Wars',
      isbn:"abs123"
    },
     {
      title: 'Romeo@Juliet',
      isbn:"abs133"
    }
   ]
 }
 ===LIfecicle methood===
  constructor    //we can create a constructor....and we always need to call super//
  super()
  console.log(1);
  }
  
  componentWillMounr (){   // It eill running before render//
    console.log(2);
  }
  
   componentDidlMounr (){    // It eill running after render//
   console.log(4);
  }
  
  render() {
  console.log(3);
    return(
      <div> this.state.books.map((book,index) => {
        return <div key={index}> {<Book book={book} key={index}/>} </div> //if we using arrays we have to use key cause react needs to now where is the changes in Dom //
        })
      </div>
    );
  }
 }
 export default BookList;
 
/ in our  --- index.js ---
 ReactDom.render(
 <div>
  <BookList"/> 
 </div>

 document.getElemenById('root');
 
 ------ //Changing the ---- Book.JS.... file  we will using now as a Class components //
     if we want to use booklist components from BookList we have to import to our Book file 
     
 import Book from './components/Book.js'
 
 
 Class Book extends Component {
  constructor(props) {
    super(props)
  }
    render() ----> // if it is a class comp. we have to use the render function //
      return(
        <div>
           <h2>{this.props.book.title}</h2>
           <p>{this.props.book.isbm}</p>
        </div>
      );
    }
        ////we dont need to write all the time this. props... we can create a const like this bellow ...  ---- we will use this format ---
        
  Class Book extends Component {
    state ={
      a1:true,
      a2"[],
      selected:null
    }
    
    OnclickHandler = (title) => {
      this.setState({
        selected: title 
        }, () => {
         console.log(this.state.selected)};
    }
 
    render() ----> // if it is a class comp. we have to use the render function //
      
      const {title,isbn} =this.proops.book;
      
      return(
       <div>
         <h2 onClick=() => {(this.OnclickHandler(title)}> {title} </h2>
         <p> {isbm} </p>
       </div>
    );
   } 
