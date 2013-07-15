# NeDB: a lightweight Javascript database using MongoDB's API

Sometimes you need database functionality but want to avoid the constraints that come with installing a full-blown solution. Maybe you are writing a Node service or web application that needs to be easily packageable, such as a <a href="https://github.com/louischatriot/braindead-ci" target="_blank">continuous integration server</a>. Maybe you're writing a desktop application with Node Webkit, and don't want to ask your users to install an external database. That's when you need <a href="https://github.com/louischatriot/nedb">NeDB</a>.

**NeDB is a lightweight database written entirely in Javascript**, and that implements the well-known and loved MongoDB API. It is packaged as a Node module that be used with a simple `require` and can be used as an in-memory only or persistent datastore. **You can think of it as SQLite for MongoDB projects**.

```javascript
var Nedb = require('nedb')
  , planets = new Nedb({ filename: 'path/to/data.db', autoload: true });

// Let's insert some data
planets.insert({ name: 'Earth', satellites: 1 }, function (err) {
  planets.insert({ name: 'Mars', satellites: 2 }, function (err) {
    planets.insert({ name: 'Jupiter', satellites: 67 }, function (err) {
      
      // Now we can query it the usual way
      planets.find({ satellites: { $lt: 10 } }, function (err, docs) {
        // docs is an array containing Earth and Mars
      });
    });
  });
});
```


#### Features
NeDB implements the most widely used features of MongoDB:  
* CRUD operations including upserts
* Ability to persist data
* Expressive query language where you can use dot notation (to query on nested documents), regular expressions, comparison operators ($lt, $lte, $gt, $gte, $in, $nin, $exists) and logical operators ($and, $or, $not)
* Documents modifiers $set, $inc, $push, $pop, $addToSet and $each
* A browser version


#### Performance
Of course, NeDB is not a replacement for a "real" database such as MongoDB, so its goal is not to be as fast as possible, it is to be fast enough. And it is: using indexing, it achieves about 5,000 writes and 25,000 reads per second. If you need more than this, you're probably not writing a small application!


#### Want to try it?
You can `npm install` it, the module name is `nedb`. You can also check the <a href="https://github.com/louischatriot/nedb">Github repository</a> to read the documentation, give feedback, raise issues or send pull requests



