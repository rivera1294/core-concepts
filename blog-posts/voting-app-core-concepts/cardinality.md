# Understand cardinality in database relationships (1 to 1, 1 to many, many to many)

Cardinality is how many references a collection has to another collection. There are different type of collection relationships. Common ones are one-to-one, one-to-many or many-to-many. Using a blog application as an example, each `post` will have a `title` which would represents a one-to-one relationship. Each `author` will have many `posts` which would represent a one-to-many relationship. And `posts` will have many `tags`which represents a many-to-many relationship.

There are different ways to portray these relationships in mongodb. Lets look at our `author` and `posts` 1 to many relationship. In a collection of `authors`, each `author` document will have a references to their `posts` they created. These `posts` can have their own collection which the `author` document can reference or the `author` document can have an array of `posts` objects that contain all the data related to a `post`.
