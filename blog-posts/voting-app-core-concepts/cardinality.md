# Understand cardinality in database relationships (1 to 1, 1 to many, many to many)

Cardinality is how many references a collection has to another collection. There are different type of collection relationships. Common ones are one-to-one, one-to-many or many-to-many. Using a blog application as an example, each `post` will have a `title` which would represents a one-to-one relationship. Each `author` will have many `posts` which would represent a one-to-many relationship. And `posts` will have many `tags`which represents a many-to-many relationship.

There are different ways to portray these relationships in mongodb. Lets look at a voting app application example.
We have 2 collections. A collection of `users` and a collection of `polls`. Each collection will have a list of documents. In this example we will look at a 1 to many relationship. This means that every `user` can reference many `polls`. There are two ways that this can be done in mongo. The `user` document could have an array called `polls` and inside that array there will be a list of `objectId's`. Those `objectId`'s will reference an individual poll that belongs to another collection.

The second way to portray a 1 to many relationship in mongo is instead of having an array of `objectId`'s, the `user` document will embed the entire poll object data inside the `polls` array. So know you have an array of objects that contains the data for a `poll`.




