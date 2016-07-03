# Into

## What is Relay really about?

> Data-fetching framework for React applications
> Data-fetching for React applications
> Data-management for React applications
> Data-management for hierarchical component-based view applications

Relay is mapping hierarchical data to hierarchical UI.

### GraphQL

* Graph based query language
* Response keys are isomorphic to query keys

```graphql
query {
  user(id: "VXNlcjox") {
    name
    avatar(width: 100) {
      url
    }
    posts {
      title
    }
  }
}
```

```json
{
  "user": {
    "name": "Viacheslav",
    "avatar": {
      "url": "http://avatar/vslinko.png"
    },
    "posts": [
      {
        "title": "Relay Internals"
      }
    ]
  }
}
```

### React

* Component based view library
* Components are reusable
* Components are hierarchical

```js
class Form {
  render() {
    return (
      <form onSubmit={() => this.handleSubmit()}>
        <input
          value={this.state.username}
          onChange={(event) => this.setState({username: event.target.value})}
        />
        <button type="submit">Submit</button>
      </form>
    )
  }
}
```

### So...

* React is declarative UI
* GraphQL to declaratively describe what data you want
* Relay is a glue between React and GraphQL

## What we will cover?

* View Layer Integration
  * Containers
  * Babel Plugin
  * GraphQL AST (Concrete Nodes)
  * Traversal API
* Data Fetching Pipeline
* Caching Mechanism
