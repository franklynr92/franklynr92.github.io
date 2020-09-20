---
layout: post
title:      "Async, sync, fetch the promises"
date:       2020-09-20 17:19:10 +0000
permalink:  async_sync_fetch_the_promises
---

While things are happening it gets other things so that it doesn't take forever to load up.

Synchronous code is when code continues off only when the previous piece of code finishes.
Asynchronous code runs while other code is running.

To put in perspective, think about you going to eat at a restaurant.

Let's say you order appetizers of wings, main entree of burgers with fries, and a desert of ice cream.

Synchronous code would be the chef cooks your wings first, then once that is done cooks your burgers, once the the burger is done they fry your fries, and once your fries are done then the ice cream comes out. The problem this presents right away is that, the burger is done before the fries causing them to be at a less than desirable temperature when it reaches your table. Now imagine a restaurant full of patrons and this is how the chef cooks. It would be a disaster.

## ENTER ASYNCHRONOUS
What asynchronous code will do here is while the wings are being cooked, the chef prepares your burgers and fries to cook. When the wings have gone out, the chef starts to put the burgers on the stove, times the fries to be cooked and finished at the same time as the burger so your meal can be more enjoyable.

Asynchronous code is meant to increase performance and efficiency of code so that the user doesn't have to wait for other longer processes to be completed.

## ENTER FETCH.

### *What is a fetch?*

**Fetch**

Fetch takes in the url of the api or backend of where the data is coming from.

Fetch is used to grab things or data from sites, that are sent out in strings as all things are in the internet.

To then translate those objects or things for the user to see it, we then taken it in as JSON(javascript string object notation) and then passed in as javascript for it to be displayed on the browser properly.

We can chain a .then after the return of the url to do things with that data. We can log it to the console, save it as a object as part of state, we can display to the user on the DOM, etc.

A fetch can be returned in a function as well making it reusable. Fetch returns data using promises, based of the promises API.

The purposes of promises are to help developers(you) deal with with asynchronous behavior in Javascript. To return a promise object you would just need to use return new promise().

Inside of the fetch function you would pass in a url that you watch fetch data from, i.e. an API.

Fetch can't be made asynchronous since it is already asynchronous by nature.

Promises help deal with asynchronous behaviors that the fetch has. There is a delay between when we send out a request and when we receive it. We use the .then chain off the previous response(promise).

The .then acts as an assembly line where we are transforming our data in different stages. Promises make asynchronous code more manageable and more reusable.

Being that the internet is wide and vast, there are times when we fetch something and get something unexpected. These things can happen for many reasons, the server is down, too many requests, usually the error could be server side but that isn't the only case. A promise doesn't always return what you were expecting it to return. To handle the chance of an error occurring we can chain a .catch at the end of the fetch and log the error for debugging purposes.

*`Summary`*

Some key things to remember about Fetch.

* Fetches uses promises to return back data. 
* A promise will always return a promises.
* We chain a .then after a promises is returned to continue off the chain.
* We are able to add a .catch to a promise for error handling.
* Fetch, fetches data usually from an API.
* Fetch is asynchronous , meaning it runs other pieces of code while it is committing a task.
