**Components can return `null` or `false` (but they can not return `undefined`)**

Ok, so after looking this up for the second time I figured should write it down...

Regularly, I write code to conditionally return a JSX node

```
function render(foo) {
  return (
    <div>
      {foo && <MyNode />}
    </div>
  }
}
```
If `foo` is false, the resulting `false` will result in an empty `div`

Alternatively, I could have had rendered `undefined` within the `div` for the same result

```
function getMyNode(foo) {
  if (foo) { return <MyNode />; }
}

function render(foo) {
  return (
    <div>
      {getMyNode(foo)}
    </div>
  }
}
```

What I sometimes forget is that a component can NOT render `undefined`

For example the following DOES NOT WORK

```
function render(foo) {
  if (foo) { return <MyNode />; }
}
```

That said, components CAN return either `null` or `false`

For example, returning `false` DOES WORK

```
function render(foo) {
  return foo && <MyNode />;
}
```

As does the following

```
function render(foo) {
  if (foo) { return <MyNode />; }
  return null;
}
```
