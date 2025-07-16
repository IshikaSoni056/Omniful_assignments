<!-- Render props pattern -->
The Render Props pattern is a technique in React for sharing code between components using a prop whose value is a function. This function then returns a React element. The "render prop" itself is not necessarily named render; it can be any prop that holds a function that returns JSX.

<!-- A render prop is a function prop that a component uses to know what to render. -->

The Render Props pattern is a technique for sharing code/logic between React components using a function as a child.


Common Examples and Use Cases

<!-- Mouse Position Tracker: -->

<!-- class MouseTracker extends React.Component {
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
        {/* The render prop will receive the mouse coordinates */}
        {this.props.render(this.state)}
      </div>
    );
  }
} -->

<!-- // Usage:
const App = () => (
  <MouseTracker render={({ x, y }) => (
    <h1>The mouse position is ({x}, {y})</h1>
  )} />
); -->