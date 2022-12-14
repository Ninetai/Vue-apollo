# Reactive Subscription

Each subscription declared in the `apollo.$subscribe` option in a component results in the creation of a reactive subscription object.

## Options

- `query`: GraphQL document (can be a file or a `gql` string).
- `variables`: Object or reactive function that returns an object. Each key will be mapped with a `'$'` in the GraphQL document, for example `foo` will become `$foo`.
- `throttle`: throttle variables updates (in ms).
- `debounce`: debounce variables updates (in ms).
- `result(data, key)` is a hook called when a result is received
- `error(error)` is a hook called when there are errors. `error` is an Apollo error object with either a `graphQLErrors` property or a `networkError` property.
- `skip` is a boolean or a (reactive) function that returns a boolean. The function gets the current component and reactive query key as arguments, so it can be used in `$query` and in `ApolloProvider`'s `defaultOptions`.

## Properties

### skip

You can pause or unpause with `skip`:

```js
this.$apollo.subscriptions.users.skip = true
```

## Methods

### refresh

Stops and restarts the query:

```js
this.$apollo.subscriptions.users.refresh()
```

### start

Starts the query:

```js
this.$apollo.subscriptions.users.start()
```

### stop

Stops the query:

```js
this.$apollo.subscriptions.users.stop()
```
