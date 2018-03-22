---
title: Apollo Client
order: 11
description: Apollo Client API reference
---

<h2 id="apollo-client">ApolloClient</h2>

The Apollo Client constructor takes a small number of options, of which two are required. These arguments make it easy to customize how Apollo works based on your environment or application needs.

- `link`: Apollo Client requires an Apollo Link to serve as the network layer. For more information about creating links, read the [docs](/docs/link).
- `cache`: The second required argument for using Apollo Client is an instance of an Apollo Cache. The default cache is the `apollo-cache-inmemory` which exports an `{ InMemoryCache }`. For more information read the [cache docs](../advanced/caching.html).
- `ssrMode`: When using the client for [server side rendering](../recipes/server-side-rendering.html), pass `ssrMode` as `true` so that React Apollo's `getDataFromTree` can work effectively.
- `ssrForceFetchDelay`: determines the time interval before Apollo Client force fetchs queries after a server side render.
- `connectToDevTools`: This argument allows the [Apollo Client Devtools](../features/developer-tooling.html) to connect to your application's Apollo Client. You can set this to be `true` to use the tools in production (they are on by default in dev mode).
- `queryDeduplication`: If set to false, this argument will force a query to still be sent to the server even if a query with identical parameters (query, variables, operationName) is already in flight.
- `defaultOptions`: If you want to set application wide defaults for the options supplied to `watchQuery`, `query`, or `mutate`, you can pass them as a `defaultOptions` object. An example object looks like this:

```js
const defaultOptions = {
  watchQuery: {
    fetchPolicy: 'cache-and-network',
    errorPolicy: 'ignore',
  },
  query: {
    fetchPolicy: 'network-only',
    errorPolicy: 'all',
  },
  mutate: {
    errorPolicy: 'all'
  }
}
```

These options will be merged with options supplied with each request.

The `ApolloClient` class is the core API for Apollo, and the one you'll need to  use no matter which integration you are using:

{% tsapibox ApolloClient.constructor %}
{% tsapibox ApolloClient.watchQuery %}
{% tsapibox ApolloClient.query %}
{% tsapibox ApolloClient.mutate %}
{% tsapibox ApolloClient.readQuery %}
{% tsapibox ApolloClient.readFragment %}
{% tsapibox ApolloClient.writeQuery %}
{% tsapibox ApolloClient.writeFragment %}
{% tsapibox ApolloClient.resetStore %}
{% tsapibox ApolloClient.onResetStore %}

<h2 id="ObservableQuery">ObservableQuery</h2>

{% tsapibox ObservableQuery.variables %}
{% tsapibox ObservableQuery.result %}
{% tsapibox ObservableQuery.currentResult %}
{% tsapibox ObservableQuery.refetch %}
{% tsapibox ObservableQuery.setOptions %}
{% tsapibox ObservableQuery.setVariables %}
{% tsapibox ObservableQuery.fetchMore %}
{% tsapibox ObservableQuery.updateQuery %}
{% tsapibox ObservableQuery.startPolling %}
{% tsapibox ObservableQuery.stopPolling %}

<h2 id="types">Types</h2>

{% tsapibox ApolloClientOptions %}
{% tsapibox DefaultOptions %}
{% tsapibox NetworkStatus %}