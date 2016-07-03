# Babel Integration

```js
Relay.QL`
  fragment on User {
    name
    ${SomeContainer.getFragment('user')}
  }
`
```

```js
fragments: {
  user: function user() {
    return function (RQL_0) {
      return {
        children: [].concat.apply([], [{
          fieldName: 'id',
          kind: 'Field',
          metadata: {
            isGenerated: true,
            isRequisite: true
          },
          type: 'ID'
        }, {
          fieldName: 'name',
          kind: 'Field',
          metadata: {},
          type: 'String'
        }, Relay.QL.__frag(RQL_0)]),
        id: Relay.QL.__id(),
        kind: 'Fragment',
        metadata: {},
        name: 'Index_UserRelayQL',
        type: 'User'
      };
    }(SomeContainer.getFragment('user'));
  }
}
```

<!--
  * POJO
  * Concrete Nodes
  * Metadata from schema
    * singular/plural
    * connection
    * type
    * extra fields
  * id field example
    * isGenerated
    * isRequisite
    * do not pass extra fields to components
-->
