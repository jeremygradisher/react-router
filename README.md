# React-router Introduction

## Creating a multi-page React application with Navigation

$ npm install
$ npm install --save react-router-dom@6

video 1: https://youtu.be/mSplGHfTkOE

video 2: https://youtu.be/G26nO0QrEMc

video 3: https://youtu.be/KGJi3z3jHAo - Providing A Router
Task 1
To add routing to your application, in App.js, import RouterProvider and replace REPLACE ME WITH A ROUTER PROVIDER with a RouterProvider.

Task 2
Assign the RouterProvider> component a router prop. Its value should be the previously defined router constant. Don’t worry about seeing a blank page if you run npm start. We’ll fix this in the next exercise when we configure our router.

video 4: https://www.youtube.com/watch?v=_2yG8J3S33U - Creating Routes - Basic Routing with Route
Task 1
Navigate to App.js where we will begin adding routes to our router. First, add createBrowserRouter, createRoutesFromElements and Route to the import statement.

Task 2
Next, let’s render the main routes of the application. As you can see, at the top of App.js a number of components are being imported but not used. For now, we’ll render the About, SignUp, Articles, Categories, and Profile components.

Using createBrowserRouter, createRoutesFromElements, and Route, let’s define our routes between the opening and closing tags of the Root route (we’ll understand what exactly we’re doing here when we talk about nested routes) for the following components to their respective paths:

About: /about
SignUp: /sign-up
Articles: /articles
Categories: /categories
Profile: /profile








## What is React Router?
React Router is a library that provides navigational components for React developers to create Single-Page Applications (SPAs) with dynamic, client-side routing.

Applications that use React-Router can benefit from the separation of content afforded to multi-page applications without the break in the user-experience caused by page reloads.

## React <RouterProvider>
React Router can be provided to the entire application using the RouterProvider component (from react-router-dom) and including a router attribute. In the given example React Router is provided to the entire application using a RouterProvider component in the main App component.


