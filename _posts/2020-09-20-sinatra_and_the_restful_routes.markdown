---
layout: post
title:      "Sinatra and the REStful Routes"
date:       2020-09-20 17:30:26 +0000
permalink:  sinatra_and_the_restful_routes
---


This what I have learned from doing my Sinatra Project from Flatiron School.
Project is called Gracious Gourmet.

###What is Sinatra?
Sinatra is a gem or a web application framework that has been created to help alleviate headaches in web development. In combination of RESTful routing you can make a website flow through your controller.

Keeping in mind MVC which stands for model view controller. The model is where the logic is kept, the data is stored here and also can be manipulated. Views are what the client can view or see, this is what is called the “front-end”. The controller is like the middleman between the model and the view. The controller relays information from the application to the browser where the user is requesting the information and vice-versa when user is sending information.

Sinatra has many different tools to it. In combination with ActiveRecord, which is included in Sinatra gem, you can use this to create tables and migrate it so that information can be stored. To make a MVP, minimum viable product, with SINATRA you want to at least have one full model and controller that has the 7 RESTFUL ROUTES and CRUD. CRUD stands for create, read, update, and delete. To do this we use the 7 RESTful routes to do this inconjuction with the HTTP verb to get the user to the proper view.

The following are the 7 RESTful routes:

INDEX — This is the landing page, the first “view” the user sees when they first go to your website. This Route uses the ‘get’ HTTP verb

New — This is where a from is displayed to then get you to the next route. This Route uses the ‘get’ HTTP verb.

CREATE — Creates an instance of something from that form. This Route uses the ‘post’ Route to create that instance 
and in the controller you would then save that instance to the database so that it can persist for that user.

SHOW — Shows what is currently stored in the database and available for the user to see. This Route also uses the ‘get’ HTTP verb.

These following routes need something special in the config.ru
to get them to actually be recognized:

EDIT — This route is created to take you to a view where you can edit instances of those creations in the database.

UPDATE — This route is used to update or change instance of those creations that are in the database

DESTROY — This route is used to delete instances of those creations from the database.

The above routes need a special key word in the config.ru file, `use Rack::MethodOverride` , to be able to run through them. The reason being is that HTTP only recognizes get and post http verbs when it was first created. To overcome that obstacles middleware was made so that other requests can be taken in. In-conjunction with that keyword you would also put in this line of code under the form tag in order to get that form to do what you were looking for.

The line of code is the following:

```
<input type=”hidden” name=”_method” value=”delete”>
<input type=”hidden” name=”_method” value=”put”>
```

To fully use these routes we use the 5 HTTP verbs to move through these routes. 

The 5 HTTP verbs are the following:

GET — Get the item and show it

POST — This is used to create, update, and destroy instances of things.

Put/Patch — Both of these items are used for updating instances.

Put is to create a new thing and replace the old

Patch is to edit parts of that thing

Delete — Deletes the item.
