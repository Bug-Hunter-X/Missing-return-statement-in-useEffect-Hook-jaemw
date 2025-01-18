# React 19 useEffect Hook Bug

This repository demonstrates a common error in React 19 applications involving the `useEffect` Hook: omitting the return statement in `useEffect` when performing cleanup operations.  This can lead to memory leaks and unexpected behavior.  The solution shows how to properly use a return statement for cleanup.

## Bug

The `bug.js` file contains a component with an `useEffect` hook that lacks a return function. This will cause issues in production environments. This is because the cleanup function that is responsible for handling the side effects, such as subscriptions or timers, is not being called, leading to memory leaks or unexpected side effects. 

## Solution

The `bugSolution.js` file demonstrates how to fix this by adding a return statement to the `useEffect` hook.  This ensures that any cleanup actions (like unsubscribing from events or clearing timers) are performed when the component unmounts or when the dependencies change.