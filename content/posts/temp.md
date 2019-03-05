---
title:
date: "2019-02-24T16:19:00.778Z"
template: "post"
draft: true
slug: "/posts/js-interview/"
category: "interview"
tags:
  - ""
description: ""
---

### Types

undefined
null
number
string
boolean
object <-- refrence type

trick questions:

- global scope: if a variable is not decleard anywhere in the code, it's global.

```
(function() {
  var a = b = 5;
})();
console.log(b);
```

Normal way of thinking about this is to look at the scope and say `b` will be undefiend since it's inside a function and is scoped to that function. However, since we never decleard b, it's set into the global and the console.log() will give us 5.

### Curring

a function with an arity greater than one is transformed into a nested series of functions.
source: http://2ality.com/2017/11/currying-in-js.html

Currying is a technique for transforming functions so that they help with partial application.

When you see functions like `doThis()()` that's called curring. Curring is

### checks

=== checks for type and value and `==` only checks value.
`[] === []` will return `false` because js checks the reffernce not actual value and `[]` create a new array so two different (empty) array are not equal.
More; https://dorey.github.io/JavaScript-Equality-Table/

### Prototypes

Any function that is created in js has a property assigned to it called `prototype` (accssible with `.__proto__`)
js is described as _prototype-baseed langauage_.
if you want to add methods to a function/class, you can use `.prototype.method` to add it to that class. for exmaple, if you wanted to add average method to Array, you can do the following:

```
Array.prototype.average = function() {

    //`this` keyword is a reference to the scope of the caller.
    const sum = this.reduce(function(prev, cur) {
        return prev + cur;
    });
    // return sum divided by number of elements
    return sum / this.length;
}
```

//Add bind
