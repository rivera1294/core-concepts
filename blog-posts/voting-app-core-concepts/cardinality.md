# Understand cardinality in database relationships (1 to 1, 1 to many, many to many)

Cardinality is how many references a collection has to another collection. There are different type of collection relationships. Common ones are one-to-one, one-to-many or many-to-many. Using a blog application as an example, each `post` will have a `title` which would represents a one-to-one relationship. Each `author` will have many `posts` which would represent a one-to-many relationship. And `posts` will have many `tags`which represents a many-to-many relationship.

There are different ways to portray these relationships in mongodb. Lets look at a voting app application example and portray a 1 to many relationship example. Our 1 to many relationship will be that every `user` can reference many `polls`. We have 2 collections. A collection of `users` and a collection of `polls`. Each collection will have a list of documents. A `user` document could have an array property called `polls` and inside that array there will be a list of `objectId's`. Those `objectId`'s will reference an individual poll that belongs to another collection. This is the idea of normalization. Normalization is the dividing up data into muliple collections and having references between those collections. 

Denormalization is the opposite of normalization. In this case instead of referencing different collections we will instead embed all the data into a single document. A `user` document will embed the entire poll object data inside the `polls` array. So now you have an array of objects that contains the data for a `poll`.




