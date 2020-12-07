# React Router

## React Router

**client-side routing**: navigating between views without leaving the React app

## Versions and Installation

React router 6 beta is available since June 2020, but development has been slow since then

packages for react router 6 (include TypeScript support):

- _react-router-dom@next_
- _history_

packages for react router 5:

- _react-router-dom_
- _@types/react-router-dom_

## Setup

the entire application is enclosed in a `BrowserRouter` element:

```js
// index.js

import { BrowserRouter } from 'react-router-dom';

ReactDOM.render(
  <React.StrictMode>
    <BrowserRouter>
      <App />
    </BrowserRouter>
  </React.StrictMode>,
  rootElement
);
```

## Basic router components (v6)

- `<Route>` - a component that renders its content when active
- `<Routes>` - a container for `<Route>` elements
- `<Link>` / `<NavLink>` - are used in place of `<a>` elements

## Basic example (v6)

```js
const App = () => {
  return (
    <div>
      <NavLink to="/slideshow">slideshow</NavLink>{' '}
      <NavLink to="/counter">counter</NavLink>
      <Routes>
        <Route path="/slideshow" element={<Slideshow />} />
        <Route path="/counter" element={<Counter />} />
      </Routes>
    </div>
  );
};
```

## Advanced routing (v6)

```jsx
const App = () => {
  return (
    <Routes>
      <Route path="/posts" element={<PostPage />}>
        <Route path="/:postId" element={<Post />} />
      </Route>
      <Route path="/shop" element={<ShopPage />}>
        <Route path="/" element={<ShopIndex />} />
        <Route path="/product/:id" element={<Product />} />
        <Route path="/cart" element={<Cart />} />
      </Route>
    </Routes>
  );
};
```

## Basic example (v5)

In v5 we use the `<Switch>` component instead of `<Routes>`

```js
const App = () => {
  return (
    <div>
      <NavLink to="/slideshow">slideshow</NavLink>{' '}
      <NavLink to="/counter">counter</NavLink>
      <Switch>
        <Route path="/slideshow">
          <Slideshow />
        </Route>
        <Route path="/counter">
          <Counter />
        </Route>
      </Switch>
    </div>
  );
};
```

## Route parameters

```jsx
<Route path="/todos/:todoId">
  <TodoDetailView />
</Route>
```

```jsx
import { useParams } from 'react-router-dom';

const TodoDetailView = () => {
  const routeParams = useParams();
  return (
    <div>
      Details of todo: {routeParams.todoId}
      <div>...</div>
    </div>
  );
};
```

## Styling links

supplying a class name that will be applied to any active link:

```xml
<NavLink to="/" activeClassName="active-link">Home</NavLink>
<NavLink to="/add" activeClassName="active-link">Add</NavLink>
```

## Navigation from React

in v6:

```jsx
const navigate = useNavigate();
// ...
navigate('/');
```

in v5:

```js
const history = useHistory();
// ...
history.push('/');
```

## Navigation from React

example:

```jsx
const AddTodoView = () => {
  const navigate = useNavigate();
  const handleSubmit = (event) => {
    event.preventDefault();
    // ...
    navigate('/');
  };
  // ...
};
```
