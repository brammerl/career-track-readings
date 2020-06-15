## Instance methods
- Mongoose instance methods: instances of models are documents. Documents have many of their own built-in instance methods. 
- When you create a new instance, you can utilize the functions that are created as instance methods within the schema. 

## Static Methods 
- You can add a function property to schema.statics
- Call the Schema#static() function 

## Middleware 
- Mongoose has 4 types of middleware: 
  - document: validate, save, remove, updateOne, deleteOne
  - model: insertMany
  - aggregate: executes when you call exec() on an aggregate object. 
  - query: count, deleteMany, deleteOne, find, findOne etc. 