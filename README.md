# React useEffect Missing Return Value

This example demonstrates a common error in React's `useEffect` hook: forgetting to include a return statement for cleanup.  When a component unmounts, the `useEffect` cleanup function is called to prevent memory leaks or other issues.  If it's missing, the effect continues to run even after the component is gone.

The `bug.js` file contains the buggy code, while `bugSolution.js` provides a corrected version.

**Problem:** The fetch in the `useEffect` hook lacks a cleanup function. This means that even after the component unmounts, the fetch operation might continue to run.

**Solution:** Add a return statement within the `useEffect` to include a cleanup function which cancels the fetch (or any asynchronous operation) before unmounting to prevent potential memory leaks and race conditions.