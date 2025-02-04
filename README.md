# Unexpected Re-renders in React's useEffect Hook

This repository demonstrates a common issue in React applications involving the `useEffect` hook.  The problem arises from an incomplete dependency array, leading to unintended re-renders and potential performance issues.

## Problem

The provided `MyComponent` uses `useEffect` to log the current count. However, because the dependency array is incomplete, the effect runs after every render, even when the count hasn't changed, resulting in unnecessary console logs.

## Solution

To resolve the issue, ensure that the dependency array (`[count]`) correctly includes all variables from the component's scope that the effect depends on. If an effect doesn't need any variables from scope, pass an empty array `[]` to only run it once after the initial render.