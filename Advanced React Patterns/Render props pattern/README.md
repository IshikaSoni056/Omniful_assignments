#  Render Props Pattern in React

The **Render Props** pattern is a **technique in React** for sharing code and behavior between components using a prop whose **value is a function**. This function is called by the component and returns a React element.

>  The term "render prop" refers to a **function prop that tells a component what to render** — the prop doesn’t have to be named `render`, though that’s a common convention.

---

##  Why Use Render Props?

This pattern is especially useful when you want to:
- Share logic across multiple components
- Keep components **flexible** and **reusable**
- Avoid duplicating logic like mouse tracking, fetching data, toggling, etc.

---

## Key Concept

```js
<Component render={functionToRenderSomething} />
```
## mouseTracker
```js

import React from 'react';

class MouseTracker extends React.Component {
  state = { x: 0, y: 0 };

  handleMouseMove = (event) => {
    this.setState({
      x: event.clientX,
      y: event.clientY,
    });
  };

  render() {
    return (
      <div style={{ height: '100vh' }} onMouseMove={this.handleMouseMove}>
        {/* Pass mouse coordinates to render function */}
        {this.props.render(this.state)}
      </div>
    );
  }
}

export default MouseTracker;
