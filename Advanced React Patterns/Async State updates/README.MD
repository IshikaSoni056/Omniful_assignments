<!-- Async State Updates in React -->
  In React, especially when using useState or this.setState, state updates are asynchronous. This means the state value doesn't change immediately after you request an update.

<!-- Why are state updates asynchronous? -->
 Instead of updating the DOM every time state changes, it schedules the updates and processes them together, improving efficiency.

 code: 
   <!-- this.setState({ count: this.state.count + 1 });
    console.log(this.state.count);  Still shows the old value -->


 Correct Way - use callback in setState:
    <!-- this.setState((prevState) => ({
    count: prevState.count + 1,
  <!-- })); --> 

Multiple State Updates in One Go 

<!-- setCount(count + 1);
setCount(count + 1); -->

You might think this gives +2, but it gives only +1 because both use the same count.

 Correct Way:

<!-- setCount((prev) => prev + 1);
setCount((prev) => prev + 1); // ✅ Adds 2 correctly -->

(Functional Component with useState)

<!-- const [count, setCount] = useState(0);

const increment = () => {
  setCount(count + 1);
  console.log(count); //  Still old value
}; -->

Correct Way (log after update using useEffect):

<!-- useEffect(() => {
  console.log(count); //  Logs updated value
}, [count]);

const increment = () => {
  setCount((prevCount) => prevCount + 1);
}; -->