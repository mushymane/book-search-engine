# Book Search Engine

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Description
![alt googlebooks](src/assets/mane.gif)

Save books found with the Google Books API. Initially this app used a RESTful API, refactored to be a GraphQL API. It uses the MERN stack and utilizes JWT for authentication. A user may sign up and log in to save and delete books from their list.

Try it out at this [link]()

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
React/JSX - component that renders the contents of the website
```
const [currentPage, setCurrentPage] = useState('About');

const renderPage = () => {
    if (currentPage === 'About') {
        return <About />;
    }
    if (currentPage === 'Portfolio') {
        return <Portfolio />;
    }
    if (currentPage === 'Contact') {
        return <Contact />;
    }
}

const handlePageChange = (page) => setCurrentPage(page);

return (
    <div className="portfolio-container justify-content-center">
        <Navbar currentPage={currentPage} handlePageChange={handlePageChange} />
        {renderPage()}
        <Footer />
    </div>
)
```

## Author Links
[LinkedIn](https://www.linkedin.com/in/luigilantin/)
[Github](https://github.com/mushymane)