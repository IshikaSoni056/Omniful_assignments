<!-- Higher-Order Components (HOCs) -->

a Higher-Order Component is a function that takes a component as an argument and returns a new, enhanced component.
<!-- What are HOCs? -->
Think of HOCs as similar to higher-order functions in JavaScript, which take functions as arguments or return functions. In React, HOCs operate on components.

<!-- const EnhancedComponent = withSomething(OriginalComponent); -->

  <!-- function withLogger(WrappedComponent) {
    return function EnhancedComponent(props) {
      console.log('Rendering', WrappedComponent.name);
      return <WrappedComponent {...props} />;
    };
  } -->

<!-- Common Use Cases for HOCs: -->

Authentication wrappers (e.g., withAuth) - withAuth(MyComponent) to ensure a user is logged in before rendering

Permission checks

Adding tracking/logging

Code reuse (e.g., data fetching)

Enhancing components with additional props

