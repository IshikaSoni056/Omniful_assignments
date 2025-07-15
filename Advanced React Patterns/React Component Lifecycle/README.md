Lifecycle of Components
Each component in React has a lifecycle which you can monitor and manipulate during its three main phases.

The three phases are: Mounting, Updating, and Unmounting.

1. Mounting

  Mounting means putting elements into the DOM.

  React has four built-in methods that gets called, in this order, when mounting a component:

  1. constructor() - The constructor() method is called before anything else, when the component is initiated, The constructor() method is called with the props, as arguments, and you should always start by calling the super(props) before anything else
  2. getDerivedStateFromProps() - Sync state with props.
  3. render() - Render JSX to the DOM. (Required)
  4. componentDidMount() - when component render for the first time, Run side effects like API calls, event listeners.

2. Updating Phase 

    This phase occurs when:
      Props change
      State changes
      forceUpdate() is called

    React has five built-in methods that gets called, in this order, when a component is updated:

    1. getDerivedStateFromProps() - Sync state with props.
    2. shouldComponentUpdate() - Return true or false to control re-render.
    3. render() - Re-render the component.
    4. getSnapshotBeforeUpdate() - Capture info (e.g. scroll position) before DOM updates. The default value is true.
    5. componentDidUpdate() - Use updated DOM, run post-update logic.

      The render() method is required and will always be called, the others are optional and will be called if you define them.

      If the getSnapshotBeforeUpdate() method is present, you should also include the componentDidUpdate() method, otherwise you will get an error.

3. Unmounting
   
   The next phase in the lifecycle is when a component is removed from the DOM, or unmounting as React likes to call it.

   componentWillUnmount() - Cleanup (e.g., remove event listeners, cancel API calls)


Functional Component Lifecycle with Hooks

    In functional components, lifecycle is handled using hooks:

    Lifecycle	Hook Equivalent
    componentDidMount	useEffect(() => {}, [])
    componentDidUpdate	useEffect(() => {...}, [deps])
    componentWillUnmount	useEffect(() => { return () => {...}; }, [])

