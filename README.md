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