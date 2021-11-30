# Book Search Engine

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Description
![alt googlebooks](assets/books.gif)

Save books found with the Google Books API. Initially this app used a RESTful API, refactored to be a GraphQL API. It uses the MERN stack and utilizes JWT for authentication. A user may sign up and log in to save and delete books from their list.

Try it out at this [link](https://immense-mesa-18388.herokuapp.com/)

## Technologies Used
- React - JavaScript library for building UIs
- JavaScript - programming language
- Node.js - runtime environment
- Express.js - back end web application framework
- MongoDB - non-relational database management system
- MongoDB Atlas - cloud database
- Mongoose - ODM
- GraphQL - data query and manipulation language for APIs
- Apollo Server Express - Express integration of Apollo Server
- JSON Web Token - an open standard used to share security information between two parties
- bcrypt - password-hashing function
- Bootstrap - CSS framework
- Git - version control
- Github - where the repository is hosted
- Visual Studio Code - text editor
- ScreenToGif - for recording short screen captures
- Heroku - where the project is deployed

## Code Snippets
short snippet of GraphQL typeDef
```
input bookToSave {
        bookId: String
        authors: [String]
        description: String
        title: String
        image: String
        link: String
    }

type Query {
    me: User
}

type Mutation {
    addUser(username: String!, email: String!, password: String!): Auth
    login(email: String!, password: String!): Auth
    saveBook(input: bookToSave): User
    removeBook(bookId: String!): User
}
```
onClick function to save a book
```
const handleSaveBook = async (bookId) => {
    // find the book in `searchedBooks` state by the matching id
    const bookToSave = searchedBooks.find((book) => book.bookId === bookId);

    // get token
    const token = Auth.loggedIn() ? Auth.getToken() : null;

    if (!token) {
        return false;
    }

    try {
        const response = await saveBook({
            variables: {
            input: bookToSave
            }
        })

        // if book successfully saves to user's account, save book id to state
        setSavedBookIds([...savedBookIds, bookToSave.bookId]);
    } catch (err) {
        console.error(err);
    }
};
```
Signup form component
```
const handleFormSubmit = async (event) => {
    event.preventDefault();

    // check if form has everything (as per react-bootstrap docs)
    const form = event.currentTarget;
    if (form.checkValidity() === false) {
        event.preventDefault();
        event.stopPropagation();
    }

    try {
        const { data } = await addUser({
            variables: { ...userFormData }
        })

        Auth.login(data.addUser.token);
    } catch (err) {
        console.error(err);
        setShowAlert(true);
    }

    setUserFormData({
        username: '',
        email: '',
        password: '',
    });
};
```

## Author Links
[LinkedIn](https://www.linkedin.com/in/luigilantin/)
[Github](https://github.com/mushymane)