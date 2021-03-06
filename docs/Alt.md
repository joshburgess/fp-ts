---
id: Alt
title: Alt
---

[Source](https://github.com/gcanti/fp-ts/blob/master/src/Alt.ts)

# Alt

**Signature** (type class) [Source](https://github.com/gcanti/fp-ts/blob/master/src/Alt.ts#L17-L19)

```ts
export interface Alt<F> extends Functor<F> {
  readonly alt: <A>(fx: HKT<F, A>, fy: HKT<F, A>) => HKT<F, A>
}
```

The `Alt` type class identifies an associative operation on a type constructor. It is similar to [Semigroup](./Semigroup.md), except
that it applies to types of kind `* -> *`, like [Array](./Array.md) or [Option](./Option.md), rather than concrete types like `string` or
`number`.

`Alt` instances are required to satisfy the following laws:

1. Associativity: `A.alt(A.alt(fa, ga), ha) = A.alt(fa, A.alt(ga, ha))`
2. Distributivity: `A.map(A.alt(fa, ga), ab) = A.alt(A.map(fa, ab), A.map(ga, ab))`

Added in v1.0.0
