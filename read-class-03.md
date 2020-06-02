1. Why would a developer choose to make data models?
- a developer would want to choose to make a data model so that there is a set of standards for how a specific set of data is going to look. This allows for less miscommunication between different teams and to allow developers to have an easier time locating and using data. (Source: https://www.dataversity.net/data-models-many-benefits-10/#:~:text=Models%20promote%20consensus%20among%20developers,easier%20to%20maintain%20and%20extend.)
2. What purpose do CRUD operations serve?
- These are 4 powerful commands (create, read, update and delete) that allow the programmer and sometimes user to manipulate the data that is in the database. (Source: https://en.wikipedia.org/wiki/Create,_read,_update_and_delete#:~:text=In%20computer%20programming%2C%20create%2C%20read,or%20destroy%20instead%20of%20delete.)
3. What kind of database is Postgres? What kind of database is MongoDB?
- Postgres is a relational database that is very strict in it's formatting. It will pretty much only allow you to have traditional tables with rows and columns. They also use SQL language rather than node.js language. From what I'm reading, MongoDB allows you to have more analytical power than Postgres. MongoDB appears to be less rigid and lets you create data of any shape/size. (Source: https://www.mongodb.com/compare/mongodb-postgresql)
4. What is Mongoose and why do we need it?
- Mongoose is a Object Data Modeling (ODM) library for MongoDB and Nose.js. It manages relationships b/w data, provides schema validation and uses it to translate b/w objects in code and the representation of those objects in MongoDB. We need it because it acts as a liason between the node.js files we create and the database that is MongoDB. 

5. Define three related pieces of data in a possible application. An example for a store application might be Product,Category and Department. Describe the constraints and rules on each piece of data and how you would relate these pieces to each other. For example, each Product has a Category and belongs in a Department.
- User Order Number: a unique number sequence for a specific order. 
- The user associated with the order: an email, shipping address, preferred credit card and the orders under that profile. 
- The stock of a specific store: a database of what items are in stock at a store that change depending on when a user orders a certain item fromt hat sort. 

Vocab: 
-Non SQL (NoSQL): a type of database that uses noSQL does so in means other than the SQL language. 
- Object Relation Mapping (ORM): a programming technique for converting data without having to use SQL. 
- Structured Query Language (SQL): domain specific language used in programming. It is designed for managin data held in relational database management systems. 
