# LEARNING OF THE UDEMY COURSE

### [CodeSandBox Link for all code ](https://codesandbox.io/dashboard/sandboxes/Nextjs%20Maxmilian%20Udemy%20Course?workspace=ws_TQRVDyHzkH3sxpUFbHgQN1)
--- 
###  [Currently at](https://www.udemy.com/course/nextjs-react-the-complete-guide/learn/lecture/43340620#learning-tools)
---
## 91 Working with Pages and Layout
 - Page.js is for the content of the page
 - Layout.js works as the shell around one or more than one page. Need at least one layout at root folder. Can also be in each folder.

## 92. Reserved File Names, Custom Components & How To Organize A NextJS Project

- If you add `icon.png` in the root app folder, it will be used as the favicon.

## 94 Configuring Dynamic Routes and Using Route parameters

- Dynamic routes are created by adding `[]` in the file name. For example, `pages/blog/[slug].js` will create a dynamic route for `/blog/post-1 `.
- To access the slug in the page defined in slug folder. Nextjs automatically passes the params.

```
const MealDetailsPage = ({ params }) => {
  console.log(params);
  return <div>MealDetailsPage={params.mealSlug}</div>;
};
export default MealDetailsPage;
```

## 101 Optimizing the image with Next Image 


```
import Image from 'next/image'
import logoImg from '../public/logo.png'
<Image src={logoImg} alt='logo image'/>
```

## 106 Using client  Components

- `usePathName` to get the current path name.
- You will want to use `use Client` as far down as in the component tree as possible. So that only the required components are turned into client components.


## 108 Setting up a SQLite Database


- If using codesandbox, you can use the `better-sqlite3` package to use SQLite in the browser. It will allow you to use SQLite in local. 
- Since most of the Nextjs components are server based unless you defined them to work on client side. You can directly access the database in the components without using something like `useEffect` to fetch the data.

## 111 Suspense and Granular loading state

- Suspense component of the Nextjs helps in adding the loading at the Granular component level which helps us showing the orher components while the other components are still loading.

## 112 Handling Error

- File name should be `error.js` to handle the error in the Nextjs.
- For not found error like entering the wrong url. You can use file name `not-found.js` to handle the error.

## 115 Throwing not found Error

- To throw the not found error, you can use the `notFound` function from the `next/navigation` package.


## 117 Image picker component

- Event handler should be used in the client component. 

## 120 Introducing and Using Server Actions

- 'use server' directive  inside function which allows function to run on the server side along with async function.
- You are not allowed to add `use server` directive inside the componet is not Server Side Component.
- If you create the seperate file then instead of adding directive inside the function you can add it at the top of the file. Also in this case you may use these function even in the client component.

```
async function shareMeal(){

    'use server'


}

```

## 124 Managing the form submission using the `useFormStatus` hook

- `{pending}  = useFormStatus()`

## 127 Working with Server Action response  & useFormState

- `useActionState` is used to manage the form state. It is used to manage the form state like `useState` but it is used to manage the form state. It is imported from 'react'

```
const state = useActionState(saveMeal, {message:null}) // saveMeal is the function which is used to save the meal.

```


## 129 Triggering Cache Revalidation

- `revalidatePath('/meals','layout')` is used to revalidate the cache. It is used to revalidate the cache after the data is updated. NextJs throws away all the cache it has


## 133 Adding Dynamic Meta Data

- Using the 

```
export async function generateMetaData({params}){}
 
```


## 141 Setting Up and using the parallel routes

- Parallel Routes is a feature that allows you to render the content of 2 different route
- We must add layout.js in the folder where we want to add the parallel routes.
- You need to add one subfolder for each parallel route that you want to add.
- Add naming convention for that subfolder is : `@archive` and `@latest` and add page.js in both the subfolder
- Now in such case `layout.js` file does not only have the {children} prop but the one parameter for each parallel route with the name given after the `@` sign.
- Make sure that whenever you are working with the parallel routes, all the subfolder should support all kind of route . 
- To fix this Nextjs has deault.js file which is used to handle the default route.
- If both the page.js and default.js has same code / functionality then you can get rid of the page.js and use the default.js file only

## 143 Catch all routes

- It is represented by `[[...slug]]` folder. It is used to catch all the routes that are not defined in the routes.
- So all the routes like `archive/year=2024` or  `archive/year=2024/month=2` will be caught by this file.
- And in this case you may get rid of page.js file which is in the archive folder because anyways our `[[...slug]]` folder will catch all the routes. So the `page.js` inside this `[[...slug]]` will be shown.
- To handle error you should create `error.js` using 'use client' because error can occur both side on client and on server.

## 147 Server vs Client Components

- Prefer keeping  component server side unless you need to use client side component.
- `usePathName` hook returns the current path name.
- If you want to create the component as client out source them and create as granualar form of client component as possible

## 148 Nested route inside dynamic route

- `/images/news/{newsItem.slug}/image` is the nested route inside the dynamic route.

## 149 Intercepting navigation & using interception routes (Very Important Topic)


- [Read more](https://nextjs.org/docs/app/building-your-application/routing/intercepting-routes)
- Intercepting routes allows you to load a route from another part of your application within the current layout. This routing paradigm can be useful when you want to display the content of a route without the user switching to a different context.
-  The intercepting route essentially intercepts an internal navigation request and instead of showing the page you would see if you would reload the page or come to the page from outside the website, a different page will be shown.
-  Convention => (.), (..), (...)

## 154 Using and Understanding the route group (Very Important Topic)

- I want to achieve the different root layout for the starting page than for the rest of the applications. This can be achieved by using the `route group`.
- Create folder naming `(content)` and move all your folders / route in this and this will allow you to create the specific layout for all the folders inside the content folder.
- There can not be no othe file on the same level of route group

## 155 Building APIs with route handlers

- You can create the API route by creating the folder `api` and then creating the file inside it naming `route.js`
- This can have functions like GET , POST, DELETE etc.
  

## 156 Using middleware in route handlers

- Create the `middleware.js` along side the package.json file and create the function middleware.
- This function will get called everytime on every request , on every page when a request is made  

## 161 Option 2: Server Side Rendering

- In NextJs server side component can return the promises and can returned the fetched data 