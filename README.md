# React 18 useEffect Infinite Loop Bug

This repository demonstrates a subtle bug that can occur in React 18 and later versions when using `setInterval` within a `useEffect` hook.  The bug arises from improper handling of state updates within the timer callback.

## Bug Description
The `bug.js` file contains a component that uses `setInterval` to increment a state variable every second.  The problem is that accessing the state within the `setInterval` callback triggers an infinite re-rendering loop, causing React to become unresponsive.

## Solution
The solution, provided in `bugSolution.js`, addresses the issue by using a functional update within `setCount`. This ensures that React efficiently updates the state without triggering the continuous re-renders. 

## How to Reproduce
1. Clone this repository.
2. Run `npm install` to install the necessary dependencies.
3. Run `npm start` to start the development server.
4. Observe the infinite loop in the console in `bug.js` and corrected behavior in `bugSolution.js`.

## Key Learning
Be cautious when using state updates within `setInterval` callbacks inside `useEffect` hooks. Functional updates provide a safer and more efficient approach to managing state in such scenarios. 