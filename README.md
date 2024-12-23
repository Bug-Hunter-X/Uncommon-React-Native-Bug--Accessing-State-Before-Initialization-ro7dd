# Uncommon React Native Bug: Accessing State Before Initialization

This repository demonstrates a subtle bug in React Native that can occur when accessing state variables before they've been initialized within functional components.  The issue arises from attempting to read state values during the initial render, before the `useState` hook has assigned a value.

## Bug Description

The core problem is referencing the state variable (`count` in the example) before React has had the chance to fully mount the component and populate the state.  This results in `undefined` being accessed, potentially leading to unexpected behavior or crashes.

## How to Reproduce

1. Clone this repository.
2. Run `npm install` or `yarn install` to install dependencies.
3. Run the application using your preferred React Native method.
4. Observe that the initial display shows 'undefined' before the increment button works correctly.

## Solution

The solution involves using optional chaining or the nullish coalescing operator to handle the potential `undefined` value during the initial render.  This ensures a graceful fallback.

## Learning Points

- Understand the lifecycle of functional components in React Native, particularly how state initialization works.
- Practice defensive programming techniques to handle potential undefined values when working with state.