# React useEffect Hook causing unnecessary re-renders

This example demonstrates an inefficient use of the React `useEffect` hook.  The effect runs after every render, causing performance issues and unnecessary re-renders.

## Problem

The provided `MyComponent` uses `useEffect` without a dependency array. This means the effect runs after every render, regardless of changes to component's state.  This can lead to unnecessary logging, API calls, and other potentially expensive operations, especially in complex apps.

## Solution

The solution is to add a dependency array to `useEffect`. In this case, the effect only needs to run when the `count` state changes.  By including `[count]` as the second argument to `useEffect`, the effect runs only when `count` updates.

## How to reproduce

1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe the console log and the component's behavior.  Notice how frequently the log message appears.
5. After applying the fix, the log message appears only when the button is clicked.
