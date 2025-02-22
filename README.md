# React 19 useEffect Infinite Loop Bug

This repository demonstrates a common error in React 19 involving the `useEffect` hook leading to an infinite loop. The issue arises when the effect causes a state change that, in turn, triggers another render, creating a continuous cycle.

## Problem

The provided `MyComponent` uses `useEffect` without a dependency array. This means the effect runs after every render, logging the current count to the console.  The `onClick` handler increments the count, causing a re-render. This re-render triggers the effect again, and the cycle repeats indefinitely, causing performance issues and filling the console.

## Solution

The solution involves adding a dependency array to the `useEffect` hook.  The dependency array lists the values the effect depends on.  If those values don't change between renders, the effect won't run again.

## How to reproduce

1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe the infinite loop in your browser's console.