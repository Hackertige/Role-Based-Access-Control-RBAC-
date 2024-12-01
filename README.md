# Role-Based-Access-Control-RBAC-
 implementation   regarding Authentication, Authorization, and Role-Based Access Control (RBAC). 
# The project has implementation of 
1. Authentication
2 . Validation
3 . Authorization
4 . Role based access controls for CRUD APIs
   # Setup and Usage

1. To install dependency use npm install
2.  To start server use npm start

# Models
1 .User Model is kept for Authentication, Authorization and Validation purpose.
2 .Post Model for CRUD APIs

# API Flows
1. Import this Postman collection to view all important APIs.
2. api/auth/login and api/auth/signup are public endpoints.
3. Rest all other CRUD endpoints can only be accessed via proving that a user is authenticated as well as authorized.

Normal User is allowed only to retrieve the Posts in MongoDB in paginated way (if they wish to), so as to handle huge no. of posts.
Admin can perform all CRUD operations on Posts document in mongoDB. When server is started Admin user is created by default if User collection is empty. Credentials for Admin user is as follows
Name : admin
email : admin@admin.com
password : admin
NOTE : All CRUD APIs require JWT authentication.
## MongoDB Integration with Postman

This project uses MongoDB as the database to store user data. Here's how to connect MongoDB, run the server, and test the APIs using Postman.


### Setting up MongoDB
1. Install and start MongoDB on your system or use a cloud service like [MongoDB Atlas](https://www.mongodb.com/cloud/atlas).
2. Update the `.env` file with the MongoDB connection string:
   ```env
   MONGO_URI=mongodb://localhost:27017/myDatabase // for exmaple in this case the database name is models. 

# Folder overview
validator : Has all necessary logic to validate the User Model fields.
routes : Has all API endpoints and defines what middlewares should be used for a particular endpoint.
model : Has DB schema that is followed for collections throughout the project.
middleware : Has necessary logic to check authourization and access level of a particular user.
controller : Has the logic to handle the incoming request and perform the proper DB operations.
config : Has config for JWT secrets.
