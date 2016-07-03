# View Layer Integrations

* Containers
  * Configuration for data fetching
  * Contains Relay logic
  * Higher-Order Component
  * All components are wrapped

```js
function UserView(props) {
  return (
    <div>
      <AvatarContainer avatar={props.user.avatar} />
      {props.user.name}
    </div>
  )
}

const UserContainer = Relay.createContainer({
  fragments: {
    user: () => Relay.QL`
      fragment on User {
        name
        avatar {
          ${AvatarContainer.getFragment('avatar')}
        }
      }
    `
  }
})
```

* Small pieces of GraphQL (called fragments) colocated with React components
* Is collocation coupling? <!-- Not all coupling is bad. -->
  * No overfetching
  * No underfetching
  * Reusing without thinking

* Query aggregation

```graphql
query {
  user(id: "VXNlcjox") {
    ...UserContainer
  }
}

fragment UserContainer on User {
  name
  avatar {
    ...AvatarContainer
  }
}

fragment AvatarContainer on Avatar {
  url
}
```
