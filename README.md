# React 19 useEffect setInterval memory leak
This repository demonstrates a common error in React 19 applications involving the `useEffect` hook and `setInterval`.  The improper use of `setInterval` without a cleanup function leads to memory leaks.

The `bug.js` file contains the erroneous code. The `bugSolution.js` demonstrates the correct implementation.

## Problem
The original code uses `setInterval` to update a counter every second. However, it lacks a cleanup function within the `useEffect` hook. This means that when the component unmounts, the `setInterval` continues to run, causing memory leaks.

## Solution
The solution involves using the return value of `useEffect` to add a cleanup function. This cleanup function clears the interval when the component unmounts, preventing memory leaks.