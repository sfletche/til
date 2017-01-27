Recently, I learned about the [lodash flow](https://lodash.com/docs/4.17.4#flow) from a [blog post](http://www.scottmessinger.com/2015/05/19/functional-programming-with-lodash/).

`_.flow` allows you to transorm something like this

```
function validateFilter(filter, acceptableOperators){  
  const validatedBlanks = validateBlanks(filter)
  const validatedValues = validateValues(validatedBlanks)
  const validatedOperators = validateOperators(validatedValues)
  const validatedLogicalOperators = validateLogicalOperators(validatedLogicalOperators)
  return validatedLogicalOperators;
}
```

into something like this

```
function validateFilter(filter){  
  return _.flow(
    validateBlanks,
    validateValues,
    validateOperators,
    validateLogicalOperators,
  )(filter)
}
```
