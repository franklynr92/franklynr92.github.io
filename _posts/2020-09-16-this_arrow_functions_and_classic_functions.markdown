---
layout: post
title:      "This, Arrow Functions, and Classic Functions"
date:       2020-09-16 21:30:49 -0400
permalink:  this_arrow_functions_and_classic_functions
---


This is a story about this, arrow functions, and classic function and how they interact with each other.

THIS keyword allows us to refer to the properties that are defined on the object from within that object.

What does this even mean?

To talk about this , we would also need to talk about the DOM as well. The DOM is a Document Object Model. Pretty much what you are looking at now is called the DOM. What the DOM is this window you see in front of you. We can all the window the document. Inside of this document there is this tree with different objects that we can interact with. In order to interact with those objects and manipulate them we would need a model for that. Think of the models as functions to get things down.

Essentially this refers to wherever it is called upon. 

For example…
In React, we have components. We have two types of components class and functional components. It doesn't matter what kind of component it is if there is a this referred in that component, this would refer to that component itself.

If you were to go to your console, using cmd + option + j on mac, and type in this. What you would get back is an object, the Window. So this refers to wherever it is called within its scope.
What is the purpose of this when referring to arrow functions, ES6, and classic functions, ES5

Let me present to you this code snippet

### Code that doesn't work

```
var person ={
firstName: "John",
lastName: "Cena",
Age: "infinite",
skills:  ["can't be seen", "can't see him", "magician"],
printSkills: function() {
this.skills.forEach(function(skill) {
 var str = this.firstName + " likes to " + skill;
 console.log(str):
    });
  }
}:
//Uncaught TypeError: Cannot read property 'firstName' of undefined
```


## Classic Functions

What's happening with the above code is that the first `this` has access to it's property of skills but when the function is being run through the second this, this.firstName, does not have access to the person object's properties. It has fallen out of scope.

```
var person ={
firstName: "John",
lastName: "Cena",
Age: "infinite",
skills:  ["can't be seen", "can't see him", "magician"],
printSkills: function() {
var _this = this;
this.skills.forEach(function(skill) {
var str = _this.firstName + " likes to   skill" + skill; 
console.log(str);
});
}
};
person.printSkills();
```

In order for us to get the second this to have access to the firstName property we would have to pluck out a copy of this and use that copy when going through each of those skills. As you can see in the above code.

var person ={
firstName: "John",
lastName: "Cena",
Age: "infinite",
skills: ["can't be seen", "can't see him", "magician"],
printSkills: function() {
this.skills.forEach(function(skill) {
var str = this.firstName + " likes to   skill" + skill; 
console.log(str);
}.bind(this));
}
};
person.printSkills();

In the above code we display what the arrow functions will do. Here instead of making a copy of this, we are just binding it through the function to have access to it in this scope, saving more memory in the long run.

## ARROW FUNCTIONS

Enter the arrow functions:

```
var person ={
firstName: "John",
lastName: "Cena",
Age: "infinite",
skills:  ["can't be seen", "can't see him", "magician"],
 printSkills() {
   this.skills.forEach(skill => {
    var str = this.firstName + " likes to   skill" + skill;
    console.log(str);
   });
 }
};
person.printSkills();
```


Arrow functions help to deal with the scope of the 'this' keyword in our Javascript code. Instead of writing out all this code, with arrow functions we are implicitly returning  whatever is after the arrow. Also being that this is being called through with an arrow function it passes it values through the function giving it access to the this.skills array.


## SUMMARY

*Classic functions*
```
var studentList = function(students) {
console.log(students);
}

studentList(["Joe", "Cindy", "Jeanne"]);
```


Arrow functions help clean out code 

*Arrow functions* =>

```
var studentList = students => console.log(students) ;

studentList(["Joe", "Cindy", "Jeanne"]);
```

By using arrow functions we do things we clean up our code and we handle the scope of what this will have access to. The arrow function binds this to the function.
In a classic function in order to bind this you would have implicitly call it in the end. Essentially what the arrow functions are doing is cleaning up code and creating better performance for your app since we are using less memory.
If your app only has a few lines of code you won't see much of a difference, the difference can be seen with very large application with many lines of codes.
