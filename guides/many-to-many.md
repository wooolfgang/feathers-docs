# Many to Many Relationships

There are a few different ways that you can do many-to-many relationships with Feathers. Let's take our [Chat Example]() from the the tutorial. It currently doesn't have many-to-many (M:N) relationships. So let's introduce the notion of `channels`. A user can belong to many channels and a channel can have many users.

## Using Sequelize

Basically using hooks to call the ORM getters.

```js
```

You can see [a complete example here]().

## Using Mongoose

Basically using `$populate`.

```js
```

You can see [a complete example here]().

## The Feathers Way

The two solutions above work great but there is one problem... **they are ORM dependent**. If you don't have an ORM that supports relationships then you are out of luck. Using a specific ORM solution makes it hard to do two things:

1. Introducing another database into your app makes it either very hard or impossible to reuse code.
2. Switching to a different database or ORM is a ton of work because you need to change a lot of code. Serious lock in. :-(

Since Feathers boasts being datastore agnostic, managing related data should also be datastore agnostic. For complex relationships and populating deeply nested objects this is where [GraphQL]() might come in. However, for a lot of apps that is overkill. You might only need to populate one level deep, not many nested levels. With Feathers you can do easily achieve this just using a few hooks.

