Recently I learned how to validate the shape of an object PropType in React components...

Instead of the overly generic (and therefore somewhat meaningless) `object` prop type

```
user: React.PropTypes.object.isRequired
```

I can use a `shape` prop type to validate the properties on that object 

```
user: React.PropTypes.shape({
  id: React.PropTypes.string.isRequired,
  email: React.PropTypes.string.isRequired,
  phone: React.PropTypes.string,
}).isRequired
```
