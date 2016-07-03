# Data Fetching Pipeline

```graphql
query {
  user(id: "VXNlcjox") {
    posts {
      title
    }
  }
}
```

1. Client (Relay) -> Server (GraphQL)
  1. RelayEnvironment.primeCache
    1. Diffing <!-- remove parts of a query that already stored -->
    2. Deffering <!-- delay some query parts, reduce initial query size -->
    3. Subtracting <!-- remove parts of a query that already requested (in-flight queries) -->
    4. Printing <!-- convert ast to graphql string -->

2. Server (GraphQL) -> Client (Relay)
  1. Write payload from the server using traversals
  2. Notify subscribers <!-- all components that listening a data -->
  3. Read query data
  4. Re-render
