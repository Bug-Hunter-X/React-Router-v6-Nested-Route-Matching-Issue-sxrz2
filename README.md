# React Router v6 Nested Route Matching Issue

This repository demonstrates a subtle issue with route matching in React Router v6 when dealing with nested routes.  The problem arises when a nested route path overlaps with a parent route's path, causing unexpected behavior.  The solution involves carefully managing route specificity using `element` instead of `component` and ensuring the child route path is unique.

## Bug Report

The provided `App.js` file showcases a scenario where the route `/about/contact` does not match correctly even though it's nested under `/about`. This is because React Router 6's route matching is strict, and the `/about` route essentially captures all paths starting with `/about`, including `/about/contact`. 

## Solution

The solution, found in `AppSolution.js`, involves avoiding nested routes where a child route's path is a simple extension of the parent route's path. Instead, you can choose more specific paths such as a parameter or make sure the nested route is different.