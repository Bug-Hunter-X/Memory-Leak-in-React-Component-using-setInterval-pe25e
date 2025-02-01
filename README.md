# React UseEffect setInterval Memory Leak

This repository demonstrates a common error in React applications involving the `useEffect` hook and `setInterval`.  The example showcases a memory leak due to improper cleanup of the interval.

## Problem

The provided `MyComponent` uses `setInterval` to update a counter every second. However, it fails to clear the interval when the component unmounts, resulting in multiple intervals running simultaneously. This leads to a memory leak and potentially unexpected behavior.

## Solution

The solution demonstrates the correct way to use `setInterval` within `useEffect`. It utilizes the return value of `setInterval` to store the interval ID, enabling the cleanup function to stop the interval when the component unmounts.

## How to reproduce

1. Clone the repository.
2. Run `npm install`.
3. Run `npm start`.

Observe the counter incrementing.  Close the browser tab. The interval continues running, indicating a memory leak (you can check via browser dev tools).

Now compare with the fix in `bugSolution.js`.