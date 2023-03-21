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





## What is React Router?
React Router is a library that provides navigational components for React developers to create Single-Page Applications (SPAs) with dynamic, client-side routing.

Applications that use React-Router can benefit from the separation of content afforded to multi-page applications without the break in the user-experience caused by page reloads.

## React <RouterProvider>
React Router can be provided to the entire application using the RouterProvider component (from react-router-dom) and including a router attribute. In the given example React Router is provided to the entire application using a RouterProvider component in the main App component.


