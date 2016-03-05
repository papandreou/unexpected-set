Asserts that a Set instance has at least one element satisfying each given
spec.

```js
expect(new Set([1, 2, 3]), 'to satisfy', [
    1,
    expect.it('to be less than or equal to', 1),
    expect.it('to be greater than', 10)
]);
```

```output
expected Set([ 1, 2, 3 ]) to satisfy
[
  1,
  expect.it('to be less than or equal to', 1),
  expect.it('to be greater than', 10)
]

Set([
  1,
  2,
  3
  // missing: should be greater than 10
])
```

If the subject should not contain additional elements, use the `exhaustively`
flag:

```js
expect(new Set([1, 2]), 'to exhaustively satisfy', [2]);
```

```output
expected Set([ 1, 2 ]) to exhaustively satisfy [ 2 ]

Set([
  1, // should be removed
  2
])
```