TIL about [`createSink`](https://github.com/acdlite/recompose/blob/master/docs/API.md#createsink) from the [`recompose`](https://github.com/acdlite/recompose) library...

Create a component to perform an action whenever prop changes

```
// DataFetcher.jsx
import { createSink } from 'recompose';
...

function mapStateToProps(state) {
  return {
    relevantState: state.relevantState,
  };
}

function onChange(): void {
  store.dispatch(someAction());
}

const fetcher = createSink(onChange);

export default connect(mapStateToProps)(fetcher);
```


Sample Usage

```
function MyComponent() {
  return (
    <React.Fragment>
      <DataFetcher />
      <DataDisplay />
    </React.Fragment>
  );
}
```
