# RelayQuery*

* RelayQuery*
  * ES2016 classes
  * Immutable wrapper for concrete GraphQL nodes
  * Contains methods for cloning, traversing, querying metadata

* RelayQuery
  * `Node`
    * `Root`
    * `Field`
    * `Fragment`
    * `Operation`
      * `Subscription`
      * `Mutation`

```js
class RelayQueryVisitor<Ts> {
  visit(node: RelayQuery.Node, nextState: Ts): ?RelayQuery.Node {}

  traverse<Tn: RelayQuery.Node>(node: Tn, nextState: Ts): ?Tn {}

  visitField(node: RelayQuery.Field, nextState: Ts): ?RelayQuery.Node {}

  visitFragment(node: RelayQuery.Fragment, nextState: Ts): ?RelayQuery.Node {}

  visitRoot(node: RelayQuery.Root, nextState: Ts): ?RelayQuery.Node {}
}

class RelayQueryTransform<Ts> extends RelayQueryVisitor<Ts> {
  traverse<Tn: RelayQuery.Node>(node: Tn, nextState: Ts): ?Tn {}
}
```
