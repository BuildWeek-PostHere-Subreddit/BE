# Back-end Documentation for the Post Here Application

Our base URL: https://backend-posthere-russ-and-mack.herokuapp.com/

## Technologies and Packages
Here is how we built our app and what pieces we used to build it.

### Technology
-NodeJS as a runtime environment
-ExpressJS as a web framework
-Heroku as a hosting environment

### Packages
-bcryptjs: Authentication
-cors: Allows for communication between other sources
-cross-env: Easy utilization of env variables
-dotenv: Easy utilization of env files
-helmet: A security tool
-jest: A testing tool
-jsonwebtoken: A security tool
-knex: A database schema tool
-knex-cleaner: A database schema tool
-nodemon: A Node-like runtine environment 
-pg: An RDBMS
-sqlite3: An RDBMS
-supertest: A testing tool

## Routes
Please refer to the base url at the beginning of this documentation.

### Users

POST REQUEST: base url/users/register: Allows you to register a new user to the database.
-requires: {username: "your username", password: "your password"}

POST REQUEST: base url/users/login: Allows you to log in a previously registered user.
-requires: {username: "your username", password: "your password"}
-returns: {Welcome back user!, token (set to localStorage for our authentication middleware), user ID}

### Posts

GET REQUEST: base url/post/: Gets all posts
-returns: All posts in the database.

GET REQUEST: base url/post/:id/: Gets all posts by :id, where :id is the id of the User
-returns: All posts by that user ID.

POST REQUEST: base url/post/new: Adds a new post.
-requires: {title: "your post title", content: "Your post content", link: A boolean on whether or not your content is a hyperlink, user_id: your user id}

PUT Request: base url/post/:id/:postid/: Updates a post by post id, where :postid is the id of the post, and :id is the id of the user. 
-requires: {any content of a post you'd like to update, your user id, and your post id}

DELETE Request: base url/post/:id/:postid/: Deletes a post by post id, where :postid is the id of the post, and :id is the id of the user. 
-requires: {any content of a post you'd like to delete, your user id, and your post id}

### Subreddits

GET REQUEST: base url/subreddit/: Gets all subreddits in the database
-requires: Authentication

GET REQUEST: base url/subreddit/:id/: Gets a subreddit by the subreddit ID
-requires: Authentication, subreddit id.

POST REQUEST: base url/subreddit/new: Adds a new subreddit to the database
-requires: Authentication, {title: "Your subreddit title"}

