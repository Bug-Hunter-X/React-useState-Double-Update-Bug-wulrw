# React useState Double Update Bug

This repository demonstrates a subtle bug related to how React's `useState` hook handles multiple updates within a single render cycle.  The bug highlights the asynchronous nature of state updates.

## Bug Description
The `bug.js` file contains a component where the `setCount` function is called twice in quick succession within the `handleClick` function.  While it might seem like the count should increment by 2, only one of these updates will be reflected in the UI.  This is because React batches state updates for performance optimization and discards intermediate updates.

## Solution
The `bugSolution.js` file demonstrates a solution using functional updates to ensure the correct increment is always applied. This uses the previous value to calculate the new state, eliminating race condition issues.

## How to reproduce
Clone the repo and run `npm install`.  Then, run `npm start` to view the buggy and fixed components.
