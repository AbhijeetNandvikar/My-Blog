---
title: OBJECTS in js
date: "2020-06-07T22:12:03.284Z"
description: "This blog will give a clear understanding of objects in js"
---

In this blog, I will try to cover the concept of objects in javaScript in detail. After reading this blog I am sure you will have a clear understanding of the topic. Let's get started…

### Introduction.

Object in javaScript is just a collection of key-value pair. A key can be considered as a unique name for every value so that we can access them. Values can be either a primitive data type or they can be a function or another object. These key-value pairs are called as properties or methods depending on the type of value.

Let’s take an example :

Here a person is an object. It has two properties called name, age and one method called greets. Here name, age, greets belongs to the person object and we can access them in the following way.

`gist:AbhijeetNandvikar/89d8da72d10fcd9ad63667d48271c12b#objExample.js`

We can also access objects using square bracket notation
`gist:AbhijeetNandvikar/89d8da72d10fcd9ad63667d48271c12b#objExample2.js`

> Note : Square bracket notation is used incase we want to access properties dynamically

### Creating objects in javaScript

There are various methods of creating an object but we will focus on the following three :

#### Direct method :
We have seen this in above examle

`gist:AbhijeetNandvikar/89d8da72d10fcd9ad63667d48271c12b#oc1.js`
 
#### Using a function constructor :

`gist:AbhijeetNandvikar/89d8da72d10fcd9ad63667d48271c12b#oc2.js`

This is dynamic way for creating javaScript objects.

Animal() is just a simple js function which acts as a constructor for Tiger object. Notice how 'this' keyword is used here, it is used to create properties and methods for Tiger object. 

The 'new' keyword creates an empty object. 'this' keyword in Animal function references to that empty object.

If we simply declare some variable in Animal() our code will not throw any error, but that variable will not become a property of object.

For eg. in our case observe that color is not a property of the Tiger object.

> Arrow functions can’t be used as a function constructor

> Always the first letter of function constructor name should be capital according to convention

> The Arguments in Animal function can be used to pass values to object dynamically.

> This is a dynamic way of creating an object in js.



#### Using ES6 class concept :

`gist:AbhijeetNandvikar/89d8da72d10fcd9ad63667d48271c12b#oc3.js`

Here we are creating a class named Animal. All the properties and methods which we want to assign to object are placed inside the class constructor. 

The constructor receives arguments which we have passed while object creation. 

A JavaScript class is declared with a PascalCase in contrast to other JavaScript data structures ie. first letter in every word should be capital. Eg ; class AnimalKingdom



> Make sure you use you call super() method inside the constructor() method if the current object extends some other object, this is done so that we can use properties and method of parent class.


#### Mutability of js objects 

Primitive data types like number, boolean and strings are Immutable whereas objects in js are mutable in nature. Mutability means that we can edit the values after it is assigned. Let’s look at a simple example which will make things clear.

`gist:AbhijeetNandvikar/89d8da72d10fcd9ad63667d48271c12b#mut1.js`


In above code snippet variable name1 contains a string - ‘Rahul’ 
 
On second line we are saying that assign value in name1 to name2. So here the value gets copied and if we change variable name2 then, name1 don’t gets affected.

which is obvious 

but objects don't exhibit such behaviour,

`gist:AbhijeetNandvikar/89d8da72d10fcd9ad63667d48271c12b#mut2.js`


In case of objects, person1 variable  holds the address to memory location where the object data is stored and when we assign person1 to person2 this address gets copied into person2 variable.

 Therefore now making changes in person2 will also affect person1 object.


Lets take one more example :
`gist:AbhijeetNandvikar/89d8da72d10fcd9ad63667d48271c12b#objeg.js`

In case 1 answer will be true because both variable contains same address and on comparison answer will be true.

On the other hand Case 2 output will be false.
This is because even though person3 and person4 have the same content inside they are stored on different memory location and above two variable only contains their addresses.


Now you must be wondering how to compare two objects? How to find whether objects received from two different sources have the same properties and methods?

Actually there is no direct way because the variable stores the address to the memory locations and the content inside that memory location is not evaluated,

But don’t worry there is one hack though…

We can Convert the objects which we want to compare in string format using JSON.stringify() method.
Store those values and compare them using equality operator. And now the output will be true

`gist:AbhijeetNandvikar/89d8da72d10fcd9ad63667d48271c12b#objcomparison.js`


#### Working with objects :
Here are some of the methods which can be uselful while working with objects..

* Object.create() : The Object.create() method creates a new object, using an existing object as blueprint.

`gist:AbhijeetNandvikar/89d8da72d10fcd9ad63667d48271c12b#obj.create.js`

* object.keys() : 
The Object.keys() method returns an array of a given object's own enumerable property names, iterated in the same order that a normal loop would. 

`gist:AbhijeetNandvikar/89d8da72d10fcd9ad63667d48271c12b#obj.keys.js`

* object.assign() :
The Object.assign() method copies all enumerable own properties from one or more source objects to a target object. It returns the target object.
//Object.assign(target, ...sources)

`gist:AbhijeetNandvikar/89d8da72d10fcd9ad63667d48271c12b#obj.assign.js`

* object.freeze() :
The Object.freeze() method freezes an object. A frozen object can no longer be changed; freezing an object prevents new properties from being added to it, existing properties from being removed, prevents changing the enumerability, configurability, or writability of existing properties, and prevents the values of existing properties from being changed. In addition, freezing an object also prevents its prototype from being changed. freeze() returns the same object that was passed in.



* The Object.seal() method seals an object, preventing new properties from being added to it and marking all existing properties as non-configurable. Values of present properties can still be changed as long as they are writable.

`gist:AbhijeetNandvikar/89d8da72d10fcd9ad63667d48271c12b#obj.fs.js`





