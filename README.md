# React_learning

- Create a react app in terminal / 
  npx create-react-app my-app
  cd my-app
  npm start
  
- Create index.js (for example)
we have to import from React... ...

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

 /
 Create a new component ---- Book.js ----- (every componant need to import React from 'react'
 
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
  
  componentWillMount (){   // It will running before render//
    console.log(2);
  }
  
   componentDidlMount (){    // It will running after render//   
   console.log(4);
    this.setState({
      books: [...this.state.books, (title: "Egri csillagok", isbn:"ert983")]
    });
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
    state = {
      a1: true,
      a2: [],
      selected: null,
      title: this.props.book.title
    }
    
    OnclickHandler = (title) => (event) => {
      this.setState({
        selected: title 
        }, () => {
         console.log(this.state.selected)};
    }
    componentWilReceiveProps(nexdtProps) {
     this.setState({
       title:nextProps.book.title
     });
   }
 
    render() ----> // if it is a class comp. we have to use the render function //
      
      const {title,isbn} =this.proops.book;
      
      return(
       <div>
         <h2 BookTitle title={this.state.title} nclickFunc={this.OnclickHandler} </h2>
         <p> {isbm} </p>
       </div>
    );
   } 
   
   export default Book;

?If we want to change our state we can use set state... example bellow :
if we use props item it cant change outside the state.... so we can do thing like this ---- 
 //  componentWilReceiveProps(nexdtProps) {
   this.setState({
     title:nextProps.book.title
   });
 }

----- Lifecycles components ----

  class Example extends React.Component {
  static getDerivedStateFromProps(props, state) {
    // ...
  }
}

The new static getDerivedStateFromProps lifecycle is invoked after a component is instantiated as well as before it is re-rendered. It can return an object to update state, or null to indicate that the new props do not require any state updates.

Together with componentDidUpdate, this new lifecycle should cover all use cases for the legacy componentWillReceiveProps.

---- more example here:   https://reactjs.org/blog/2018/03/27/update-on-async-rendering.html   -----
