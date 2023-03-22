# React-router Introduction

## Creating a multi-page React application with Navigation

$ npm install

$ npm install --save react-router-dom@6

## video 1: https://youtu.be/mSplGHfTkOE

## video 2: https://youtu.be/G26nO0QrEMc

## video 3: https://youtu.be/KGJi3z3jHAo - Providing A Router
Task 1
To add routing to your application, in App.js, import RouterProvider and replace REPLACE ME WITH A ROUTER PROVIDER with a RouterProvider.

Task 2
Assign the RouterProvider> component a router prop. Its value should be the previously defined router constant. Don’t worry about seeing a blank page if you run npm start. We’ll fix this in the next exercise when we configure our router.

## video 4: https://www.youtube.com/watch?v=_2yG8J3S33U - Creating Routes - Basic Routing with Route
Task 1
Navigate to App.js where we will begin adding routes to our router. First, add createBrowserRouter, createRoutesFromElements and Route to the import statement.

Task 2
Next, let’s render the main routes of the application. As you can see, at the top of App.js a number of components are being imported but not used. For now, we’ll render the About, SignUp, Articles, Categories, and Profile components.

Using createBrowserRouter, createRoutesFromElements, and Route, let’s define our routes between the opening and closing tags of the Root route (we’ll understand what exactly we’re doing here when we talk about nested routes) for the following components to their respective paths:
```
About: /about
SignUp: /sign-up
Articles: /articles
Categories: /categories
Profile: /profile
```

## video 5: https://youtu.be/wt4JTW2gVdg - Linking to Routes

In the last exercise, you used the URL bar to navigate to a path that matched one of your application’s routes. But how do you navigate from within the app itself?

When building a website using HTML, we use the anchor ((anchor tag)) tag to create links to other pages. A side effect of the anchor tag is that it causes the page to reload. This can distract our users from the immersive experience of our smooth React application!

Task 1
Head over to Articles.js located in the src/components/. This component renders a list of (anchor tag) links for each value in the filteredArticles array. If you try clicking on these links in the running application, you’ll notice a very subtle page reload (pay attention to the “refresh” button in your browser)!

Import the Link component into this file and then replace the (anchor tag) tags to eliminate the page reload!

Note: The articles themselves won’t appear yet. We’ll fix that soon!

Hint
Task 2
In the running application, try clicking on the links rendered by the Header, such as “Articles”. Again, you may notice a page refresh.

Open up the Header.js file and you’ll see that these links are rendered using plain old (anchor tag) tags!

First, import the NavLink component into the Header.js file. Then, inside the return statement of the Header component, replace each instance of the (anchor tag) tag with a NavLink component.

Make sure to replace the href attribute with the to prop!

Hint
Task 3
To verify your work, try clicking on the navigation links. You should notice that the page no longer refreshes! Furthermore, you’ll notice the link you clicked on will be bolded!


## video 6: https://youtu.be/N8i8uW4mxPE - Dynamic Routes:

URL parameters are dynamic segments of a URL that act as placeholders for more specific resources. They appear in a dynamic route as a colon (:) followed by a variable name, like so:
```
const route = createBrowserRouter(createRoutesFromElement(
  <Route path='/articles/:title' element={ <Article /> }/>
))
```

## Let’s break down this short, yet powerful demonstration of URL parameters:

In this example, the path prop 'articles/:title' contains the URL parameter :title.

This means that when the user navigates to pages such as '/articles/what-is-react' or '/articles/html-and-css', the Article /> component will render.

When the Article component is rendered in this way, it can access the actual value of that :title URL parameter (what-is-react or html-and-css) to determine which article to display (more on this in the next exercise). A single route can even have multiple parameters (eg. 'articles/:title/comments/:commentId') or none (eg. 'articles').

Let’s take advantage of dynamic routes by using URL parameters in our application.

# LEARN REACT ROUTER V6
## useParams - video 7: https://youtu.be/oQHNGEwXr44

It is common to use the value of URL parameters to determine what is displayed in the component that a dynamic route renders. For example, the Article component might need to display the title of the current article.

React Router provides a hook, useParams(), for accessing the value of URL parameters. When called, useParams() returns an object that maps the names of URL Parameters to their values in the current URL.

# 2022 Audit Nested Routes
## video 8: https://youtu.be/84nxDr4_iMo
Up to this point, we’ve been working with routers that are relatively small. As our application grows and we add more features, we may want additional components to render within our defined views depending on user actions.


# Navigate
## video 9: 
If you take anything away from this lesson, it should be that React Router treats everything as a component. To get fully comfortable using React Router in your code, you have to embrace this idea and the declarative coding style that follows from it. For the most part, this is pretty intuitive, but it can feel a bit counterintuitive when it comes to redirecting users.

To appreciate the declarative pattern, consider a common case for redirecting a user: a user wants to access a /profile page that requires authentication but is not currently signed in.

```
import React from "react";
import { useSelector } from "react-redux";
import { Link, Outlet, Navigate } from "react-router-dom";
import { selectCurrentUser, selectIsLoggedIn } from "../features/session/sessionSlice";

export default function Profile () {
  const currentUser = useSelector(selectCurrentUser)
  const loggedIn = useSelector(selectIsLoggedIn);
  
  // use loggedIn to return a Navigate
  if (!loggedIn) {
    return <Navigate to="/sign-up"/>
  }

  return (
    <main>
      <h1>{currentUser.username}</h1>
      <Link to={`edit`}>Edit</Link>
      <Outlet/>
    </main>
  )
}
```

# useNavigate
## video 10: https://youtu.be/cTs9m2W9eoE

In the previous exercise, you learned how to redirect declaratively by rendering a Navigate component that updates the browser’s current location. Though this approach follows React Router’s declarative coding style, it does introduce a few extra steps in the React rendering lifecycle:

The Navigate component must be returned.
The Navigate component is then rendered.
The URL is updated.
And finally the appropriate route is rendered.
React Router also provides a mechanism for updating the browser’s location imperatively using the useNavigate hook.

import { useNavigate } from 'react-router-dom';
The useNavigate() function returns a navigate function that allows us to specify a path where we’d like to navigate.

# Query Parameters
## video 11: https://youtu.be/8AKdEh96mBQ

Query parameters appear in URLs beginning with a question mark (?) and are followed by a parameter name assigned to a value. They are optional and are most often used to search, sort and/or filter resources.

For example, if you were to visit the URL below…
```
https://www.google.com/search?q=codecademy
```
… you would be taken to Google’s /search page displaying results for the search term codecademy. In this example, the name of the query parameter is q.

# Review: https://youtu.be/H9NYBb6hhuM

Great work! You’ve learned everything you need to know to add front-end routing to your React applications using React Router! To recap, you’ve learned how to:

Install react-router-dom and add it to a React application.
Enable routing by using RouterProvider and providing a router.
Creating a router using createBrowserRouter().
Use createRoutesFromElements() to configure a router.
Use the Route component to add static and dynamic routes to an application.
Use Link and NavLink components to add links to an application.
Access the values of URL parameters using React Router’s useParams hook.
Create nested routes using Route, Outlet, and relative paths.
Declaratively redirect users by rendering React Router’s Navigate component
Imperatively redirect users via the useNavigate hook.
Access and set the value of query parameters using React Router’s useSearchParams hook.



## What is React Router?
React Router is a library that provides navigational components for React developers to create Single-Page Applications (SPAs) with dynamic, client-side routing.

Applications that use React-Router can benefit from the separation of content afforded to multi-page applications without the break in the user-experience caused by page reloads.

## React <RouterProvider>
React Router can be provided to the entire application using the RouterProvider component (from react-router-dom) and including a router attribute. In the given example React Router is provided to the entire application using a RouterProvider component in the main App component.


