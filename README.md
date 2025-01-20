# React useEffect Hook: Memory Leak in setInterval

This repository demonstrates a common mistake when using the `setInterval` function within a React `useEffect` hook: forgetting to clear the interval when the component unmounts. This leads to memory leaks and potentially unexpected behavior.

## Bug Description
The `bug.js` file contains a component that uses `setInterval` to update a counter every second. However, it omits the crucial cleanup function to stop the interval when the component is unmounted.  This means the interval continues to run even after the component is removed from the DOM, leading to a memory leak.

## Solution
The `bugSolution.js` file corrects this issue by adding a cleanup function to the `useEffect` hook. This cleanup function uses `clearInterval` to stop the interval before the component unmounts, preventing the memory leak.

## How to reproduce the bug
1. Clone the repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the console. When you navigate away from the component or refresh the page, the `setInterval` will still run in the background.