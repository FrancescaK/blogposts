# NeDB: a lightweight Javascript database using MongoDB's API

Sometimes you need database functionality but want to avoid the constraints that come with installing a full-blown solution. Maybe you're writing a desktop application with Node Webkit, and don't want to have your users install MongoDB. Maybe you are writing a Node service or web application that needs to be easily packageable. Or maybe you just want to build a prototype quickly. That's when you need <a href="https://github.com/louischatriot/nedb">NeDB</a>.

NeDB is a lightweight database written entirely in Javascript, and that implements the well-known and loved MongoDB API. It is packaged as a Node module that be used with a simple `require`. You can use it as an in-memory only or persistent datastore.


[IMAGE ON JEFF ATWOOD'S LAW HERE]  


#### Features
NeDB implements the most widely used features of MongoDB:  
* CRUD operations including upserts
* Ability to persist data
* Expressive query language where you can use dot notation (to query on nested documents), regular expressions, comparison operators ($lt, $lte, $gt, $gte, $in, $nin, $exists) and logical operators ($and, $or, $not)
* Documents modifiers $set, $inc, $push, $pop, $addToSet and $each


[CODE SAMPLE HERE]


#### Performance
Of course, NeDB is not a replacement for MongoDB, so it's goal is not to be as fast as possible, it is to be fast enough. And it is: using indexing, it achieves about 5,000 writes and 25,000 reads per second.


#### Want to try it?
You can `npm install` it, the module name is `nedb`. You can also check the <a href="https://github.com/louischatriot/nedb">Github repository</a> to give feedback, raise issues or send pull requests



