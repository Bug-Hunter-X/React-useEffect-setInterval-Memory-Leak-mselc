# React useEffect setInterval Memory Leak

This repository demonstrates a common mistake when using `setInterval` within the `useEffect` hook in React: forgetting to include a cleanup function to stop the interval when the component unmounts. This leads to a memory leak, as the interval continues to run even after the component is no longer rendered.

The `bug.js` file contains the buggy code. The `bugSolution.js` file shows the corrected version with the cleanup function.

## Bug

The bug lies in the `useEffect` hook. The `setInterval` is started but never stopped, resulting in a memory leak.

## Solution

The solution involves using the return value of `useEffect` to implement a cleanup function. This function will clear the interval when the component unmounts or when the dependencies of the `useEffect` hook change.