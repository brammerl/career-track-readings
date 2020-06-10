# Mongoose Populate
- Population is the process of automatically replacing the specified paths in the document with documents from other collections
- You can populate a single document, multiple documents, a plain object, multiple plain objects or all objects returned from the query. 

- to save a ref - create the reference with a new _id and then assign that _id to a new object that is created. 

```
const author = new Person({
  _id: new mongoose.Types.ObjectId(),
  name: 'Ian Fleming',
  age: 50
});

author.save(function (err) {
  if (err) return handleError(err);

  const story1 = new Story({
    title: 'Casino Royale',
    author: author._id    // assign the _id from the person
  });

  story1.save(function (err) {
    if (err) return handleError(err);
    // that's it!
  });
});
```
- You can populate the information that is being referenced by calling upon the specific object that is created.

```
Story.
  findOne({ title: 'Casino Royale' }).
  populate('author').
  exec(function (err, story) {
    if (err) return handleError(err);
    console.log('The author is %s', story.author.name);
    // prints "The author is Ian Fleming"
  });
```
# Express Routing
- router is a mini express app that provides us with routing apis .use, .get, .param, and route. 
- router.use() is to define middleware. -- a way to do something before a request is processed. ie. checking if an user is authenticated, logging data for analytics etc. 
-.param() creates middleware that will run for a certain route parameter. 
- app.route is a shortcut to call the express router 
  - lets us define multiple actiosn on a single login route. 

## Conclusion
- use express.Router() multiple times to define groups of routes
- Apply the express.Router() to a section of our site using app.use()
- Use route middleware to process requests
- Use route middleware to validate parameters using .param()
- Use app.route() as a shortcut to the Router to define multiple requests on a route. 

# Mongoose Virtuals
- Using mongoose virtuals you can define more sophisticated relationships b/w documents. 
- You can use the populate match option to add additional filter to the populate() query. 
- Also supports counting the number of documents with matching foreignField as opposed to the documents themselves. 

```
const PersonSchema = new Schema({
  name: String,
  band: String
});

const BandSchema = new Schema({
  name: String
});
BandSchema.virtual('members', {
  ref: 'Person', // The model to use
  localField: 'name', // Find people where `localField`
  foreignField: 'band', // is equal to `foreignField`
  // If `justOne` is true, 'members' will be a single doc as opposed to
  // an array. `justOne` is false by default.
  justOne: false,
  options: { sort: { name: -1 }, limit: 5 } // Query options, see http://bit.ly/mongoose-query-options
});

const Person = mongoose.model('Person', PersonSchema);
const Band = mongoose.model('Band', BandSchema);

/**
 * Suppose you have 2 bands: "Guns N' Roses" and "Motley Crue"
 * And 4 people: "Axl Rose" and "Slash" with "Guns N' Roses", and
 * "Vince Neil" and "Nikki Sixx" with "Motley Crue"
 */
Band.find({}).populate('members').exec(function(error, bands) {
  /* `bands.members` is now an array of instances of `Person` */
});
```