---
layout: post
title:      "Active Record Associations, Validations and the MVC architecture"
date:       2020-09-20 17:27:34 +0000
permalink:  active_record_associations_validations_and_the_mvc_architecture
---


###START
Before I speak about AR Associations, let us touch upon the MVC.

Model, view, controller.

The model holds the database where the `object` is essentially held.

The view is what the user sees, that is presented from the controller.

The controller is the middleman that takes the request from the user/client using the browser requesting the data.

###Request flow

When a client requests data from the view, the request goes to the `controller` grabs the data the client is looking for from the `model`. The model then gives the controller that data. The `controller` then takes that data and presents it to the client to `view` in the browser. This is the request flow.

![](http://miro.medium.com/max/440/0*SSGBaMt-QI4Np6I1)

To go more into depths, the model is connected to a database that holds data for the application.

With that out of the way, let’s talk about **Active Record Associations**.

###ActiveRecord Associations

```
has_many: through:
has_many:
belongs_to:
```

What exactly does this reference?…

These items all reference relationships made in ActiveRecord Associations. These relationships made can give access to other tables/models so that you can interact with them in the backend and show some cool funky stuff on the view(browser GUI).

What these Associations do is help the models/database connect to other databases.

Let’s talk about a car’s and their issues.

A vehicle is owned by someone who uses it from time to time, a user. That vehicle over time, due to wear and tear, and other such complications may come across some issues. Sometimes a user may have more than one vehicle with different issues. Sometimes those vehicles may have different mechanics that help with different issues depending when the issue comes across. One issue can be persistent throughout other vehicles.

To put it into coding

```
User 
has_many :vehicles
has_many :issues through: :vehicles

Vehicle
belongs_to: user
has_many :issues

Issue
belongs_to :vehicle
belongs_to :mechanics

Mechanic
has_many :issues
has_many :vehicles through: :issues
```

With these associations made a user can make a vehicle and save it to their database. They can then create issues for their vehicles. Afterwards once mechanics are integrated into the application they can help resolve those issues the user’s vehicles are having.

###Validations

There are other things as well such as validations to make sure user data is valid and data is being repeated unnecessarily. Validations can also be used to make sure the user is putting in the data the way that you intended to be.

```
User
has_many :vehicles
has_many :issues, through: :vehicles
has_many :mechanics
validates :user_name, :email, :name, presence: true
validates :user_name, :email, uniqueness: true
end
```

What this is doing is creating validations to make sure that a user doesn’t sign up with the same user_name and email as someone else as there can be one instance of an email for a person.

We also don’t want a user to have the same user_name as someone else in case in the future we want to create a feature where a user can search for someone else using that attribute.

How annoying would it be to try to search for someone but not get the right person because of something like that. This is something to take into consideration when coding as well.
